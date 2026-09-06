# Allegiant WordPress Site Review (via WordPress MCP)

**Site:** https://allegiant.co.uk ("Allegiant | A CMC.")
**Review date:** 5 September 2026
**Method:** Read only review through the Allegiant WordPress MCP connection. No changes were made to the live site. The review covered site settings, users, plugins, themes, menus, pages, posts, comments and a sample of the media library.

---

## Summary

The site is in generally good shape editorially. The compliance footer is complete, a Cookiebot consent declaration is in place, security tooling (Wordfence, Cloudflare, activity logging, backups) is installed, and the blog is active and topical. The material risks are operational rather than editorial: every user account is a full administrator, the plugin estate is large with several high risk utilities left active in production, two session replay tools run side by side on a site that handles claims enquiries, and there is duplication in the compliance page set that could let two versions of a regulatory document drift apart.

Findings are grouped below with a priority label: **P1** (act this week), **P2** (act this month), **P3** (ongoing housekeeping).

---

## 1. Access control and user accounts

**Finding 1.1 (P1): all eight user accounts are administrators.**
Every registered user holds the administrator role. For a regulated firm this fails the least privilege principle expected under FCA systems and controls requirements and NIST access control guidance. An editor level compromise becomes a full site compromise, and any one of eight accounts can install plugins, edit code and export the database.

*Recommendation:* keep at most two named administrators. Move content staff to Editor, and anyone who only writes posts to Author. Review quarterly.

**Finding 1.2 (P1): a shared generic administrator account exists.**
The account "Claims Team" (sales@allegiant-finance.co.uk) is a shared login dating from 2017. Shared credentials defeat individual accountability and make the activity logs far less useful as an audit trail.

*Recommendation:* retire the shared account, reassign its content to a named user, and require individual accounts only. Enable two factor authentication for all users (Wordfence supports this).

**Finding 1.3 (P2): legacy email domains on active accounts.**
Three accounts still use the old allegiant-finance.co.uk domain, as does the site's admin notification address (sales@allegiant-finance.co.uk). Security notifications going to an unmonitored or generic sales alias is a real risk.

*Recommendation:* update the site admin email to a monitored IT or security alias on the current domain, and normalise user emails.

---

## 2. Plugin estate and attack surface

39 plugins are installed and 38 are active. That is a large attack surface for a site of this nature, and several of the active plugins are high impact utilities that should not sit enabled on production.

**Finding 2.1 (P1): high risk utilities left active.**

| Plugin | Risk if compromised or misused |
|---|---|
| Better Search Replace | Rewrites the entire database |
| All-in-One WP Migration + Unlimited Extension | Exports the full site (database, form entries, users) to a downloadable file |
| Download Plugins and Themes from Dashboard | Bulk code exfiltration from the admin |
| Simple Export Import for ACF Data | Exports and imports field data across sites |
| ACF Theme Code Pro | Development tool, no production purpose |
| WP Data Logger | Debug logging on production, contents and retention unknown |

*Recommendation:* deactivate and remove these when not actively in use. Where a migration export has ever been run, confirm no .wpress export files remain in wp-content, because they contain the full database and are a data breach waiting to be crawled.

**Finding 2.2 (P1): the MCP AI connector needs a governance wrapper.**
"Easy MCP AI" (the plugin providing this very connection) exposes 243 tools covering content, media, users and settings. It is powerful and useful, and it also means an AI session or a leaked credential can edit a regulated firm's financial promotions directly.

*Recommendation:* restrict the connector to a dedicated service account with the minimum role that still works, rotate its application password regularly, keep its actions in the activity log under a distinct user, and route any AI drafted public content through the firm's existing financial promotion sign off before publication (CMCOB 3 territory).

**Finding 2.3 (P2): duplicated tooling to consolidate.**
There are two backup stacks (UpdraftPlus and All-in-One WP Migration), two activity log plugins (Activity Log and Simple History), two thumbnail regenerators, two analytics session recorders (Microsoft Clarity and Mouseflow), and two payment stacks (Paymattic plus Paymattic Pro alongside WP Stripe Checkout). Each duplicate adds update burden and attack surface without adding capability.

*Recommendation:* pick one of each pair and remove the other. Suggested keeps: UpdraftPlus (scheduled, off site), Simple History or Activity Log (one only), one regenerator, one session tool (see 3.1), and a single payment plugin once current form dependencies are mapped.

**Finding 2.4 (P2): update hygiene gaps.**
Advanced iFrame Pro has WordPress automatic updates deliberately disabled (updates come from CodeCanyon only), so it needs a manual patching routine. The inactive "Allegiant Fraud and Scam Claim Form" plugin and the two inactive themes (allegiant v0.1 and Allegiant Finance) are dormant code that still needs patching or, better, removal.

*Recommendation:* remove inactive plugins and themes entirely, and add Advanced iFrame Pro to a monthly manual update checklist. Keep one prior default theme only if needed for fallback testing.

**Finding 2.5 (P3): positives worth keeping.**
Wordfence, Cloudflare, LiteSpeed Cache, activity logging and scheduled backups are the right shape of stack. Confirm backups are encrypted, stored off site in the UK or with appropriate safeguards, and restore tested at least annually.

---

## 3. Data protection (UK GDPR, DPA 2018, PECR)

**Finding 3.1 (P1): two session replay tools run simultaneously.**
Microsoft Clarity and Mouseflow are both active. Session replay on a claims website can capture form input including names, financial details and potentially health or vulnerability information typed by claimants. Running both doubles the exposure and the processor list for no analytical gain.

