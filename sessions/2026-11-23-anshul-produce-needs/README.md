# What Anshul's produce distribution business likely needs

Desk memo for topc-social/topc-tasks#347, 2026-11-23. Trigger: Anshul Bhalerao posted on Ideato on 2026-10-24: "We are working as a traditional business of produce distribution and looking for guidance from a person in this industry." Nobody answered for a month.

**Read:** nothing public about his business turned up, so this memo covers what a small family fresh-produce distributor in India commonly struggles with and where help exists. It assumes Maharashtra, which comes from his Marathi surname and is **not confirmed**. Nobody has asked him anything yet, so what he actually needs is still open. The questions at the end are the next step.

## His business: nothing found

Searches for his name with fruit, vegetables, APMC, wholesale, Pune, Nashik and Vashi, plus LinkedIn, found no match. A search tool refused a profile-compiling query, and people-search sites were not used. Family trading firms are usually listed under the firm's or father's name, so the firm name and market yard are what to ask for.

## 1. Common problems

1. **Many hands share the consumer rupee.** Farmers get about 33% (tomato), 36% (onion) and 37% (potato) of the consumer price. The rest goes to wholesalers and retailers. No separate trader margin is given. [RBI WP 08/2024](https://website.rbi.org.in/documents/87730/30842423/WPS+No.+8%2C+2024+-+Vegetables+Inflation+in+India.pdf)
2. **Wastage.** Post-harvest loss is 6.02–15.05% for fruits and 4.87–11.61% for vegetables. Guava loses 15.05%, 3.46% of it at market level. [NABCONS 2022 for MoFPI, via Lok Sabha answer](https://eparlib.sansad.in/bitstream/123456789/3017416/1/AU1976_37fxUw.pdf)
3. **Boom-and-bust prices.** Weak market integration means distress sales in the flush season and spikes in the lean one. The distributor carries that price risk. [RBI press release](https://website.rbi.org.in/web/rbi/-/press-releases/rbi-working-paper-no.-08-/-2024-vegetables-inflation-in-india-a-study-of-tomato-onion-and-potato-top-)
4. **Credit to buyers ties up cash.** Wholesalers gave buyers several days' credit in almost 40% of recent sales. This is Odisha data, not Maharashtra. [CGIAR 2025](https://cgspace.cgiar.org/server/api/core/bitstreams/dd58c49a-8261-4411-adcb-d22547292431/content)
5. **Payments are still mostly cash**, though electronic payments are rising (RBI survey of 10,699 farmers, traders and retailers). [RBI Bulletin](https://website.rbi.org.in/documents/d/rbi/04ar19022025)
6. **APMC rules keep shifting.** Maharashtra delisted fruits and vegetables from APMC control in 2016 and moved the commission to the buyer. A 2020 reform bill was withdrawn after a traders' strike. [ThePrint](https://theprint.in/statedraft/how-indias-most-farmer-friendly-state-failed-to-allow-direct-farmer-to-consumer-sales/157875), [PRS](https://prsindia.org/bills/states/the-farmers-produce-trade-and-commerce-promotion-and-facilitation-maharashtra-amendment-bill-2021)
7. **Quick commerce sources around traditional traders.** Zepto runs 70+ sourcing hubs and its own app that tracks mandi prices and scores vendors. [Indian Television](https://indiantelevision.com/news-headline/zepto-gets-to-the-root-of-fresh-supply-with-farmer-first-new-playbook/)
8. **B2B agritech buyers are unstable.** WayCool laid people off three times in 2023–24. [Entrackr](https://entrackr.com/2024/07/agritech-firm-waycool-lays-off-more-than-200-employees)
9. **Most small businesses still run on paper.** Vyapar's cofounder estimated 80–85% of proprietors keep paper books. The figure is from 2020 and self-reported. [Livemint via IndiaMART](https://corporate.indiamart.com/2020/07/27/an-app-to-turn-the-khata-digital-for-small-businesses-livemint)

## 2. Where help exists

10. **Agriculture Infrastructure Fund:** 3% interest subvention on loans up to ₹2 crore for 7 years, plus a credit guarantee. A Parliament answer says standalone cold storage may not qualify, so check with the lender. [myScheme](https://myscheme.gov.in/schemes/aif)
11. **NHB/MIDH pack house and cold storage:** a 35% credit-linked, back-ended subsidy in general areas. [NHB guideline](https://nhb.gov.in/guideline/113.pdf)
12. **PMFME:** a 35% subsidy up to ₹10 lakh, only if he adds processing such as cut fruit, pulp or dried produce. [PIB](https://pib.gov.in/PressReleasePage.aspx?PRID=2198685)
13. **MAGNET (Maharashtra, with ADB):** covers 14 horticulture value chains. The 2022 call is closed, and MAGNET 2.0's rules aren't published yet. Fraud in MAGNET's name has been reported. [Free Press Journal](https://www.freepressjournal.in/mumbai/maharashtra-to-fast-track-magnet-20-to-boost-farm-market-access-processing-and-exports)
14. **eNAM:** free trader registration and live arrival data, but only 4 Maharashtra mandis were on it as of Dec 2024, all in Jalgaon. [eNAM](https://enam.gov.in/web/stakeholders-Involved/traders)
15. **Incubators:** AIC-ADT Baramati (agri startups, labs; next cohort "coming soon") and ICAR-DOGR Pune's agribusiness incubation centre. [Startup Grants India](https://www.startupgrantsindia.com/hindi/providers/aic-adt-baramati-foundation), [ICAR-DOGR](https://dogr.icar.gov.in/index.php)
16. **AC&ABC (MANAGE/NABARD):** free 45-day training plus a subsidy, only for someone with an agri or allied degree. [myScheme](https://www.myscheme.gov.in/schemes/acandabc)
17. **SFAC equity grant:** not in operation, per SFAC itself. [SFAC](https://sfacindia.com/Equity_grant.aspx)

## 3. Tools that already exist

18. **Credit ledger and billing:** Khatabook (udhaar reminders on WhatsApp) and Vyapar (GST billing). Both are free to start and closed source. [Khatabook explainer](https://miracuves.com/blog/what-is-khatabook-and-how-does-it-work/), [Vyapar](https://vyaparapp.in/invoicing-software)
19. **Stock with expiry, open source:** ERPNext batch-wise inventory. [Frappe docs](https://docs.frappe.io/erpnext/user/manual/en/managing-batch-wise-inventory)
20. **Delivery routes, open source:** VROOM handles vehicle capacity and time windows. It has to be self-hosted. [GitHub](https://github.com/vroom-project/vroom)
21. **WhatsApp ordering:** an early open-source bot, or Take App (hosted). [GitHub](https://github.com/bibinprathap/whatsapp-chatbot), [Take App](https://www.take.app/features/orders)

## 4. How others like him grew

22. **Sahyadri Farms, Nashik:** started as a farmer group in 2011, reached ₹15,489 Mn turnover in FY24, exports to 40+ countries and runs its own stores. [AgroSpectrum](https://agrospectrumindia.com/2024/10/03/sahyadri-farms-achieves-the-turnover-of-rs-15489-mn-in-fy-2023-24.html)
23. **INI Farms (Kimaye), Pune:** an own brand sold in supermarkets and exported to about 35 countries. AgroStar acquired it in 2022. [YourStory](https://yourstory.com/2022/03/agrostar-entry-global-food-supply-chain-ini-farms-acquisition/amp)
24. **JKH Fruits to Frooos, Kerala:** a family wholesaler moving 300–400 t a day, where the son started a retail brand. This is the closest match to a second-generation family trader. [Dhanam](https://english.dhanamonline.com/entrepreneurship/the-frooos-revolution-exotic-fruits-at-prices-everyone-can-afford-2-9000750)
25. **Supplying quick commerce:** Mulyam Agronomics is a sourcing intermediary for 10-minute delivery apps. The profile is company-friendly. [The Strategy Story](https://thestrategystory.com/2026/03/29/mulyam-agronomics-the-company-which-makes-your-10-minutes-fruits-and-vegetable-deliveries-possible-today/)

## Couldn't find

- Typical credit days or default rates for Maharashtra produce traders
- Any data on quick commerce taking volume from Pune or Nashik mandi traders
- Supplier terms for Zepto, Blinkit or Reliance
- Rules for MAGNET 2.0
- Whether MPKV Rahuri has an agribusiness incubator
- A documented Maharashtra family wholesaler that moved into quick commerce

The long PDFs (NABCONS, MAGNET calls) were read through search summaries only. Check the official guideline before acting on any scheme amount.

## Questions to ask Anshul

1. What's the firm called, which market yard is it in, and what produce does it move?
2. What kind of guidance is he after: growing sales, new buyers (modern trade, quick commerce, exports), cash and credit, wastage, or going digital?
3. Who are his buyers today, and how long do they take to pay?
4. Is he the next generation in a family business looking to change how it runs (like Frooos)?
5. What does he keep books and orders in now: paper, WhatsApp, Vyapar?

## Where TOPC could help

- **People:** Ideato and TOPC's community could find him someone who has run a produce or FMCG distribution business. Nobody has been identified yet.
- **Projects:** Kamal's [snap-the-bill shop app](https://www.ideato.social/idea/403047e7-faef-4920-a499-443dbd788d59) idea and the [multi-store stock idea](https://www.ideato.social/idea/bb21dfa0-e425-4769-8891-78586ace21fe) are close, but they're built for retail shops, not distributors. Whether they fit him depends on his answer to question 5.
