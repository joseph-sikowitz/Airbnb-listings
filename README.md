# AirBNB Listings

A page that loads the first 50 San Francisco Airbnb listings from a local JSON
snapshot using `fetch()` and `await`, and displays them as cards.

## Live Demo

🔗 [View the deployed site](https://yourusername.github.io/airbnb-listings/)

_(update this link once GitHub Pages is live)_

## Features

- Fetches listing data using `fetch()` and `async/await`
- Displays for each listing: name, description, host name + photo,
  price, thumbnail, and top amenities
- Handles broken/missing images with a fallback placeholder
- **Creative addition — Compare tray:** select up to 3 listings using the
  "Compare" button on each card. A tray slides up from the bottom of the
  page showing the selected listings side-by-side, highlighting the
  lowest price and highest rating, and calling out which amenities each
  listing has that none of the others do.

## Data quirks worth knowing

The raw dataset stores a couple of fields in ways that aren't immediately
usable:

- `price` is a string like `"$187.00"`, not a number — it gets stripped
  down to a plain number before any comparisons happen.
- `amenities` is a JSON-encoded string (e.g. `'["Wifi","Kitchen"]'`), not
  an actual array, so it needs `JSON.parse()` before it can be looped over.
- `name` has extra info packed in after `·` characters (rating, bedroom
  count, etc.) — only the first segment is used for the card title.

## Tech

- HTML, CSS, vanilla JavaScript
- Bootstrap 5 for layout/styling

## Data Source

Based on Airbnb San Francisco listings data (`airbnb_sf_listings_500.json`),
provided for this class assignment.
