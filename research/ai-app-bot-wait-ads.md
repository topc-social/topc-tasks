# Ads in AI app and bot wait screens: who sells, what's empty

Task: topc-social/topc-tasks#71 (follow-up to #67 and #69). Desk research, 2026-10-25. Every figure is sourced; most come from vendors (see Weak claims).

**Short answer:** the money went into ads *in the answer*, not the wait. Well over $100M raised, by Kontext, Koah, Nexad, Gravity and ZeroClick. Ads in the wait itself are a June 2026 wave aimed at coding agents. Two slots look unserved:
- the Telegram bot "generating…" message
- the wait on web image and video generators

Evidence that small devs want this is thin.

## Sellers for AI apps

| Name | Where the ad shows | Sells the wait? | Dev payout | Traction | Launched | Source |
|---|---|---|---|---|---|---|
| Idlen (`@idlen/chat-sdk`) | "A native ad while the model thinks"; "Ads load during AI processing only" | **Yes** | SDK share not stated (extension users get 70%) | No numbers | June 2026 | [idlen.io](https://www.idlen.io), [stork.ai](https://www.stork.ai/tool/idlen-io) |
| uwait (user-side extension) | Banner while ChatGPT/Claude web loads | **Yes** | 50% user / 30% cited publishers / 20% uwait | 180 PH points | 2026 (PH launch looks like today) | [Product Hunt](https://www.producthunt.com/products/uwait) |
| largelanguageads.com | "Users see ads while waiting for their content to generate" | Yes (its own claim) | no source found | Only the maker's own post | ~May 2025 | [thread](https://yomotherboard.com/question/how-are-you-monetizing-your-ai-app-without-subscriptions/) |
| Unnamed (@spuliz) | Video ads while videos generate | Yes (looking for early users) | no source found | none | Oct 2024 | [HF forum](https://discuss.huggingface.co/t/ai-app-monetization/112552) |
| Kontext | Branded links under the chatbot answer | No | Rev share, % not public | $10M seed; DeepAI, Pixel Chat | no source found | [Adweek](https://www.adweek.com/programmatic/pitch-deck-kontext-raises-10-million-funding-ads-in-ai-chatbots/) |
| Nexad | Ads alongside AI answers | No | split not found | $6M seed (Prosus, a16z) | Apr 2025 | [Prosus](https://www.prosus.com/news-insights/group-updates/2025/prosus-ventures-and-a16z-co-lead-dollar-6m-seed-round-in-nexad) |
| Koah | Contextual ads in chat answers | No | Undisclosed | Over $26M raised; Luzia, Liner, DeepAI | Nov 2024 | [TechCrunch](https://techcrunch.com/2025/09/07/koah-raises-5m-to-bring-ads-into-ai-apps), [SiliconANGLE](https://siliconangle.com/2026/02/24/koah-raises-20-5m-scale-adsense-ai-across-apps) |
| Gravity | Ads in the conversation, fetched "in parallel" with the answer | No | not found | $38.5M total (dates conflict) | 2025 | [TNW](https://thenextweb.com/news/gravity-ai-ads-30-5m-series-a-agent-to-agent) |
| ZeroClick | Sponsored content inside answers | No | not found | $55M; founder of Honey | 2025 | [hellopartner](https://hellopartner.com/2025/09/02/market-movers-ai-ad-platform-zeroclick-raises-55-million) |
| Imprezia (YC S25) | Brand mentions in answers | No | per impression or click | ~$500K, invite-only | 2025 | [YC](https://ycombinator.com/companies/imprezia) |
| AdZen, ChatAds, Monetzly, EarnLayer, Dappier, Jutera, Aryel | In-chat ads and affiliate links | No | Dappier $5–15 CPM; ChatAds dev keeps 100% of affiliate fees | thin | 2025–26 | [Caplight](https://www.caplight.com/company/adzen), [getchatads](https://www.getchatads.com/blog/six-ad-monetization-platforms-for-ai-wrappers-compared/) |
| EthicalAds, Carbon | Next to chatbot output / in the CLI | No | not found | established dev ad networks | — | [EthicalAds](https://www.ethicalads.io/publishers/ai/), [Carbon](https://carbonads.net/cli) |

Only Idlen sells the wait in apps whose owners control it, with real docs. Every funded player sells the answer.

## Telegram

- **Telegram's own ads:** bot and channel owners get "50% of the revenue from ads displayed in their channels and bots" ([core.telegram.org](https://core.telegram.org/api/revenue)). In bots, the ad sits above the chat. It's fetched when the user opens the chat and cached for 5 minutes ([sponsored messages](https://core.telegram.org/api/sponsored-messages)). So these are chat-open ads, not processing ads.
- **AdsGram:**
  - Mini App formats: reward, interstitial and task.
  - Has a bots product, paid per click in USDT ([docs](https://docs.adsgram.ai/bots/), [Cointelegraph](https://cointelegraph.com/news/telegram-adsgram-launch-devs-earn-ton-ads)).
  - The docs don't say when the bot ad shows.
- **Telega.io:** interstitials in Mini Apps, plus posts broadcast to bot subscribers. Not tied to a wait ([blog](https://telega.io/blog/how-to-monetize-telegram-mini-app)).
- **Monetag:** rewarded interstitials for Mini Apps, ~$2 CPM by a third-party figure ([TechBullion](https://techbullion.com/monetag-unveils-new-monetization-option-for-telegram-mini-apps-via-rewarded-interstitial-ads/)).
- **The empty slot:** many bots post "generating…" and then edit that same message into the result ([Bannerbear example](https://www.bannerbear.com/blog/how-to-build-a-telegram-chatbot-to-create-custom-images-on-demand-with-bannerbear-node-js/)). Nobody sells that message.

## Discord

- **Policy** (July 2024 version, from search results because the live page returned 403): "Do not disclose API Data to data brokers, advertising networks or services, or any other monetization-related service." Bot messages should also be "relevant to the function of the Application." ([policy](https://support-dev.discord.com/hc/articles/8563934450327), [older version](https://support-dev.discord.com/hc/articles/25279999805975))
- **Discord's own route:** Premium Apps (subscriptions) in the US, UK and EU. A 70/30 split per a user forum post ([source](https://support.discord.com/hc/en-us/community/posts/22834240582423-Lower-Premium-App-Subscriptions-fees)).
- **AdBot (acord.dev):** pays server owners for ads posted in chat (vendor claim; [link](https://discordbotlist.com/bots/acord)).
- **Top.gg:** sells featured spots to bot devs ([link](https://top.gg/advertise)).
- **The "Bot is thinking…" wait:** no seller, and the policy makes it risky. Blocked rather than empty.

## Mobile AI apps

- AdMob "app open ads" are for splash and loading screens on app open or resume, not the generation wait ([AdMob](https://support.google.com/admob/answer/9341964)).
- AI art apps do ship ad SDKs. Example: ~872K installs with Google, Facebook, Unity and ironSource SDKs ([AppGoblin](https://www.appgoblin.info/apps/com.codespaceapps.aiartapp)). Users complain about "Too many adverts" ([reviews](https://grand-screen.com/apps/ai-art-generator-photo-draw/reviews/)).
- "Watch an ad to generate": no clean source found.
- Tooling exists (interstitial and rewarded ads), so there's no real gap here.

## Do small devs want it?

1. "Is anyone looking to show video ads while videos are being generated to optimize costs of expensive API calls?" ([HF forum, Oct 2024](https://discuss.huggingface.co/t/ai-app-monetization/112552))
2. "Ads helped too, but only when they didn't get annoying." (same thread, Aug 2025)
3. "every chat, every image generation, every model query costs real compute money… Maybe the answer isn't subscriptions" ([r/LargeLanguageModels](https://reddit.com/r/LargeLanguageModels/comments/1ol1cvm/how_will_ai_tools_stay_free_if_running_them_is_so/))
4. "I'm searching for ways to monetize usage without directly charging users" ([thread, May 2025](https://yomotherboard.com/question/how-are-you-monetizing-your-ai-app-without-subscriptions/))
5. Against: a free tool used by ~10,000 people made "£1" from ads ([Indie Hackers](https://www.indiehackers.com/post/how-to-monetize-my-tool-has-helped-10-000-people-but-only-made-1-78484f5691); quote taken from a search snippet).

## What's empty

- **Telegram bot "generating…" / "downloading…" messages:** nobody sells them. The bot owner controls the message, and Telegram already accepts ads in bots.
- **Image, headshot, logo and video generator waits on the web (10s to minutes):** Idlen is built for chat, and the image and video claims are unverified.
- **Discord's "thinking…" wait:** blocked by policy.
- **Mobile generation waits:** covered by AdMob and AppLovin.

## Verdict

1. Funded players sell the answer. Selling the wait is new, small, and mostly about coding agents.
2. The clearest unserved slot is the Telegram bot "generating…" message. The web image and video generator wait comes next.
3. Demand is anecdotal, and ad money on small traffic looks tiny. A seller has to bring advertisers, not just an SDK.

## Weak claims

- The Idlen, uwait, AdsGram, Telega, Monetag and Top.gg figures are from the vendors.
- The Discord 70/30 split is from a forum post. The policy text is the 2024 version, read via search.
- Gravity's dates conflict. Craiyon "ads during generation" comes from a third-party source only.
- uwait's launch date is inferred.
- No HN or X threads found. BotStat, TON ads and Nativo-for-LLM: no results.
