# GEOSECURE
Your Money. Your Location. Your Control.

Complete React / JavaScript / HTML / CSS prototype. Includes Tailwind CSS, Lucide icons and Recharts. All dependencies are bundled in the production build; no CDN, bank backend or API key is needed at runtime.

## Run in VS Code (Windows, Mac or Linux)
1. Install Node.js 20.19+ or 22.12+.
2. Extract this ZIP and open the GEOSECURE folder in VS Code.
3. Open Terminal > New Terminal.
4. Run `npm install`.
5. Run `npm run dev`.
6. Open the localhost URL printed by Vite.
If PowerShell blocks npm, use `npm.cmd install` and `npm.cmd run dev`.

## Demo login
Click **Continue with demo account**, or use:
- Email: rahul@geosecure.demo
- Password: Demo@123
Signup stores a salted SHA-256 demo password digest in this browser's localStorage. This is not production authentication. Use fictional details and a disposable password. Signup accounts do not sync between devices. Browser storage is optional for the demo button. Financial state resets on reload.

## Files
- index.html: HTML entry point
- src/main.jsx: all ten React pages and interactive state
- src/styles.css: responsive CSS + Tailwind import
- src/security.js: Haversine distance and transaction decisions
- vite.config.js: build configuration
- package.json / package-lock.json: dependencies and scripts
- dist/: ready-to-host compiled website

## Presentation path (2–3 minutes)
1. Enter demo account, then launch Live Dashboard.
2. Geo-Fence Map > Outside Safe Zone: protected status changes.
3. Secure Transactions: attempt a ₹100 payment to Priya, priya@demobank. Location check rejects it.
4. Travel Mode > 20 km > 6 hours > Activate > confirm simulated approval. One hour equals 15 real seconds for presentation; expiry is automatic.
5. Retry payment: approval reduces the demo balance and adds history.
6. Fraud Attack Simulator > Run: the stolen OTP passes but independent device, location and signature checks block the attempt.
7. Threat Mode > Activate > confirm. All outgoing payments fail, including inside the home zone.
8. Verify identity & restore access to unfreeze (registered-device switch must be on).

## Phone / other laptops
Run `npm run dev` and use the Network URL shown by Vite on devices connected to the same Wi-Fi, allowing the local server through your firewall if needed. Alternatively upload the contents of dist to a static web host. Do not double-click index.html: use an HTTP server. Demo login works in other browsers; custom accounts are local to each browser.

## Build / static hosting
`npm run build` generates dist. Upload the contents of dist to a static host. Relative assets support GitHub Pages subdirectories. `npm run preview` serves a local production preview.

## Security scope
All coordinates, payments, signatures, identities, devices and risk scores are simulated. Admin controls are a demo persona, not role-based access control. Real production integration requires server-side enforcement, hardware-backed cryptographic signatures, anti-spoofing, secure account recovery and security review. This is not proof that all fraud can be prevented.

Risk score = 8 base + 42 outside zone + 35 unverified device + 25 missing approval + 25 amount over ₹50,000, capped at 100. Mandatory failures always reject even below risk threshold. Insufficient balance and Threat Mode always reject. Travel permission extends the initial Home radius of 5 km and is centered on Mohali. Family permissions show eligibility only; no family transfer flow is implemented.

## Verification
Production build passed. Haversine zero-distance and outside-distance cases, successful transaction and mandatory rejection paths were checked. Responsive styles cover phone, tablet and desktop. See delivery notes for browser test coverage.
