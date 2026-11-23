# QuickBay

Mobile-first automotive service discovery and bay-reservation test website.

## Stack
- Static HTML/CSS/browser JavaScript
- Supabase Auth with Google OAuth
- Supabase Postgres for customer profiles, vehicles and booking requests
- OpenStreetMap Overpass for mapped service-centre discovery
- Leaflet maps

## Deploy
Connect this repository to Vercel as a static site. The root entry point is `index.html`; no build command is required.

## Supabase
The connected QuickBay Supabase project already contains `profiles`, `vehicles`, `bookings`, `workshops`, bays, services and job-card tables. This site reuses the existing tables and RLS policies. Only the Supabase URL and publishable key are included in browser code. Never expose a service-role or secret key.

## Google sign-in
The UI uses Supabase Auth Google OAuth. The project owner must enable the Google provider with OAuth Web Client ID and Client Secret in Supabase Dashboard. Follow [supabase/GOOGLE_AUTH_SETUP.md](supabase/GOOGLE_AUTH_SETUP.md).

## Test-mode notes
- The legacy 4-digit OTP flow is only a demo profile path, not real SMS/email OTP.
- UPI/payment actions remain simulated; no payment gateway is connected.
- OpenStreetMap listings may lack phone, rating or hours and are not automatically QuickBay-approved partners.
- External OSM selections are stored in booking notes; they are not inserted into the canonical workshop directory.
