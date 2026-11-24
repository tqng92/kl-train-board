# kl-train-board

Next train arrivals for **Merdeka** (MRT Kajang Line) and **Plaza Rakyat** (LRT Sri Petaling + Ampang Lines, ~7 min walk from Merdeka), Kuala Lumpur.

Single static page — no build step, no dependencies. Fetches Rapid KL's journey-planner backend (`jp-web.myrapid.com.my/endpoint/geoservice`, the API behind the official journey planner) directly from the browser, refreshes every minute, and ticks countdowns locally every second.

## Notes

- Times are generated from the official timetable (headway tables anchored to the first train of the day), **not live train positions**. Accurate to a couple of minutes in normal service; unreliable during disruptions.
- The Putrajaya Line also calls at Merdeka, but the API has no stop data for it there — board at Tun Razak Exchange instead.
- Service is roughly 06:00–24:00; outside that window boards show "no more trains today".

## Run locally

```sh
python -m http.server 8123   # from this folder
# open http://127.0.0.1:8123
```
