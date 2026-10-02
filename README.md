# event-discovery-v1

A **local event discovery** React component that aggregates nearby events (concerts, workshops, meetups) and displays them as cards sorted by distance from the user.

> **Built by Girish Lade** — https://ladestack.in

## Features

- **Location-based sorting** — uses the browser Geolocation API to sort events by distance (Haversine formula) from the user's current position; falls back to NYC coordinates if location access is denied.
- **Save to calendar** — generates a downloadable `.ics` calendar event (2-hour duration) for any event via a single click.
- **Offline caching** — fetched events are cached in `localStorage` so the UI renders instantly on repeat visits.
- **Responsive card layout** — event cards with name, date, venue, distance, and action buttons.

## Tech stack

- React (hooks: `useState`, `useEffect`)
- shadcn/ui-style `Card` / `Button` components
- `lucide-react` icons (`Calendar`, `MapPin`, `Clock`)
- Tailwind CSS utility classes

## Quick start

1. Copy `event-discovery` into your React project (rename to `event-discovery.jsx`).
2. Make sure `react`, `lucide-react`, and your shadcn `Card`/`Button` components are installed.
3. Fix the imports to match your project layout:
   ```js
   import { Card, CardContent, CardFooter, CardHeader, CardTitle } from "@/components/ui/card"
   import { Button } from "@/components/ui/button"
   ```
4. Render it:
   ```jsx
   import EventDiscovery from "./event-discovery"
   export default function App() { return <EventDiscovery /> }
   ```

## API integration

The component ships with **mock event data** (comment: `// Mock event data that would normally come from Ticketmaster API`). To go live, replace the mocked fetch with the [Ticketmaster Discovery API](https://developer.ticketmaster.com/products-and-docs/apis/discovery-api/v2/) and map the response to the existing event shape.

## Project structure

```
.
├── event-discovery      # the EventDiscovery React component (main file)
├── LICENSE              # license
└── README.md
```

## Deploy notes

This repo is a reusable component snippet, not a standalone website — there is no build step and no deployment target. Drop it into any React + Tailwind project and it works.

## License

See [LICENSE](./LICENSE).
