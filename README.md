<div align="center">

# 🌿 TerraNest

### a simple little dashboard for cities, weather & disasters

*keeping useful city information in one place, without making it complicated.*

<br/>

![Python](https://img.shields.io/badge/Python-16A34A?style=for-the-badge\&logo=python\&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-0EA5E9?style=for-the-badge\&logo=fastapi\&logoColor=white)
![Streamlit](https://img.shields.io/badge/Streamlit-DC2626?style=for-the-badge\&logo=streamlit\&logoColor=white)
![SQLite](https://img.shields.io/badge/SQLite-F59E0B?style=for-the-badge\&logo=sqlite\&logoColor=white)

</div>

---

## 🌱 What is TerraNest?

TerraNest started with a pretty simple idea — what if city information, weather and disaster data could all be checked from the same place?

The project has a **FastAPI backend** that handles the data and APIs, along with a **Streamlit dashboard** where everything can actually be explored.

You can add cities, get their weather, record disasters, filter the data and see it all on an interactive map. Coordinates are looked up automatically, so there's no need to manually enter latitude and longitude every time.

---

## ☁️ What can it do?

### 🏙️ Cities

You can add and manage cities and keep track of things like:

* city and state
* temperature
* humidity
* weather conditions
* latitude and longitude

Cities can also be searched and filtered based on different parameters.

### 🌦️ Weather

Enter a city name and the application takes care of the rest.

It uses the **Open-Meteo API** to find the location and fetch current weather information, including temperature, humidity and conditions.

### 🚨 Disasters

Disaster records can be added with details such as:

* disaster type
* severity
* affected population
* status
* location

The records can then be filtered and managed through the API.

### 🗺️ Map

The map is probably one of my favourite parts of the project.

Cities and disasters are displayed together using **Folium**, with different markers making it easier to get a quick idea of what's happening where.

### 📊 Statistics

There are also separate statistics endpoints and dashboard visualisations for things like city temperatures and disaster data.

---

## 🛠️ Tech used

| Part          | Technology                     |
| ------------- | ------------------------------ |
| Backend       | FastAPI, Uvicorn, Pydantic     |
| Database      | SQLite, SQLAlchemy             |
| Frontend      | Streamlit                      |
| Maps          | Folium, Streamlit-Folium       |
| External APIs | Open-Meteo Weather & Geocoding |
| Testing       | Pytest, FastAPI TestClient     |

---

## 📁 Project structure

```text
terraverse-main/
│
├── app.py
├── database.py
├── models.py
├── validators.py
├── weather_service.py
│
├── routes/
│   ├── city_routes.py
│   └── disaster_routes.py
│
├── frontend/
│   └── streamlit_app.py
│
└── tests/
    └── test_api.py
```

---

## 🚀 Running it locally

Clone the repository and move into the project:

```bash
git clone <repository-url>
cd terraverse-main
```

Create a virtual environment:

```bash
python -m venv venv
```

On Windows PowerShell:

```powershell
.\venv\Scripts\Activate.ps1
```

Install the dependencies:

```bash
pip install -r requirements.txt
pip install streamlit folium streamlit-folium
```

### Start the backend

```bash
uvicorn app:app --reload
```

The API will be running at:

```text
http://127.0.0.1:8000
```

### Start the dashboard

Open another terminal and run:

```bash
streamlit run frontend/streamlit_app.py
```

The FastAPI documentation is also available at:

```text
http://127.0.0.1:8000/docs
```

---

## 🔌 API endpoints

### Cities

```text
POST   /cities
GET    /cities
GET    /cities/{id}
PUT    /cities/{id}
DELETE /cities/{id}
POST   /cities/weather
GET    /cities/statistics
```

### Disasters

```text
POST   /disasters
GET    /disasters
GET    /disasters/{id}
PUT    /disasters/{id}
DELETE /disasters/{id}
GET    /disasters/statistics/summary
```

The `/docs` page contains the complete request and response documentation.

---

## 🧪 Tests

The project uses **Pytest** and FastAPI's `TestClient`.

Run the tests with:

```bash
python -m pytest -q
```

**20 tests passing** ✅

The tests cover the main city and disaster operations, including CRUD, filtering and statistics.

---

## 🌿 Things I'd like to add later

There are a few directions this could go in the future:

* 🔐 Authentication
* 🔮 Disaster risk prediction
* 🔔 Notifications
* ☁️ Cloud deployment

---

## 💌 A little note

This was built as a project to get more comfortable with **FastAPI, databases, APIs and building something that actually has a frontend to interact with**.

There were definitely a few moments of *"why is this not working"* along the way, but that's part of the fun. :)

---

<div align="center">

<img src="https://media.giphy.com/media/3o7TKMt1VVNkHV2PaE/giphy.gif" width="300">

### 🌙 thanks for stopping by!

*made by Thejaswini*

</div>
