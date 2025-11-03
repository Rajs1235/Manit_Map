 # 🗺️ MANIT Campus GIS - React Frontend

This is an interactive GIS web application built for the MANIT (Maulana Azad National Institute of Technology) Bhopal campus. It allows students, faculty, and visitors to explore the campus, get detailed information about buildings, and use navigation features.

This project is built using React, Mapbox GL JS, and Tailwind CSS.

Live Demo: https://bobbymanitmap.netlify.app/

# ✨ Features
🗺️ Interactive GIS Map: A fully functional map built with Mapbox GL JS, supporting pan, zoom, and rotate.

# LAYER Multiple Map Layers:** Users can switch between different map layers:

MANIT Layer: Custom GIS data (buildings, hostels, departments).

Satellite Layer: High-resolution satellite imagery.

Custom Layer: An alternative custom base map.

# 🖱️ GIS Data Interaction:
🚀 Navigation & Directions: Uses @mapbox/mapbox-gl-directions for turn-by-turn navigation, similar to Google Maps.

📍 "Navigate from My Location": A button that allows users to start navigation directly from their current location.

🔵 User Geolocation: Uses the browser's navigator.geolocation API to display the user's live location as a blue dot on the map.

🔍 Search: A search box powered by @mapbox/search-js-react that uses the Mapbox Geocoding API to find any location worldwide.

🚀 Double-clicking on any campus building opens a popup with its details (Photo, Warden/HOD name, contact, area, etc.).

🏞️ Static Info Pages: Displays static images exported from ArcGIS, such as a Contour Map and a Land Use Land Cover (LULC) Map.

🔒 Secure Authentication: Includes Login and SignUp pages to connect to the backend API.

# 💡 Architecture: ArcGIS + Mapbox + React
The process for handling GIS data in this project is unique:

🚀 Data Creation (ArcGIS): All spatial data for the campus (building polygons, road lines, points of interest) was created in ArcGIS Pro.

🚀 Data Export (ArcGIS): This data was exported from ArcGIS into Shapefile or GeoJSON formats.

🚀 Data Hosting (Mapbox Studio): These exported files were uploaded to Mapbox Studio as a "Tileset" (a data layer).

🚀 Styling (Mapbox Studio): A new "Map Style" was created. This style uses "Satellite" as the base layer and adds the uploaded MANIT data tileset (manitlanddatamark-3rdbdl) on top, with custom styling (e.g., coloring buildings red).

🚀 Loading (React): This React app uses the mapbox-gl-js library to load that specific Style URL (mapbox://styles/...) directly.

🚀 Interaction (React): Using functions like map.on("dblclick", ...) and map.queryRenderedFeatures(...), the app interacts with Mapbox and reads the properties of the (now hosted) ArcGIS data.

# 🛠️ Tech Stack
Frontend: React (Hooks)

Routing: React Router DOM

Mapping: Mapbox GL JS, @mapbox/search-js-react, @mapbox/mapbox-gl-directions

Styling: Tailwind CSS

# 🚀 How to Run (Local Development)
Clone the Repository:

Bash

git clone https://github.com/your-username/your-repo.git
cd your-repo/frontend
Install Dependencies:

Bash

npm install
Create an Environment File:

Create a .env file in the project's root folder.

Add your Mapbox Access Token to it:

REACT_APP_MAPBOX_TOKEN="pk.eyJ1..."
(Note: Your token is currently hardcoded; moving it to .env is the best practice.)

Start the App:

Bash

npm start
Your project will start on http://localhost:3000 (or 5173 if you are using Vite).

# 👥 Project Team

Team Members:
Bobydayal Saket (B.Tech 3rd Year)

Raj Srivastava (B.Tech 3rd Year)

Swati Jalandhara (B.Tech 3rd Year)
