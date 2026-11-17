---
description: Find the right SimOptions travel eSIM for a trip
argument-hint: <destinations> [trip length] [data need] [currency]
---

Recommend a SimOptions travel eSIM for this trip: $ARGUMENTS

Follow the `esim-trip` skill:
1. Read the destinations, trip length, data need and currency from the request. If no destination is given, ask for it. If the trip length is missing, ask once.
2. Look up each destination's code with `destinations_search`.
3. Call `plans_find` with all the codes in one call, `minDays` set to the trip length, and `minDataGb` and `currency` if given.
4. Recommend the best one or two plans with their price, validity, data, networks and `pageUrl`, using only what the tools returned.
5. Offer to check the traveller's phone with `devices_check`.
