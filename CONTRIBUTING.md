# Contributing to QuickBay

Thanks for helping improve QuickBay.

## Before you start

- QuickBay is currently a test website, not a production workshop marketplace.
- Keep the existing customer-facing features working when changing the interface.
- Do not present OpenStreetMap directory results as verified or approved partners.
- Keep secrets, OAuth client secrets, service-role keys and private tokens out of source control.

## Suggested workflow

1. Create a feature branch from `main`.
2. Make a focused change and keep the mobile layout in mind.
3. Test the affected flow in a browser, including relevant error and permission states.
4. Check that maps, location access, centre actions, booking navigation and authentication are not unintentionally broken.
5. Open a pull request with a concise summary, screenshots for UI changes and manual test notes.

## Code and UI guidelines

- The current app is a static HTML/CSS/JavaScript project with `index.html` as its entry point.
- Prefer small, readable changes over introducing a framework without a clear need.
- Preserve accessibility: semantic controls, visible focus states and clear labels.
- Be explicit about prototype or simulated functionality.
- Avoid adding dependencies unless they materially improve the product.

## Reporting a bug

Include the browser/device, steps to reproduce, expected result, actual result and screenshots or console errors when available.
