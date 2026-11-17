---
name: esim-trip
description: Plan mobile data for a trip with SimOptions travel eSIMs. Use when someone asks which eSIM, data plan or roaming option to get for a trip, compares eSIM plans for one or more countries, or asks whether their phone supports eSIM.
---

# Plan a trip's mobile data with SimOptions

Use the SimOptions tools (`destinations_search`, `plans_find`, `devices_check`) to recommend a travel eSIM from live data. Every fact you state about a plan (price, data, validity, networks, 5G, calls, SMS, top-ups) comes from a tool result in this conversation. Never guess or fill in a value the tools did not return.

## 1. Know the trip

You need the destinations and the trip length. If either is missing, ask once, briefly. Also useful, but don't insist on them:
- how much data they expect to use (light browsing and maps, social media, video and hotspot)
- whether they need calls or SMS, or a local phone number
- their currency

## 2. Find the destination codes

Call `destinations_search` for each place the traveller names, then pass the returned `code` values to `plans_find`. Never type a code from memory: the United Kingdom is `GB`, not `UK`, and regions have their own codes. A country with no page of its own is answered with the regional destinations that cover it.

## 3. Find plans

Call `plans_find` with every destination of the trip in one call. With several codes, it returns only plans that cover all of them, which is usually what a multi-country traveller wants.

- Set `minDays` to the trip length.
- Set `minDataGb` only when the traveller gave a data need. Unlimited plans always qualify.
- Set `currency` when the traveller uses one.

If nothing matches, relax one filter at a time (data first, then days) and say what you changed.

## 4. Recommend

- Lead with one or two plans that fit, not the whole list. Say why each fits: validity against the trip length, data against their use.
- Mention what matters for the trip: 5G, calls or SMS and a phone number if they asked, and whether the eSIM can be topped up if they might run out.
- If plans differ in cost, show the cheapest that fits and the next step up.
- Give each recommended plan's `pageUrl`, where it is bought. Do not build or guess other links.

## 5. Check the phone

If the traveller hasn't confirmed that their phone supports eSIM, offer to check it with `devices_check`. A `"yes"` names the listed model. `"unknown"` is not a no: the list only holds compatible models, so suggest checking the phone's settings for an eSIM option.

## Keep it honest

- Prices are those returned for the requested currency at the time of the call and may change on the site.
- Purchases, activation and support happen on simoptions.com. These tools only read the catalogue.
