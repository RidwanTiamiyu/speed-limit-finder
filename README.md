# Speed Limit Finder

A single-file web tool that shows speed-limit signs seen in street imagery and compares them with OpenStreetMap and your own GIS speed layer. Red rings mark signs that disagree with the road data, so you can check them in Google Street View.

## How to use
1. Get a free client token: register an app at mapillary.com/dashboard/developers (READ scope only) and copy the Client Token (starts with `MLY|`).
2. Open the page and paste the token. It is stored only in your browser.
3. Type `lat,lng` (or an address) in **Go to**, zoom in to about 1 to 2 miles across, and click **Load signs and roads in view**.
4. Optional: upload a GeoJSON (WGS84) of your GIS speed lines and pick the speed attribute.
5. Click a sign for its Street View link. Use **Export all signs (CSV)** to save results.

## What it does
- Pulls `regulatory--maximum-speed-limit-*` map features from the Mapillary API v4.
- Pulls road lines with a `maxspeed` tag from OpenStreetMap (Overpass).
- Matches each sign to the nearest road line within the match radius and flags mismatches.

## Limits
- Only works where Mapillary has street imagery, and detections can be wrong.
- Signs are field evidence, not legal truth. In NC the legal limit comes from ordinances.
- Not tested against every road type or at scale. Verify before relying on a result.

## Credits and terms
Sign data © Mapillary (see [Mapillary Terms](https://mapillary.com/legal)). Road data © OpenStreetMap contributors. Background map tiles from OpenStreetMap.
Use of the Mapillary API is subject to their terms, including developer and commercial-use sections. No license has been added to this repository yet.
