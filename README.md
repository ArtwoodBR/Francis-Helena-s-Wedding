# Francis & Helena Wedding Website

A responsive wedding invitation and RSVP website for:

- **Couple:** Francis & Helena
- **Date:** Saturday, 31 October 2026
- **Venue:** Subtle Class Event Centre
- **Colours:** White, gold and burnt orange

## Features

- Interactive envelope opening animation
- Wedding countdown
- Invitation section
- Love story timeline
- Couple photo gallery with lightbox
- Mobile-friendly navigation
- RSVP collection:
  - Full name
  - WhatsApp number
  - Email address
  - Attendance status
  - Number of guests
  - Dietary needs or message
- Supabase database support
- Database fields for assigning and tracking table numbers later

## Open the website in Visual Studio Code

1. Extract the ZIP file.
2. Open the extracted folder in Visual Studio Code.
3. Install the **Live Server** extension.
4. Right-click `index.html`.
5. Select **Open with Live Server**.

## Connect the RSVP form to Supabase

### 1. Create Supabase project

Create a project at Supabase and wait for it to finish setting up.

### 2. Create the RSVP table

1. Open your Supabase dashboard.
2. Go to **SQL Editor**.
3. Open `supabase.sql` from this project.
4. Copy all the SQL.
5. Paste it in the SQL Editor and click **Run**.

### 3. Add Supabase details to the website

In Supabase, go to:

**Project Settings → API**

Copy:

- Project URL
- `anon` / public key

Open `app.js` and replace:

```js
const SUPABASE_URL = "PASTE_YOUR_SUPABASE_URL_HERE";
const SUPABASE_ANON_KEY = "PASTE_YOUR_SUPABASE_ANON_KEY_HERE";
```

Never put your Supabase `service_role` key in this website.

## View and manage RSVPs

In Supabase:

1. Open **Table Editor**.
2. Select the `rsvps` table.
3. View all confirmed guests.
4. Enter each guest's table number in the `table_number` column.
5. Use the `table_number_sent` checkbox to track who has received their table.

You can export the RSVP table as CSV from Supabase.

## Add the couple's photos

Replace these files inside the `assets` folder:

- `hero-couple.svg`
- `couple-1.svg`
- `couple-2.svg`
- `couple-3.svg`
- `couple-4.svg`

You may use `.jpg`, `.jpeg`, `.png`, or `.webp` images instead. If you change a file extension, update its filename in `index.html` and in the relevant gallery button's `data-image` value.

Recommended image sizes:

- Hero: 1800 × 1200 pixels, landscape
- Gallery 1: 1000 × 1400 pixels, portrait
- Gallery 2 and 3: 1000 × 800 pixels
- Gallery 4: 1600 × 900 pixels, landscape

## Edit the love story

Search `index.html` for:

- `The First Hello`
- `Falling in Love`
- `The Yes`

Replace the sample paragraphs with Francis and Helena's real story.

## Change wedding time

The current countdown ends at **12:00 noon Ghana time** on 31 October 2026.

To change it, edit this line in `app.js`:

```js
const WEDDING_DATE = new Date("2026-10-31T12:00:00Z");
```

Ghana uses UTC, so `Z` is correct for Ghana time.

## Publish the website

Easy hosting options:

- Netlify
- Vercel
- GitHub Pages

For Netlify, drag the entire project folder into the Netlify deployment area after connecting Supabase.

## Privacy note

This site collects personal contact information. Keep the Supabase table private, restrict dashboard access, and only use the data for wedding communication.
