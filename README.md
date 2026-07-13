# 🍃 Windfall

Windfall is a community-maintained map for tracking neighborhood fruit trees — log where trees are, what kind of fruit they produce, and when they're likely to be ready to pick. Predictions combine each tree's own logged history with local weather data (growing-degree-days) to estimate ripening windows, and anyone with the link can add trees, photos, and ripeness check-ins.

## Features

- Interactive map (Leaflet + OpenStreetMap) with fruit-shaped, color-coded pins that simplify to dots and clusters as you zoom out
- Ripeness check-ins (flowering / not yet / ready / past peak) that build a season-by-season history per tree
- Weather-informed harvest predictions using growing-degree-day accumulation
- Climacteric vs. non-climacteric picking guidance per fruit type
- Photo storage per tree (tree + fruit close-up)
- Shared, multi-user data via Supabase (Postgres + Storage)

## Tech stack

- Static HTML/CSS/JS (no build step)
- [Leaflet](https://leafletjs.com/) + [Leaflet.markercluster](https://github.com/Leaflet/Leaflet.markercluster) for the map
- [Supabase](https://supabase.com/) for the database and photo storage
- [Open-Meteo](https://open-meteo.com/) for weather data and geocoding
- Hosted on [Netlify](https://www.netlify.com/)

## Setup

1. Create a free [Supabase](https://supabase.com/) project.
2. Run the SQL in `supabase-schema.sql` (or your own equivalent) to create the `trees` table and storage policies.
3. Update `SUPABASE_URL` and `SUPABASE_ANON_KEY` near the top of the `<script>` block in `index.html` with your own project's values (the anon key is designed to be public — access is controlled by Row Level Security policies, not by hiding this key).
4. Deploy `index.html` to Netlify (or any static host).

## Contributing

Issues and pull requests are welcome. Please read the [Code of Conduct](./CODE_OF_CONDUCT.md) before participating.

## License

Released under the [MIT License](./LICENSE).

---

This site is powered by [Netlify](https://www.netlify.com).
