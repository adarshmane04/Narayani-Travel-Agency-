# Narayani Travel Agency Website

A single-page travel agency website with tour packages, an interactive India map, an enquiry form, a staff login and a client dashboard. It is one HTML file with no build step.

## What is in this folder

| File | Purpose |
| --- | --- |
| `index.html` | The whole website (HTML, CSS and JavaScript) |
| `README.md` | This guide |

## How to open it

1. Unzip the folder.
2. Double-click `index.html`. It opens in your browser.

An internet connection is needed only to load the fonts. Without it the site still works with fallback fonts.

## What the site contains

- **Home:** hero section, a "Plan a trip" form, nine sample tour packages with a category filter, "Who we travel with", and contact details.
- **Map:** an India map with a pin for every destination. Select a pin to see the trip, the best months and an "Open in Google Maps" link.
- **Enquiry form:** builds a ready-to-send message with a Copy button. If you add a WhatsApp number it also shows a "Send on WhatsApp" button. Nothing is sent automatically.
- **Staff login:** go to `index.html#login`, or use the "Staff login" button at the top.
- **Client dashboard:** add clients, search, filter by status, change status, delete, and see upcoming trips.

## Staff login details

Default sign-in:

- Username: `admin`
- Password: `narayani123`

Change both in the `CONFIG` block (see below). This login only locks the dashboard screen. Anyone who opens the file can read the password in the code, so it is not real security. For real protection you need a server with proper user accounts.

## Make it yours

Open `index.html` in a text editor such as Notepad or VS Code and search for `EDIT THESE`. You will find two blocks.

### 1. CONFIG

```js
const CONFIG = {
  agency: 'Narayani Travel Agency',
  phone: '+91 98XXX XXXXX',
  whatsapp: '',            // digits with country code, for example 919812345678
  email: 'hello@narayani-travels.example',
  address: 'Office address, City, State, PIN',
  staffUser: 'admin',
  staffPass: 'narayani123'
};
```

Replace the phone, email and address with your real details. Fill in `whatsapp` to show the WhatsApp button.

### 2. PACKAGES

Each package is one line like this:

```js
{id:'goa', name:'Goa Beach Break', cat:'beach', nights:3, price:14500,
 place:'Goa', lon:73.95, lat:15.45, lab:'l', best:'Nov to Feb', gq:'Goa, India',
 hl:['North and South Goa beaches','Old Goa churches','Sunset river cruise']}
```

| Field | Meaning |
| --- | --- |
| `id` | Short unique name, no spaces |
| `name` | Package title |
| `cat` | `hills`, `beach`, `heritage` or `pilgrim` |
| `nights` | Number of nights (days are nights + 1) |
| `price` | Price per person in rupees |
| `place` | Label shown next to the map pin |
| `lon`, `lat` | Position of the pin on the map |
| `lab` | `'l'` puts the pin label on the left, `'r'` on the right |
| `best` | Best months to travel |
| `gq` | Text used for the Google Maps link |
| `hl` | Three highlights shown on the card |

Copy a line, change the values, and a new package and map pin appear. The packages, prices, phone number, email and address that come with the site are samples. Replace them before you publish.

## How client data is stored

When you open `index.html` from your computer, the dashboard saves clients in your browser (local storage). That means:

- Data stays on that one computer and browser.
- Clearing browser data erases it.
- Other staff members cannot see it.

The version published on claude.ai can share client data live with the people you add as editors. That live sharing does not work from this zip.

To share data between staff from your own website, you need a small backend with a database. Ask Claude to add one.

## Putting it online

Upload `index.html` to any static host, for example Netlify Drop, GitHub Pages or your own hosting plan. Then point your domain at it.

## Limits to know about

- The staff login is a screen lock only, as explained above.
- Enquiries are not stored or emailed. Visitors send them through WhatsApp or by copying the message.
- Map pins use a simplified India outline, so positions are approximate.
