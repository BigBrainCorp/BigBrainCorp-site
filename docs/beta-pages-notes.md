# Notes for the BigBrain Visualizer beta pages

Written on November 7, 2026 while preparing the site for the closed beta.

## Decisions the owner has made

No placeholder is left in any page.

- Audit event retention is twelve months: sign-in, activation and seat events are kept for
  twelve months, then deleted. A nightly job in the service will enforce it once built.
- The contact address for BigBrain Visualizer is `Info@BigBrainCorp.com` everywhere on the
  site, and the privacy page's header and Contact section now show that address too, so
  the whole page shows one address.
- The effective dates on `terms.html` and `privacy.html` are November 7, 2026. Move them to
  the push date if the owner pushes later.

The legal entity (BigBrainCorp LLC), the governing law (Arizona, courts of Maricopa
County), the liability cap (the lesser of fees paid in the previous twelve months or 100 US
dollars), the 30 day response time for data requests, the record retention wording, and the
under 13 rule are all taken from the other product's pages as they stand today.

## Final page addresses

These names are final. The Mac app's sign-in screen and the product page footer link to them.

| Page | Address |
|---|---|
| Terms of Use | https://bigbraincorp.com/terms.html |
| Privacy Policy | https://bigbraincorp.com/privacy.html |
| Security Policy | https://bigbraincorp.com/security.html |
| Why BigBrain System Visualizer (unlisted article) | https://bigbraincorp.com/why-bigbrain.html |

The names copy the other product's site, where the same three documents are `terms.html`,
`privacy.html` and `security.html` and the footer of every page links to all of them. One
terms page for the company, with the Visualizer named inside it, matches how the privacy
page already works here (one page covering the site, the viewer, and now the app and
service). The two new pages are in `sitemap.xml`; the product page stays unlisted.

## What the other product did for its beta, and what carries over

Read: the other product's terms, privacy, security, support, refund, FAQ and downloads
pages as they are today, the same pages as they were during its beta (the commits of
August 17, 2026 that removed the beta framing), its release notes for version 1.0.0
(leaving beta) and 1.1.2 (an agent feature in beta), and the blog post introducing that
agent beta.

What it did:

- A beta code on the downloads page gated the builds. The copy said who to write to for a
  code ("Contact the support address if you need one"). The same code was entered at
  checkout in place of a payment. The Visualizer's product page and license service work
  the same way (the code before the download and at Subscribe), which is why the one line
  under the code box here also says to write to support.
- The downloads page carried a short beta banner: builds may change between releases, use
  them for evaluation. Carried over into the terms page's "Beta software" section rather
  than onto the product page, which already says the app is in a closed beta when it asks
  for the code.
- The support policy said "no formal SLA during the beta" and "may change between beta
  releases without notice". The Visualizer has no support page yet; the terms page says the
  app and service may change during the beta and names the support address instead.
- Its terms were never beta-specific. The beta ended by removing the code and the labels,
  and the terms stayed. The agent beta later added one section ("Beta status": may change,
  break or be withdrawn; no refund on its account). The Visualizer's terms take that shape:
  one short beta section, and the rest written to survive the beta.
- Its legal pages give an effective date, the vendor name and a contact address in a header
  card, and a "Plain-English Summary" first. Copied.
- Its security page has "How to verify the app is genuine" with the `spctl` command, a
  "Telemetry" section, an "Honest limitations" section and an "Official domain" section.
  Copied in shape, with the Visualizer's facts.
- Its privacy page has a GDPR legal basis paragraph, a sub-processor list (Stripe,
  Microsoft Azure), a retention paragraph and a rights paragraph with a 30 day response.
  Copied into the new section of the privacy page.

What differs, because the Visualizer sells seats and signs people in:

- The other product has no account and no licensing server: a license file bound to a
  machine fingerprint, checked offline, any email for delivery. The Visualizer has an
  account (the verified email from Apple, Google or Microsoft through Microsoft Entra
  External ID), a license service that holds a device hash per Mac and the seat state, and
  an audit log. So the privacy page must say what the service holds and that it never sees a
  password, and the terms must say the account email is the account.
- Its license is one machine for a fixed number of days, bought once. The Visualizer's seat
  is one person on one Mac at a time, and signing in on another Mac moves the seat. Said in
  the terms and explained in the security page's "Seats" section.
- Its purchases happen on the website with a fingerprint pasted in. The Visualizer's happen
  inside the app, later, through Stripe Checkout and the Customer Portal. The privacy page
  says Stripe will handle payments and the card details never reach the company; the terms
  say subscription terms will be added before anyone can buy.
- Its refund policy is "no refunds after delivery". The Visualizer has no purchases during
  the beta, so there is no refund page yet; the terms say the beta costs nothing.
- Its app sends package names to registries. The Visualizer's app sends nothing about the
  system to the company; the coding agent the person already uses does the reading, under
  their own account with that provider. The privacy page says so in the same words the
  other product uses for its own agent features.

## Decisions worth knowing

- The terms say a beta license ends 30 days after the code is taken or when the beta ends,
  whichever comes first. The service as built lets a beta license run to its own end date
  when the code is removed. The terms are the stricter reading on purpose: the company can
  always be more generous than its terms.
- The support address line under the beta code box is in the page's HTML, not in the
  script, so it shows whenever the code box shows.
- `security.html` names the app as "BigBrain System Visualizer" in the `spctl` command.
  Check the installed app's bundle name matches before pushing.
- The product page's Why section is drawn from the app repository's design document
  `docs/00-why-bigbrain.md`, cut to the site's plain style, with no names from its demo.
- The product page follows the shape of the other two products' home pages: a headline in
  the visitor's words, the problem, why a design review rather than a code review, top
  reasons as cards, how it works as numbered steps, the scenarios as stories, what makes it
  different, a privacy promise grid, free and paid with the plan shapes and no prices, the
  download section with its four states, the viewers, and the guide and policies. The card,
  step and grid patterns are copied from the other product's home page styles; none of its
  sentences are. Two elements of that model have no source for this product and were left
  out: a "we needed this ourselves" passage and a "questions behind the tool" blog list.
- `why-bigbrain.html` is the full article behind the product page's Read more link, built
  from the app repository's `docs/00-why-bigbrain.md` with the demo's names and the cloud
  and payment vendors left out. It is unlisted like the product page (noindex, not in
  index.html, products.html or sitemap.xml) and linked only from the product page.
