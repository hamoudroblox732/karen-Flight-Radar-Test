# Karen Flight Radar Test

A standalone test project for reading live aircraft telemetry from the PTFS community 24data relay.

## Current scope

- Main server and Event server data endpoints.
- REST polling and documented main-server SSE stream.
- Search by aircraft type or callsign.
- Aircraft details: player name, type, heading, altitude, speed, ground state, and X/Y coordinates.
- A coordinate test radar that plots available X/Y positions.

## Important limitation

The radar currently plots PTFS world X/Y coordinates in a relative test view. It is **not yet calibrated to the original PTFS map**. A verified world-to-map transform and a suitable map asset are required before aircraft can be drawn at their true positions on that map.

The relay exposes the main and event data feeds. A private Roblox server invite URL does not, by itself, select that exact server in the relay. The test therefore offers only the relay's documented Main and Event feeds.

## Run

Open `index.html` in a browser, select Main or Event, and press **اتصال**.

Default relay:
`https://ws.awdevhardware.org`

Documented endpoints:
- `GET /acft-data`
- `GET /acft-data/event`
- `GET /sse/acft-data` (main server)
- `GET /health`

If browser requests are blocked by CORS, the page will report the connection error. Do not put private keys or credentials in this frontend.

## Publish with GitHub Pages

In the repository, open **Settings → Pages**, choose **Deploy from a branch**, select **main** and **/(root)**, then save. GitHub Pages may take a few minutes to publish.

## Sources

- [24data Relay API documentation](https://ws.awdevhardware.org/)
- [PTFSFlightPlanner live-data adapter](https://github.com/DayzdRB/PTFSFlightPlanner/blob/main/js/live-data-adapter.js)

Unofficial community tool for Roblox PTFS only. Not for real-world flight operations.
