# Ads while Lovable, Bolt and v0 build: terms and how

Task: topc-social/topc-tasks#69 (follow-up to #67, pick 1). Desk research, 2026-10-25. Not legal advice. Quotes came through a page summariser, so re-read them on the live pages before relying on them.

**Short answer:** it's a grey area, and it can be done. None of the three products' terms mention extensions or ads. Their "don't modify / interfere / automate" clauses bind the user, not the extension maker. Chrome allows ads next to third-party sites under four conditions. The real risks are the store listing rules, the vendors blocking us, and trademark use.

## The three products' terms

**Lovable** ([terms](https://lovable.dev/terms), [platform rules](https://lovable.dev/platform-rules)). Verdict: **grey**.
- Relevant clauses: "copy, modify, distribute… or otherwise exploit the Services"; "use automated tools (such as bots, scrapers, or crawlers) to access or interact with the Services"; "overload, disrupt, or interfere with the normal operation"; no use of the name or logos "in any way that implies our affiliation".
- Nothing on extensions, ads or overlays. An overlay is arguably not "modify the Services".

**Bolt.new (StackBlitz)** ([terms](https://stackblitz.com/terms-of-service), [AUP](https://stackblitz.com/acceptable-use-policy)). Verdict: **grey, leaning risky**.
- §2.3: "interfere… with the proper working of the Services"; "modify… or create derivative works"; prohibited content includes "unauthorized or unsolicited advertising". §1.5(a): marks only per their brand guidelines. AUP §3.5: no scraping "through automated means".
- It's the only one of the three with an advertising clause, though that clause is about content users post.

**v0 (Vercel)** ([terms](https://vercel.com/legal/terms), [AUP](https://vercel.com/legal/acceptable-use-policy), [AI terms](https://vercel.com/legal/ai-product-terms)). Verdict: **grey**.
- §12: "modify… or create derivative works"; §12(v): don't obscure notices. AUP: "using automation to interact with Vercel's website"; no web scraping of the AI Services.
- The AUP's "using automation to interact" is the clause closest to an extension that watches the page.

Nothing in these terms binds a third-party extension maker. Trademark is the main exposure there. Tortious interference: no source found.

## Chrome Web Store and Firefox

From Chrome's [Ads policy](https://developer.chrome.com/docs/webstore/program-policies/ads): ads next to a third-party site are allowed "only if all of the following criteria are met":
- "clearly disclosed to the user"
- "clear attribution of the ads' source"
- "do not interfere with any native ads or functionality of the website"
- "do not mimic or impersonate the native ads or content"

The same policy also says:
- Ads must be "easily removable by either adjusting the settings or uninstalling".
- "AdSense may not be used to serve ads in Products."

Chrome's [single purpose FAQ](https://developer.chrome.com/docs/webstore/program-policies/quality-guidelines-faq):
- Bundling ad injection with other functionality is a no: "This violates the single purpose policy."
- It's fine "if injecting ads is the single purpose of the extension".
- So the extension does one thing: show the sponsored line while you wait. No build timer bundled in.

Chrome's [affiliate ads policy](https://developer.chrome.com/docs/webstore/program-policies/affiliate-ads):
- The program "must be described prominently" on the store page.
- It needs "a direct and transparent user benefit". The revenue share may count (inference, not a ruling).

Browsing data is restricted, so send only impression events, never page or chat content.

[Firefox](https://extensionworkshop.com/documentation/publish/add-on-policies/): injected content must be clearly identified as coming from the add-on, and changes to web content must be opt-in; the install permission prompt doesn't count.

## Precedents

- [Google, 2015](https://security.googleblog.com/2015/05/new-research-ad-injection-economy.html): 192 deceptive ad-injection extensions removed (14M users), over the narrow-purpose rule.
- [Superfish/Lenovo, FTC 2017](https://ftc.gov/news-events/press-releases/2017/09/lenovo-settles-ftc-charges-it-harmed-consumers-preinstalled): it was unlawful because there was no consent or disclosure.
- Honey/PayPal: about swapping affiliate cookies, not overlays. A class action was dismissed in November 2025 ([hellopartner](https://hellopartner.com/2025/11/25/paypal-wins-dismissal-of-influencer-lawsuit-over-honeys-alleged-cookie-stuffing)). One source says a consolidated case continues in 2026 ([ppc.land](https://ppc.land/honey-loses-7-000-merchants-as-judge-lets-creator-lawsuit-proceed/), weak, docket not checked).
- [Facebook v. BrandTotal](https://www.proskauer.com/blog/facebook-brings-suit-against-developers-of-a-browser-extension-that-harvested-user-data): Facebook sued an extension maker for breach of terms over data scraping. [Settled in 2022](https://techcrunch.com/2022/10/03/meta-settles-lawsuit-for-significant-sum-against-businesses-scraping-facebook-and-instagram-data).
- No case found about an extension overlaying ads on a SaaS tool's waiting screen.
- Kickbacks patches third-party coding tools and says it "does not guarantee that this is permitted by those platforms' terms" ([AdGuard](https://adguard.com/en/blog/ai-coding-ads-kickbacks-vscode.html)). No reaction from Anthropic or Microsoft found.

## How the extension would work

- **Previews run on separate domains from the editor page:** Lovable `preview--*.lovable.app` ([source](https://docs.lovable.dev/api-reference/projects/create-embed-url)), Bolt `*.webcontainer-api.io` (weak: [a bolt.diy fork](https://huggingface.co/spaces/bitsnaps/bolt.diy/blob/main/app/routes/webcontainer.preview.%24id.tsx)), v0 `*.vusercontent.net` ([source](https://community.vercel.com/t/v0-demo-iframe-works-on-localhost-but-not-in-production-csp-blocks/30442)).
- **Detecting a build:** a content script on the editor page watches the chat pane (stop button, streaming text) with a MutationObserver. It never needs to touch the preview iframe. That's inference; the DOM wasn't inspected live.
- **Proof it can be done:** [Vibesuite](https://chromewebstore.google.com/detail/vibesuite-add-ons-for-lov/gaodnbdamhdecolnkilbbddmljfbkkbg) already shows live generation status and times on Lovable, Bolt, v0 and Figma Make. Lovable even [lists community extensions](https://docs.lovable.dev/integrations/chrome-extensions). None of them show ads.
- **Wait length:** Lovable only, from blogs: 30–90s, "a minute or two", 2–3 min ([rapidevelopers](https://rapidevelopers.com/lovable-issues/how-to-use-lovable), [websitesetup](https://websitesetup.org/how-to-build-website-with-lovable/), [supademo](https://supademo.com/user-flow-examples/lovable)). Bolt and v0: no source found. That's over the 10-second attention limit, the same weakness as the Claude spinner.

## Routes where we own the wait screen

- **v0 Platform API:** streams generation as SSE (`chats.createStream`), so our own front end owns the wait ([docs](https://v0.app/docs/api/v2/reference/chats/create-chat-streaming.md)).
  - The [API terms](https://vercel.com/legal/api-terms) have no advertising clause. They require disclosing AI use to end users, and ban reselling or getting around capacity limits.
  - This is the cleanest route.
- **bolt.diy:** MIT-licensed, but WebContainers need a commercial licence for for-profit production use, with no public price ([webcontainers.io](https://webcontainers.io/enterprise)).
- **Lovable API:** Business plan and up, with no build or streaming hook ([docs](https://docs.lovable.dev/api-reference/projects/create-embed-url)).
  - Lovable runs an [affiliate program](https://lovable.dev/affiliates) (up to $100 per new subscriber).
  - No source found for a Vercel or StackBlitz affiliate program.

## Verdict

1. Grey, not banned. The terms risk falls on the user's account; Bolt's terms are the closest to a ban.
2. Chrome allows it if the extension is ads-only, disclosed, attributed, never touches the site's own ads or features, is easy to turn off, and doesn't use the vendors' marks. Expect the vendors to block it or the page structure to change and break it, more than a lawsuit.
3. The waits (30s to 3 min, Lovable only, from blogs) are past the 10s attention limit, so this has the same weakness as Kickbacks.

## Weak claims

- The Honey 2026 status
- The Bolt preview domain
- All wait times
- What each tool shows on screen during a build (not inspected)
- Anthropic's "no ads" wording
- Whether Chrome accepts a revenue share as the user benefit

Not checked: the full Lovable API docs, the vendors' brand guidelines, the Honey docket, live DOM inspection.
