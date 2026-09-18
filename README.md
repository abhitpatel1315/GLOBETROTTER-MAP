# GLOBETROTTER-MAP
PERSONALISED TRAVEL PLANNER 


| API / Service                 | Used for                                                                   | Free?                    |
| ----------------------------- | -------------------------------------------------------------------------- | ------------------------ |
| **OpenStreetMap**             | Map tiles / displaying the map                                             | ✅ Yes                    |
| **Leaflet.js**                | Interactive map functionality                                              | ✅ Open source            |
| **Wikipedia API**             | Finding famous places around a searched city + article information         | ✅ Yes                    |
| **Wikimedia Commons API**     | Getting photos for tourist places                                          | ✅ Yes                    |
| **Nominatim (OpenStreetMap)** | Finding the coordinates of cities that aren't already in the city database | ✅ Yes, with usage limits |


1. OpenStreetMap

Used for the actual map:

https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png

It provides the map background.

2. Leaflet.js

Used to create the interactive map:

https://unpkg.com/leaflet@1.9.4/dist/leaflet.js

It handles markers, zooming, popups, map movement, etc.

3. Wikipedia API

This is the important one for city searches.

For example:

Ahmedabad

The code gets Ahmedabad's coordinates and asks Wikipedia for nearby pages/places using:

generator=geosearch

So it can find places around a city dynamically.

4. Wikimedia Commons API

Used to find photos for places such as:

Taj Mahal
Gateway of India
Statue of Unity
Hawa Mahal

The code searches Wikimedia Commons for an image.

5. Nominatim API

This is used when you search a city that isn't already in my built-in city list.

For example:

Rajahmundry

Nominatim finds its latitude/longitude, then the code sends those coordinates to Wikipedia to find nearby famous places.

Overall flow
User searches
     ↓
Is it a State/UT?
     ↓
YES → Built-in state tourist places
     ↓
NO
     ↓
Is it a known City?
     ↓
YES → City coordinates → Wikipedia API → Famous places
     ↓
NO
     ↓
Nominatim → Find city coordinates
     ↓
Wikipedia API → Find nearby famous places
     ↓
Wikimedia Commons → Get photos
     ↓
Leaflet + OpenStreetMap → Show everything on map

So you don't need an API key for these APIs/services in this particular dem
