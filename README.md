# Pingle

A daily geography game played with the speed of light.

A server is hiding somewhere on Earth. You start with ping times from two probe cities. Tap a city on the map to ping the server from there: the reply time tells you how far away the server could be, and a glowing band of dots shows every place that fits. Overlapping bands narrow it down. Ping from the server's own city to win. You get six pings.

## How the clues work

Light in fiber-optic cable travels about 200 km per millisecond, and a ping goes there and back. So a 40 ms reply puts the server at most about 4,000 km away. Real cables don't follow straight lines, so the true distance is usually about 60–80% of that limit. That window is the band drawn on the map.

## Modes

- **Daily:** the server hides in one of 66 big internet hubs. Everyone gets the same server each day (UTC).
- **Hard:** the server hides in one of about 95 smaller cities, and you can ping from all 161 cities. It's also daily and shared.
- **Practice:** a random server every round. It doesn't count toward your stats.

Pick a mode with the tabs or link to it directly: `#daily`, `#hard`, `#practice`.

## Features

- **Pan and zoom:** drag to pan, pinch or use the +/− buttons to zoom. Ctrl-scroll and trackpad pinch work on desktop. City names appear once you zoom in far enough.
- **Hints:** the side panel counts how many cities still fit every ping, and highlights them in the city list.
- **Stats and streaks:** kept separately for Daily and Hard. They show games played, find rate, current and best streak, and how many pings each win took.
- **Share:** copy an emoji grid of your game.

## How it's built

`index.html` is the whole game: plain HTML, CSS and JavaScript with no build step, no external map data and no backend. Progress and stats stay in your browser's `localStorage`.

- **Ping times are simulated** from the real great-circle distance between cities, with a fixed, per-route detour factor so the same route always gives the same reply.
- **The map** is a dot grid drawn from hand-traced, simplified coastlines included in the source.

## Roadmap

- [x] Streaks and stats across days
- [x] Hard mode: mystery servers outside the big hubs
- [x] Pinch-to-zoom on the map for phones
- [x] Practice mode
- [ ] Replace simulated pings with real measurements from public probe networks such as RIPE Atlas or Globalping (check each network's data-use terms first)

## License

Code is released under the [MIT License](LICENSE).
