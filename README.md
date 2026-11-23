![QuickBay — Smarter Workshops. Better Service.](assets/quickbay-banner.svg)

<div align="center">

# QuickBay

### Smarter workshops. Better service.

A mobile-first automotive service discovery and bay-reservation **test platform** built to make finding a service centre and requesting a workshop bay simpler.

[**Open the live test site**](https://quickbay-underscore.vercel.app) · [Repository](https://github.com/yoyo-0909/QUICKBAY_) · [Google sign-in setup](supabase/GOOGLE_AUTH_SETUP.md)

</div>

---

## What QuickBay is

QuickBay is an early-stage test website for discovering nearby automotive service centres, viewing centre details, requesting a service bay and managing basic customer and vehicle information. The current pilot is centred around **Tiruvallur, Tamil Nadu**.

> **Project status:** Prototype / test deployment. Directory results sourced from OpenStreetMap are not automatically verified or approved QuickBay partners. Some flows are simulated; see [current limitations](#current-test-mode-limitations).

## Product highlights

| Area | What is included |
| --- | --- |
| Service discovery | Nearby service-centre discovery using map data and location access |
| Map experience | Leaflet map with OpenStreetMap-based centre markers |
| Centre actions | Call links when a phone number is available and directions through Google Maps |
| Bay requests | Customer-facing bay booking/request flow |
| Customer account | Supabase Auth integration, with Google OAuth setup required |
| Customer vehicles | Vehicle information can be saved to the connected Supabase database |
| Booking records | Authenticated booking requests can be stored in Supabase |
| Mobile-first UI | Responsive single-page experience designed for phone screens |

## Technology

- **Frontend:** HTML, CSS and browser JavaScript
- **Maps:** Leaflet
- **Map data:** OpenStreetMap / Overpass
- **Authentication:** Supabase Auth (Google OAuth)
- **Database:** Supabase Postgres
- **Hosting:** Vercel
- **Source control:** GitHub

## Live environment

| Resource | Link |
| --- | --- |
| Test website | https://quickbay-underscore.vercel.app |
| GitHub repository | https://github.com/yoyo-0909/QUICKBAY_ |
| Vercel project | https://vercel.com/yoyo-0909/quickbay-underscore |
| Supabase project | https://supabase.com/dashboard/project/zotokdookrbnjfyldizr |

The `main` branch is connected to Vercel. Pushing a commit to `main` triggers a deployment. The site is a static frontend, so no build command is required.

## Run locally

1. Clone the repository:

   ```bash
   git clone https://github.com/yoyo-0909/QUICKBAY_.git
   cd QUICKBAY_
   ```

2. Open `index.html` in a browser, or serve the folder with any static file server.

   Example:

   ```bash
   python -m http.server 8000
   ```

3. Visit `http://localhost:8000`.

Location access works best on HTTPS or localhost. Some browser features may be restricted when opening the file directly.

## Supabase configuration

The frontend is connected to the existing QuickBay Supabase project. The browser uses the project's URL and **publishable** key; never put a service-role key or other secret in frontend code.

### Google sign-in

Google sign-in requires a Google OAuth Web Client ID and Client Secret configured in the Supabase Dashboard. Follow the step-by-step instructions in [`supabase/GOOGLE_AUTH_SETUP.md`](supabase/GOOGLE_AUTH_SETUP.md).

Supabase callback URL:

```text
https://zotokdookrbnjfyldizr.supabase.co/auth/v1/callback
```

Live site origin:

```text
https://quickbay-underscore.vercel.app
```

Do not commit OAuth client secrets, service-role keys, access tokens or private credentials.

## Current test-mode limitations

- The legacy four-digit OTP path is a demo flow, not a real SMS or email OTP service.
- Payment / UPI actions are simulated; no live payment gateway is connected.
- OpenStreetMap directory results can be incomplete and may not include phone numbers, ratings or opening hours.
- Map results are not automatically approved QuickBay workshop partners.
- External map-directory selections are recorded as booking metadata; they are not treated as canonical workshop records.
- Google sign-in will only work after the OAuth provider credentials and redirect settings are completed in Supabase.

## Repository structure

```text
.
├── .gitignore
├── assets/
│   └── quickbay-banner.svg
├── CONTRIBUTING.md
├── index.html
├── README.md
├── SECURITY.md
└── supabase/
    └── GOOGLE_AUTH_SETUP.md
```

## Development notes

- Keep the root `index.html` as the Vercel entry point unless the deployment configuration is intentionally changed.
- Preserve the existing customer-facing flows when making UI changes.
- Treat external map listings separately from approved workshop records.
- Test location permissions, map loading, authentication redirects and booking persistence before calling a feature production-ready.

## Contributing and security

- Read [CONTRIBUTING.md](CONTRIBUTING.md) before proposing changes.
- Read [SECURITY.md](SECURITY.md) for safe vulnerability reporting and credential-handling guidance.
- Never commit OAuth client secrets, Supabase service-role keys or private tokens.

## Roadmap

- Complete and verify Google OAuth end-to-end.
- Validate workshop listings and introduce an approval workflow.
- Expand pilot coverage beyond the initial Tiruvallur area using reliable workshop records.
- Improve booking status visibility and workshop-side workflows.
- Replace simulated payment actions only after selecting and integrating a real payment provider.

---

<div align="center">

**QuickBay** · Built as a test platform for a better automotive service experience.

</div>
