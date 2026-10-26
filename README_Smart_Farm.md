# AgriTwin — AI Smart Farming Assistant

An Android app that helps farmers make smarter irrigation decisions using satellite crop-health data, weather forecasts and AI. Built for **WHACK Hackathon 4.0** by Team TendToZero (theme: *Integrated Smart Irrigation & Crop Disease Prediction System*).

---

## Features

- **Farm digital twin** — satellite-based map view of the farm with location, boundaries and crop-health overlay (Google Maps)
- **AI irrigation recommendations** — uses NDVI crop-health data, weather and evapotranspiration to suggest when and how much to irrigate
- **Weather monitoring** — temperature, humidity, wind, rainfall and forecast from OpenWeather
- **Plant disease detection** — on-device TensorFlow Lite model that analyses a crop photo and returns the disease, severity and treatment advice
- **Farming chatbot** — Gemini-powered assistant for irrigation and crop-health questions
- **Irrigation control** — Auto, Manual and Scheduled modes with zone, water volume and duration settings
- **Rainwater transfer** — module for tracking and transferring harvested rainwater
- **Insights dashboard** — crop health, stress and risk indicators in one place
- **Hindi and English** language support

---

## Tech Stack

| Area | Technology |
|---|---|
| Language | Kotlin |
| UI | Jetpack Compose, Material 3, Navigation Compose |
| AI / ML | TensorFlow Lite (plant disease model), Gemini API |
| Satellite data | Sentinel Hub API (NDVI) |
| Weather | OpenWeather API |
| Maps | Google Maps SDK / Maps Compose |
| Networking | Retrofit, OkHttp, Gson, Kotlin Coroutines |
| Storage / images | DataStore, Coil |

---

## Project Structure

```
Smart_farm-master/
├── app/src/main/
│   ├── java/com/example/agritwin/
│   │   ├── ai/            # AI engine, Gemini chatbot, plant disease model service
│   │   ├── network/       # Sentinel Hub and OpenWeather API services
│   │   ├── navigation/    # App navigation
│   │   └── ui/            # Screens, dialogs and theme
│   └── assets/plant_disease_model.tflite
├── SMARTFARM- TendToZero(2)- Final submission.pptx   # Hackathon presentation
└── build.gradle
```

---

## Setup

### Prerequisites

- Android Studio (latest stable)
- Android SDK 36, minimum supported Android version 7.0 (API 24)

### Steps

1. Clone the repository

```bash
git clone https://github.com/TusharSharmaji/Smart_Farm.git
```

2. Open the `Smart_farm-master` folder in Android Studio and let Gradle sync.

3. Create the file `app/src/main/java/com/example/agritwin/config/ApiKeys.kt` with your own keys:

```kotlin
package com.example.agritwin.config

object ApiKeys {
    const val GEMINI_API_KEY = "YOUR_GEMINI_API_KEY"
    const val OPENWEATHER_API_KEY = "YOUR_OPENWEATHER_API_KEY"
    const val SENTINEL_CLIENT_ID = "YOUR_SENTINEL_HUB_CLIENT_ID"
    const val SENTINEL_CLIENT_SECRET = "YOUR_SENTINEL_HUB_CLIENT_SECRET"
    const val DEFAULT_FARM_NAME = "My Farm"
    const val DEFAULT_LATITUDE = 26.9124
    const val DEFAULT_LONGITUDE = 75.7873
    const val DEMO_MODE_ENABLED = false
}
```

4. Add your Google Maps API key in `app/src/main/AndroidManifest.xml` under the `com.google.android.geo.API_KEY` meta-data entry.

5. Run the app on an emulator or an Android device.

> Never commit real API keys. Keep `ApiKeys.kt` out of version control.

---

## Team

Team **TendToZero** — WHACK Hackathon 4.0

## Author

**Tushar Sharma** — [GitHub](https://github.com/TusharSharmaji) · [LinkedIn](https://linkedin.com/in/tushar-sharma-16oct2004)
