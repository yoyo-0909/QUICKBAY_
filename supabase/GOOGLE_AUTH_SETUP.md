# Enable Google (Gmail account) sign-in

The frontend calls Supabase Auth `signInWithOAuth({ provider: "google" })`. The Google OAuth credentials must be created by the project owner and entered directly into Supabase. Do not commit the Google Client Secret to GitHub or frontend code.

## 1. Create Google OAuth credentials
1. Open https://console.cloud.google.com/auth/overview
2. Configure the OAuth consent screen (Audience, Branding and Data Access).
3. Ensure the OpenID scopes are enabled: `openid`, `.../auth/userinfo.email`, and `.../auth/userinfo.profile`.
4. Create an OAuth Client ID of type **Web application**.
5. Add your Vercel production origin (for example `https://YOUR-VERCEL-DOMAIN`) to Authorized JavaScript origins.
6. Add this exact Authorized redirect URI:
   `https://zotokdookrbnjfyldizr.supabase.co/auth/v1/callback`
7. Copy the generated Client ID and Client Secret.

## 2. Enable Google in Supabase
Open https://supabase.com/dashboard/project/zotokdookrbnjfyldizr/auth/providers?provider=Google
Enable Google, paste the Client ID and Client Secret, then save.

## 3. Allow Vercel redirects
Open https://supabase.com/dashboard/project/zotokdookrbnjfyldizr/auth/url-configuration
- Set Site URL to the deployed Vercel URL.
- Add `https://YOUR-VERCEL-DOMAIN/**` to the redirect allow list.
- Add any Vercel preview URL pattern you plan to use.
- For local testing, add `http://localhost:8000/**`.

The app redirects back to the same page after Google authentication.

## 4. Verify
Open the deployed site, choose Continue with Google, complete consent, and confirm QuickBay returns to vehicle setup/dashboard. Save a vehicle and create a test booking, then check the Supabase `vehicles` and `bookings` tables.

## Security
The browser contains only the Supabase publishable key. Never put the Supabase service_role key or Google Client Secret in this repository or browser code.
