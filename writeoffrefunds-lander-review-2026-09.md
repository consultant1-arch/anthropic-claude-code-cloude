# writeoffrefunds.co.uk lander: review of the 6 September 2026 audit export

**Reviewed by:** Claude, from the uploaded export (screenshots, view source HTML and audit notes) of https://www.writeoffrefunds.co.uk/1/v1/1-landing
**Context:** this is the paid landing page the allegiant.co.uk write off hub banner links to. It is a Next.js app on Vercel, so none of it is editable over the WordPress connection. Fixes below are for the lander's developer and the compliance team. Nothing on the WordPress side needs changing as a result of this audit.

## Verified against primary sources

- **The headline banner is accurate and cited.** "FCA confirms £129 million has already been paid out to UK drivers" matches the FCA press release of 19 September 2025 (around 270,000 motorists due £200 million for underpaid claims, £129 million already paid to almost 150,000 customers at that date). The footnote links the right source. If anything the figure is now conservative, since the programme total is £200 million.
- The £1,896 FOS mean top up claim is footnoted with the qualification and points to allegiant.co.uk/wofc, consistent with the main site.
- The compliance footer carries the FRN, ICO and Companies House numbers, the free route wording (lender or insurer direct, then FOS, FSCS for failed firms) and links to the policy set on allegiant.co.uk. All consistent with the main site.

## Fixes needed, in priority order

1. **No fee disclosure anywhere on the page.** The footer has the free alternative wording but never mentions that Allegiant charges a success fee, or the 18% to 36% including VAT range disclosed on allegiant.co.uk. For a CMC financial promotion this is the gap most likely to draw CMCOB criticism. Add the standard fee sentence to the footer.
2. **"Millions of UK drivers... have likely been underpaid... according to a major investigation by the FCA" overstates the source.** The FCA found around 270,000 motorists were underpaid, with £200 million due. "Millions have likely been underpaid" attributes to the FCA a scale it did not find, which sits badly against the clear, fair and not misleading standard. Reword to the FCA's own numbers, for example: "The FCA found motorists were underpaid on written off vehicle claims, with £200 million in compensation due to around 270,000 drivers."
3. **The form submits the vehicle registration by GET.** On submit the reg lands in the URL query string, and from there into browser history, server logs and the page location seen by every advertising pixel on the page. A registration number is personal data in this context. Change to a POST or scripted submission and confirm the reg never reaches the tracking domains. UK GDPR data minimisation.
4. **No consent management platform is visible.** The page loads GTM, Google Ads, TikTok, Meta, Snapchat, Taboola, Clarity, Mouseflow and Trustpilot, and neither the audit nor the screenshots show any cookie banner. If those pixels fire before consent, that is a PECR breach on a lead generation page. Verify in a cold browser and gate everything non essential behind consent. Also: Clarity and Mouseflow are BOTH running here, the same double session replay issue flagged on the main site, on a page that collects vehicle registrations.
5. **The structured data uses the old FCA register record URL** (register.fca.org.uk/s/firm?id=0010X00004QBAvNQAX). The main site retired record ID links this week. Swap to the durable FRN keyed link: https://register.fca.org.uk/s/search?q=836810&type=Companies
6. **Meta description grammar:** "Have you wrote your car off since 2019?" should read "Have you written your car off since 2019?". This text appears under the brand name in Google results.
7. **Copyright line says 2025**; update to 2026.
8. **Press logos** (Mirror, The Sun, The Times, FT) under "Scandal reported in the national media": keep evidence of each outlet's coverage on file, and ideally link the articles.

## SEO notes (secondary, it is a paid lander)

- The canonical tag pointing all variant URLs at the domain root is correct and prevents the variants competing with each other or with allegiant.co.uk.
- The marketing copy is client rendered (the raw HTML body is empty before hydration), so the page will not rank organically in any meaningful way. That is acceptable for a paid lander; no action unless organic ranking is ever wanted, in which case the copy needs server rendering.
- Keeping this on a separate domain, canonicalised and paid only, avoids cannibalising the main site's write off hub. The "3 million cars written off since 2019" line is conservative against the hub's 3.6 million (2019 to 2025) figure; align them if the pages are ever compared.

Sources: [FCA press release, 19 September 2025](https://www.fca.org.uk/news/press-releases/over-270000-motorists-receive-motor-insurance-compensation-insurers)
