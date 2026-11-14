# Pingle

A daily geography game played with the speed of light.

A server is hiding somewhere on Earth. You start with ping times from two probe cities. Tap a city on the map to ping the server from there: the reply time tells you how far away the server could be, and a glowing band of dots shows every place that fits. Overlapping bands narrow it down. Ping from the server's own city to win. You get six pings.

## How the clues work

Light in fiber-optic cable travels about 200 km per millisecond, and a ping goes there and back. So a 40 ms reply puts the server at most about 4,000 km away. Real cables don't follow straight lines, so the true distance is usually about 60–80% of that limit. That window is the band drawn on the map.

## Status

Prototype. `index.html` is the whole game: plain HTML, CSS and JavaScript with no build step and no external map data.

- **Ping times are simulated** from the real great-circle distance between cities, with a fixed, per-route detour factor so the same route always gives the same reply.
- **The map** is a dot grid drawn from hand-traced, simplified coastlines included in the source.
- **66 cities** you can ping from, mostly major internet hubs. Everyone gets the same mystery server each day (UTC).

## Roadmap

- [ ] Replace simulated pings with real measurements from public probe networks such as RIPE Atlas or Globalping (check each network's data-use terms first)
- [ ] Streaks and stats across days
- [ ] Hard mode: mystery servers outside the big hubs
- [ ] Pinch-to-zoom on the map for phones

## License

Code is released under the [MIT License](LICENSE).
