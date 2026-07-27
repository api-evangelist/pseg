# PSEG (pseg)

Public Service Enterprise Group (PSEG) is a diversified energy holding company headquartered in Newark, New Jersey. Its regulated utility subsidiary Public Service Electric and Gas (PSE&G) is New Jersey's largest electric and gas distribution utility, and PSEG Long Island operates the transmission and distribution system on behalf of the Long Island Power Authority. PSEG sits squarely in the utility-retailer tier of the United States energy value chain — it meters, bills, and serves end customers, and it sells generation into the PJM wholesale market rather than publishing that market's data itself. Its API posture is honestly closed. There is no developer portal: developer., developers., api., docs., and data.pseg.com do not resolve, and /developers, /api, and /docs on pseg.com return the site's soft-404 page. Green Button is present only as a file: PSEG Long Island's MySmartEnergy FAQ states customers can "download data information in CSV or Green Button (.XML) format," which is Download My Data behind a customer login, not Connect My Data. There is no documented programmatic third-party access to customer usage data — in the New Jersey BPU AMI docket PSE&G described manual secondary-user sharing, a Letter of Authorization with spreadsheets emailed back, and EDI for BPU-licensed suppliers. Grid data is equally closed: the PSE&G NJ and PSEG Long Island outage maps are vendor-hosted KUBRA StormCenter applications with no published data API. Open market data for this territory comes from PJM and the EIA, not from PSEG.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/pseg/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/pseg/refs/heads/main/apis.yml)

## Tags

- Energy
- United States
- Utilities
- Electricity
- Gas
- Smart Metering
- Green Button
- Grid
- New Jersey

## Timestamps

- **Created:** 2026-07-27
- **Modified:** 2026-07-27

## APIs

No public APIs are documented by PSEG. See [review.yml](review.yml) for every URL probed and the result.

## Energy Data Posture

- **Home market:** United States (New Jersey via PSE&G; Long Island, New York via PSEG Long Island)
- **Mandate regime:** `green-button-voluntary` — no US federal consumer energy data mandate. The New Jersey BPU's PSE&G AMI proceeding directs Green Button-referenced meter data sharing with non-discriminatory third-party access, which is a state regulatory direction rather than a consumer data right.
- **Mandate status:** `live-claimed-unverified` — Green Button **Download My Data** is documented in PSEG Long Island's public MySmartEnergy FAQ but reachable only after a customer login, so it could not be verified anonymously, and no Green Button Alliance certification listing names PSEG. Green Button **Connect My Data** is verifiably absent.
- **Data standard:** Green Button / NAESB REQ.21 ESPI, Download My Data profile only, as a CSV/XML file export. No version published. Legacy retail-choice EDI for licensed third-party suppliers.
- **Consumer data API:** No. Customer usage data leaves PSEG only as a self-service file download, a view-only secondary user inside MyMeter/MySmartEnergy, a Letter of Authorization answered with emailed spreadsheets, or EDI.
- **Market data open:** No. The PSE&G NJ and PSEG Long Island outage maps are KUBRA StormCenter applications hosted at kubra.io with no documented data API. PJM and the U.S. EIA publish the open data for this footprint.
- **Access gate:** `customer-account-required` — no signup, no keys, no application form, no sandbox. You must be a customer and log in at `nj.myaccount.pseg.com`.
- **Auth model:** Session login only. No OAuth 2.0, no API keys, no mTLS, and no OpenID Connect discovery document served on any probed host.

## Properties

- [Website](https://www.pseg.com/)
- [About](https://corporate.pseg.com/)
- [Blog](https://corporate.pseg.com/newsroom)
- [LinkedIn](https://www.linkedin.com/company/pseg)
- [Login](https://nj.myaccount.pseg.com/user/login)
- [Documentation](https://www.psegliny.com/myaccount/serviceandrates/mysmartenergy) — MySmartEnergy FAQ, the Green Button (.XML) download reference
- [Documentation](https://nj.myaccount.pseg.com/myservicepublic/smartmeters) — PSE&G NJ smart meters and MyMeter

## Maintainers

- Kin Lane — kin@apievangelist.com
