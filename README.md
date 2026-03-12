# WeatherAlert-Monitor

A research project documenting severe weather alerts and monitoring methodologies.

## Current California Weather Alerts

**Active Alerts Count:** 3

1. **Heat Advisory** (Severity: Moderate)
   - **Areas:** San Diego County Coastal Areas; San Bernardino and Riverside County Valleys-The Inland Empire; San Diego County Inland Valleys; Orange County Coastal; Orange County Inland

2. **Heat Advisory** (Severity: Moderate)
   - **Areas:** San Luis Obispo County Beaches; San Luis Obispo County Inland Central Coast; Santa Lucia Mountains; Santa Barbara County Central Coast Beaches; Santa Barbara County Inland Central Coast; Santa Ynez Valley; Santa Barbara County Southwestern Coast; Santa Barbara County Southeastern Coast; Santa Ynez Mountains Western Range; Santa Ynez Mountains Eastern Range

3. **Heat Advisory** (Severity: Moderate)
   - **Areas:** Santa Clarita Valley; Ventura County Beaches; Ventura County Inland Coast; Lake Casitas; Ojai Valley; Central Ventura County Valleys; Malibu Coast; Los Angeles County Beaches; Palos Verdes Hills; Los Angeles County Inland Coast including Downtown Los Angeles; Western Santa Monica Mountains Recreational Area; Eastern Santa Monica Mountains Recreational Area; Calabasas and Agoura Hills; Western San Fernando Valley; Eastern San Fernando Valley; Southeastern Ventura County Valleys; Santa Susana Mountains; Los Angeles County San Gabriel Valley

## NWS API Reference

- **Base URL:** `https://api.weather.gov`
- **Alert endpoint:** `GET /alerts/active?area={state}` (e.g., `https://api.weather.gov/alerts/active?area=CA`)
- **Response format:** JSON‑LD / GeoJSON `AlertCollection` containing a `features` array. Each feature includes:
  - `id` – unique alert identifier
  - `properties.event` – alert title (e.g., "Heat Advisory")
  - `properties.severity` – severity level (e.g., Moderate, Severe)
  - `properties.areaDesc` – human‑readable list of affected areas
  - `properties.effective`, `onset`, `expires`, `ends`
  - Additional CAP fields such as `certainty`, `urgency`, `instruction`.
- **Headers:** `User-Agent` required; optional `Accept` to request specific formats (e.g., `application/geo+json`).
- **Other useful endpoints:** `/points/{lat},{lon}` for location metadata, `/gridpoints/{office}/{x},{y}/forecast` for forecasts.