*Recommendation:* keep one tool at most. Verify that keystroke and input masking is on for all form fields, that recording only starts after Cookiebot consent for statistics or marketing cookies, that both vendors appear in the Cookiebot declaration and the privacy policy processor list, and that international transfer safeguards are documented.

**Finding 3.2 (P2): confirm consent gating end to end.**
A Cookiebot declaration is embedded on the Cookies Declaration page, which is good and self updating. What the page cannot show is whether Clarity, Mouseflow, Stripe and any WPCode injected pixels actually wait for consent before firing.

*Recommendation:* run a cold browser test: decline consent, then confirm no Clarity, Mouseflow or marketing requests fire. Repeat quarterly and after any tag change.

**Finding 3.3 (P2): form and payment data flows need a documented map.**
Contact Form 7, Paymattic and WP Stripe Checkout all take user submitted data. Where entries are stored, who receives notification emails, and how long records are kept should be written into the record of processing activities. WP Data Logger's output needs the same treatment or, preferably, the plugin removed (see 2.1).

---

## 4. Compliance content (CMCOB)

**Finding 4.1 (P2): duplicate regulatory pages risk version drift.**
Two pre contract pages are published: "Pre-Contract Information" (/compliance/pre-contract-information/, linked in the footer) and the older "Pre Contractual Information" (/compliance/pre-contractual-information/, last edited May 2026). The fees page slug is /compliance/our-fees-2/, which suggests an earlier fees page also exists. Two live versions of a regulatory document will eventually disagree, and CMCOB requires pre contract information and fee disclosures to be accurate.

*Recommendation:* choose the canonical version of each, 301 redirect the duplicate (Simple 301 Redirects is already installed), and add the compliance set to a scheduled review rota. The three complaints pages (Complaints Resolution, regulated, unregulated, plus the newer data protection complaints page) should be cross checked for consistency at the same time.

**Finding 4.2 (P2): the footer legal set is otherwise complete and current.**
Pre contract information, service summary, terms of engagement, complaints, cancellation, privacy policy (updated June 2026) and cookies are all linked from the footer menus. This is the right structure; keep it.

**Finding 4.3 (P3): content housekeeping.**
There are 14 draft pages (some stale since mid 2025, including old lender profile drafts), 5 private pages, 9 pages and 5 posts in trash. Stale drafts of regulated claims content carry a small but real risk of accidental publication of outdated information.

*Recommendation:* review drafts quarterly, delete what will not be published, and empty trash.

**Finding 4.4 (P3): comments and pingbacks default to open.**
Site defaults have comments and pings open on new content. No pending comments exist today, but user generated content on a CMC site can amount to an unapproved financial promotion or misleading claim if it slips through.

*Recommendation:* set new posts to comments closed by default, and close pingbacks and trackbacks entirely.

---

## 5. Configuration, accessibility and quality

**Finding 5.1 (P2): timezone is unset.**
The site timezone is blank, so WordPress falls back to UTC. Scheduled posts, log timestamps and anything time sensitive will be an hour out for half the year. Set it to Europe/London.

**Finding 5.2 (P2): image alt text coverage is patchy.**
Of the 15 most recent images, 6 have no alt text, including blog featured images. Alt text matters for WCAG 2.2 accessibility, supports Consumer Duty expectations around consumer understanding, and helps SEO. One recent upload also retains an AI generator default filename ("Gemini_Generated_Image_..."), which looks unprofessional in page source and image search.

*Recommendation:* add alt text on upload as standard, backfill priority pages, and rename files meaningfully before upload.

**Finding 5.3 (P3): site title and tagline tidy up.**
The title is "Allegiant | A CMC." and the tagline begins with a stray leading space and reads " Irresponsible Lending, Car Finance Claim & More.". Minor, but this text feeds search snippets and social previews. Tidy both.

**Finding 5.4 (P3): blog cadence.**
Content is topical and well aligned to the FCA motor finance redress scheme timeline, but the most recent post is 9 July 2026, roughly two months ago. Given redress scheme milestones through 2026 and 2027, a fortnightly cadence would keep the Insights section working as an acquisition channel.

---

## Priority action list

**This week (P1)**
1. Reduce administrator accounts to two named individuals; move everyone else to Editor or Author.
2. Retire the shared "Claims Team" login and enforce two factor authentication.
3. Deactivate and remove high risk utility plugins (Better Search Replace, migration tools, dashboard downloader, ACF export tools, WP Data Logger) and sweep for leftover migration export files.
4. Scope the MCP AI connector to a dedicated, least privilege service account and put AI drafted public content through financial promotion sign off.
5. Decide between Clarity and Mouseflow, remove the other, and verify input masking plus consent gating.

**This month (P2)**
6. Consolidate duplicate plugins (backups, activity logs, thumbnail tools, payment stack).
7. Remove inactive plugin and themes; add Advanced iFrame Pro to a manual patch checklist.
8. Canonicalise duplicate compliance pages with 301 redirects and cross check the complaints page set.
9. Run the cold browser consent test and document form and payment data flows.
10. Set timezone to Europe/London; update the admin email to a monitored alias; start alt text backfill.

**Ongoing (P3)**
11. Quarterly access, draft content and consent audits; annual backup restore test.
12. Close comments and pings by default; tidy title and tagline; resume blog cadence.

---

*This review was produced from data available through the WordPress REST API via MCP. It did not include server level checks (PHP version, file permissions, TLS configuration), Wordfence scan results or Cloudflare settings, which are worth a follow up pass with hosting access.*
