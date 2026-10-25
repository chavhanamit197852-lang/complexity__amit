# EventVerse

EventVerse is a responsive event discovery and community engagement prototype. It helps people discover events around Mumbai, register for experiences, save events, and explore organizer and admin workflows.

The project is intentionally built as a lightweight browser prototype with no authentication or database requirement.

## Features

- Premium dark startup-style interface
- Responsive desktop, tablet, and mobile layouts
- Event search and filtering
- Category browsing
- Mumbai-based location display
- IIT Bombay, Powai Google Maps preview
- Nearby event discovery
- College showcase carousel with:
  - IIT Bombay
  - IIT Roorkee
  - COEP Pune
  - VJTI Mumbai
  - Walchand College of Engineering
- Event detail pages
- Demo registration flow
- Save/bookmark events
- User portal
- Organizer dashboard
- Create-event workflow
- Admin approval queue
- Community dashboard
- LocalStorage persistence
- Smooth scroll animations
- Floating hero preview animation
- Reduced-motion accessibility support

## Project Structure

```text
eventverse/
├── index.html
├── app.js
├── styles.css
└── assets/
```

### Main files

- `index.html` — application shell and CDN library imports
- `app.js` — seeded data, routing, rendering, state, demo flows, and interactions
- `styles.css` — responsive visual system and animations
- `assets/` — local image assets

## Running Locally

This prototype does not require a build step or package installation.

### Option 1: Open directly

Open `index.html` in a browser.

### Option 2: Use a local server

From the project directory, run one of the following:

```powershell
python -m http.server 5500
```

Then open:

```text
http://localhost:5500
```

Using a local server is recommended because browser security policies can restrict some remote embeds when opening files directly.

## Demo Routes

| Route | Purpose |
|---|---|
| `/` | Landing page and featured discovery |
| `/discover` | Event discovery and search |
| `/categories` | Category browsing |
| `/nearby` | Nearby events and IIT Bombay map |
| `/community` | Community activity dashboard |
| `/events/:id` | Event detail page |
| `/user` | User portal |
| `/organizer` | Organizer dashboard |
| `/organizer/events/create` | Create an event |
| `/admin` | Admin approval dashboard |

Routes are implemented with hash navigation, so the browser URLs use forms such as:

```text
http://localhost:5500/#/discover
```

## Demo Flow

1. Open the landing page.
2. Click **Discover** in the navbar.
3. Search for an event or choose a category.
4. Open an event and click **Register now**.
5. Open **Demo portals**.
6. Enter the organizer portal.
7. Create an event.
8. Open the admin portal.
9. Approve the pending event.
10. Return to discovery to see the approved event.

## Data and Persistence

Seeded event data is stored in memory on first load. User interactions are persisted in browser `localStorage`:

- `ev-events`
- `ev-reg`
- `ev-saved`

To reset the demo state, clear the site's localStorage in browser developer tools and reload the page.

## UI Libraries

The prototype loads these libraries from CDNs:

- Tailwind CSS
- AOS for scroll-triggered animations
- Lucide for icon support

The core application remains dependency-free and can still be opened without a build tool.

## Location Behavior

The visible demo location is:

```text
Mumbai, Maharashtra
```

The nearby map is centered on:

```text
IIT Bombay, Powai, Mumbai
```

The map uses a Google Maps embed and does not require an API key for the prototype preview.

## Validation

Validate the application JavaScript with:

```powershell
node --check .\app.js
```

