# Blood+Bank

A blood donation management web app built with Node.js and Express. It includes public accounts, donor registration and search, a blood bank locator, contact queries, and an admin dashboard.

## Requirements

- Node.js 18 or newer
- npm

## Run locally

1. Install dependencies:

   ```sh
   npm install
   ```

2. Create a local `.env` file by copying `.env.example`. Set `ADMIN_USERNAME` and `ADMIN_PASSWORD` to your own credentials. Keep `.env` private; it is excluded from Git.

3. Start the app:

   ```sh
   npm start
   ```

4. Open [http://127.0.0.1:3000](http://127.0.0.1:3000).

The server uses port `3000` by default. Set the `PORT` environment variable to use another port.

## Public features

- Create a public account, log in, and view or edit the profile.
- Donor registration is optional; an account does not require donor registration.
- Search donors by blood group.
- Use the locator and allow browser location access to search for nearby blood banks.
- Submit contact queries.

## Admin login

Set the admin username and password in your private local `.env` file, then log in at [http://127.0.0.1:3000/admin/login](http://127.0.0.1:3000/admin/login). Public users create their own accounts through the signup page.

## Demo data and storage

The app starts with sample donors and contact queries in memory. Registrations made through the public signup form are saved to `users.json` and survive server restarts. Donor and contact form data currently lives in memory and resets when the Node.js server restarts. The SQL file under `sql/` is from the original project and is not currently connected to the Node.js app.

## Project structure

- `server.js` — Express routes and application logic
- `public/styles.css` — frontend styles
- `image/` — project images served by the app
- `users.json` — locally saved public accounts, created when accounts are registered or edited
- `sql/` — original MySQL schema and sample data

## Notes

The locator embeds Google Maps search results. Browser location access works on `localhost` and requires the visitor to grant permission.
