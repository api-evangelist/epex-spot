# EPEX SPOT (epex-spot)

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

EPEX SPOT SE, the European Power Exchange, operates the organised short-term electricity markets across thirteen European countries - day-ahead and intraday auctions on the MATS trading system and continuous intraday trading on the M7 trading system. Day-ahead prices set on EPEX SPOT are the reference for much of the European power sector.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/epex-spot/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/epex-spot/refs/heads/main/apis.yml)

## Access Model (Read This First)

EPEX SPOT has real machine-readable interfaces, but **no open self-serve developer API**. Everything is gated one of two ways:

- **Trading APIs (MATS and M7)** require exchange membership. MATS is the Multiple Auction Trading System (successor to ETS) covering all day-ahead and intraday auctions, with REST-based order submission and results retrieval (CSV/XML/JSON). M7 runs the continuous intraday markets and is accessed over AMQP, typically through software from EPEX SPOT's [ISV list](https://www.epexspot.com/en/software-providers). Full API specifications are distributed only to members and ISVs.
- **Market Data Services** are paid subscriptions ordered through the [EEX Group Webshop](https://webshop.eex-group.com/epex-spot-public-market-data): read-only APIs (Day-Ahead and pan-EU Intraday API Read-only at EUR 1,040/month; Continuous API Read-only at EUR 3,360/month) and SFTP/webshare file packages (CSV/Excel, end-of-day and historical). Webshop prices cover internal usage within one legal entity; external usage (display, redistribution, indexation) is quoted individually by marketdata.sales@epexspot.com.

Because endpoint documentation sits behind those gates, this entry does not model or fabricate an endpoint surface - the APIs listed in `apis.yml` are the real, named interfaces, marked `endpointsModeled` with no invented paths.

**Free alternatives for day-ahead prices:** EPEX SPOT publishes browsable (not API) market results at [epexspot.com/en/market-results](https://www.epexspot.com/en/market-results), and EPEX day-ahead prices for most bidding zones are freely available through the ENTSO-E Transparency Platform RESTful API.

## Tags

- Day-Ahead Prices
- Electricity
- Energy Markets
- Power Exchange
- Intraday Trading
- Market Data
- Auctions
- Europe

## Timestamps

- **Created:** 2026-07-11
- **Modified:** 2026-07-11

## APIs

### EPEX SPOT Day-Ahead and Intraday Auction Market Data API

Read-only API subscription (Day-Ahead and pan-EU Intraday API Read-only, EUR 1,040.00/month for internal usage) delivering day-ahead and intraday auction results - prices and volumes - for all market areas where EPEX SPOT operates, sourced from the MATS auction trading system. Subscription-gated; endpoints documented to subscribers only.

- **Human URL:** [https://www.epexspot.com/en/marketdataservices](https://www.epexspot.com/en/marketdataservices)

#### Tags

- Day-Ahead Prices
- Auctions
- Market Results

#### Properties

- [Documentation](https://www.epexspot.com/en/marketdataservices)
- [Pricing](https://webshop.eex-group.com/epex-spot-public-market-data)

### EPEX SPOT Continuous Intraday Market Data API

Read-only API subscription (Continuous API Read-only, EUR 3,360.00/month for internal usage) giving real-time access to production data - all trades and orders - on the continuous intraday market operated on the M7 trading system. Subscription-gated; endpoints documented to subscribers only.

- **Human URL:** [https://www.epexspot.com/en/marketdataservices](https://www.epexspot.com/en/marketdataservices)

#### Tags

- Intraday Trading
- Trades
- Order Book

#### Properties

- [Documentation](https://www.epexspot.com/en/marketdataservices)
- [Pricing](https://webshop.eex-group.com/epex-spot-public-market-data)

### EPEX SPOT MATS Auction Trading API

Member trading API for the Multiple Auction Trading System (MATS), the platform that replaced the legacy ETS system for all EPEX SPOT auction markets. Supports linear, block, scalable complex, and Future-To-Spot orders, plus market results retrieval over REST - market result reports (CSV), trade reports (XML), and aggregated and individual order results (JSON). Requires exchange membership.

- **Human URL:** [https://www.epexspot.com/en/technology](https://www.epexspot.com/en/technology)

#### Tags

- Auctions
- Trading
- Order Management

#### Properties

- [Documentation](https://www.epexspot.com/en/technology)
- [API Reference (MATS API Introduction, PDF)](https://www.epexspot.com/sites/default/files/download_center_files/MATS%20API%20Introduction%20v1.0%20-%20Light%20Package.pdf)

### EPEX SPOT M7 Intraday Trading API

Member trading API for the M7 trading system that runs all EPEX SPOT continuous intraday markets. Clients exchange standardized messages with M7 over an AMQP server - the interface behind the large majority of automated intraday order flow on the exchange and the integration point for listed ISVs. Requires exchange membership.

- **Human URL:** [https://www.epexspot.com/en/technology](https://www.epexspot.com/en/technology)

#### Tags

- Intraday Trading
- AMQP
- Algorithmic Trading

#### Properties

- [Documentation](https://www.epexspot.com/en/technology)
- [Partners (ISV list)](https://www.epexspot.com/en/software-providers)

## Common Properties

- [LinkedIn](https://www.linkedin.com/company/epex-spot)
- [Website](https://www.epexspot.com)
- [Documentation](https://www.epexspot.com/en/marketdataservices)
- [Downloads](https://www.epexspot.com/en/downloads)
- [Market Results](https://www.epexspot.com/en/market-results)
- [Pricing](https://webshop.eex-group.com/epex-spot-public-market-data)
- [Plans](plans/epex-spot-plans-pricing.yml)
- [Blog](https://www.epexspot.com/en/news)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
