<div align="center">

# 🌍 TerraWatch

### a cozy little city & disaster watchtower ☁️🕯️

*live weather, disaster tracking, and a soft interactive map — all in one gentle dashboard*

<br/>

![Python](https://img.shields.io/badge/Python-16A34A?style=for-the-badge&logo=python&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-0EA5E9?style=for-the-badge&logo=fastapi&logoColor=white)
![Streamlit](https://img.shields.io/badge/Streamlit-DC2626?style=for-the-badge&logo=streamlit&logoColor=white)
![SQLite](https://img.shields.io/badge/SQLite-F59E0B?style=for-the-badge&logo=sqlite&logoColor=white)

![Made with love](https://img.shields.io/badge/made%20with-%F0%9F%A4%8D%20love-ff69b4?style=flat-square)
![Tests](https://img.shields.io/badge/tests-20%20passing-brightgreen?style=flat-square&logo=pytest&logoColor=white)
![Status](https://img.shields.io/badge/status-cozy%20%26%20active-blueviolet?style=flat-square)
![PRs Welcome](https://img.shields.io/badge/PRs-welcome-orange?style=flat-square)

</div>

---

## 🫖 What is this?

TerraWatch is a little home for scattered information — the kind you'd otherwise have to hunt down across five different tabs. One place for **city weather**, one place for **disaster tracking**, and a **map** that ties it all together, warmly.

No need to look up coordinates yourself either — TerraWatch quietly figures those out for you in the background. ✨

---

## 🌤️ What it does

- 🏙️ **Track cities** — add, search, filter by state or temperature, and keep tabs on the ones you care about
- ☁️ **Pull live weather** — just type a city name, TerraWatch fetches temperature, humidity & conditions from Open-Meteo
- 🚨 **Log disasters** — type, severity, affected population, status — filterable and easy to scan
- 📍 **Auto-geolocation** — no manual lat/long typing, ever
- 🗺️ **Interactive map** — blue pins for cities, color-coded pins for disasters by severity
- 📊 **Analytics dashboard** — gentle little charts for temperature spread, disaster types, and more

---

## 🧸 Tech stack

| Layer | Tools |
|---|---|
| Backend | FastAPI · Uvicorn · Pydantic |
| Database | SQLite + SQLAlchemy |
| Frontend | Streamlit · Folium |
| External data | Open-Meteo Weather & Geocoding APIs |
| Testing | Pytest · FastAPI TestClient |

---

## 📁 Project structure

```text
City_information_project/
├── app.py                     # FastAPI entry point
├── database.py
├── models.py
├── validators.py
├── weather_service.py
├── routes/
│   ├── city_routes.py
│   └── disaster_routes.py
├── frontend/
│   └── streamlit_app.py
└── tests/
    └── test_api.py
```

---

## 🚀 Getting started

```bash
# clone & enter
git clone <repository-url>
cd City_information_project

# set up a cozy little virtual environment
python -m venv venv
.\venv\Scripts\Activate.ps1     # Windows PowerShell

# install everything
pip install -r requirements.txt
pip install streamlit folium streamlit-folium
```

Then, in two terminals:

```bash
# terminal 1 — backend
uvicorn app:app --reload
# → http://127.0.0.1:8000

# terminal 2 — frontend
streamlit run frontend/streamlit_app.py
```

Interactive API docs live at `http://127.0.0.1:8000/docs` 📖

---

## 🔌 API at a glance

**Cities**
```http
POST   /cities              # add a city (coordinates resolved automatically)
GET    /cities               ?state=  &min_temperature=
GET    /cities/{id}
PUT    /cities/{id}
DELETE /cities/{id}
POST   /cities/weather      # create a city from just a name — live weather included
GET    /cities/statistics
```

**Disasters**
```http
POST   /disasters           # coordinates resolved automatically too
GET    /disasters            ?state=  &disaster_type=  &severity=  &status=
GET    /disasters/{id}
PUT    /disasters/{id}
DELETE /disasters/{id}
GET    /disasters/statistics/summary
```

Full field lists, request/response examples, and error codes are all documented live in the `/docs` Swagger UI — no need to duplicate them here. 🍃

---

## ✅ Testing

```bash
python -m pytest -q
```

20 tests, all passing, covering CRUD, filtering, and statistics for both cities and disasters.

---

## 🌱 Roadmap

- 🔐 Authentication
- 🔮 Risk prediction
- 🔔 Notifications
- ☁️ Cloud deployment

---

## 💌 Author

Made with warm hands and a lot of tea by **Thejaswini** 🕊️

---

<div align="center">

### 🐾 thanks for stopping by

![cute cat gif](https://media.giphy.com/media/JIX9t2j0ZTN9S/giphy.gif)

*monitor gently, respond kindly* 🌙

</div>
