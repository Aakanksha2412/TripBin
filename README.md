# TripBin

TripBin is a travel itinerary planner built with Flutter and Firebase. It helps you plan trips, track budgets and bookings, search flights, and share travel moments in a social feed.

## Features

- **Sign up and log in** with email and password (Firebase Authentication)
- **Create trips** with destination, dates and budget
- **Home dashboard** listing all your saved trips
- **Itineraries** to view trip details
- **Budget tracker** for each trip
- **Hotel bookings** with check-in and check-out dates
- **Flight search** by departure city, arrival city and dates (Aviationstack API)
- **Explore** destinations with city search and place details
- **Travel feed** to post photos and comment on posts
- **Profile page** with user details and profile picture

## Tech Stack

| Area | Tools |
|------|-------|
| Framework | Flutter (Dart SDK 3.5+) |
| State management | Provider |
| Authentication | Firebase Auth |
| Database | Cloud Firestore, Firebase Realtime Database |
| Maps and location | Google Maps Flutter, Google Places, Geolocator |
| Networking | http, Dio |
| Media | camera, image_picker, flutter_image_compress |
| Local storage | shared_preferences, flutter_secure_storage |
| Data loading | excel (city list from `.xlsx`) |

## Project Structure

```
tripbin_app/
├── lib/
│   ├── main.dart            # App entry point and routes
│   ├── models/              # Trip, City and User models
│   ├── providers/           # Trip state (Provider)
│   ├── services/            # Auth, Trip, City and Excel loader services
│   ├── views/               # All app screens
│   ├── assets/              # Logo, city data, default images
│   └── images/              # Destination images
├── android/
├── ios/
└── pubspec.yaml
```

## Firestore Collections

| Collection | Purpose |
|------------|---------|
| `users` | User profiles |
| `trips` | Trips created by users |
| `cities` | City data for search |
| `posts` | Feed posts |
| `comments` | Comments on posts |

## Getting Started

### Prerequisites

- Flutter SDK 3.5 or later
- A Firebase project
- FlutterFire CLI: `dart pub global activate flutterfire_cli`
- An Aviationstack API key (free tier at aviationstack.com) for flight search

### Setup

1. Clone the repo:
   ```bash
   git clone https://github.com/Aakanksha2412/TripBin.git
   cd TripBin/tripbin_app
   ```
2. Install packages:
   ```bash
   flutter pub get
   ```
3. Connect your Firebase project. This creates `lib/firebase_options.dart`:
   ```bash
   flutterfire configure
   ```
4. In the Firebase console, turn on **Email/Password** sign-in and create a **Cloud Firestore** database.
5. Add your Aviationstack API key in `lib/views/flights_page.dart`.
6. Run the app:
   ```bash
   flutter run
   ```

## Security Note

The Firebase config in `lib/firebase_options.dart` contains client API keys. These identify the Firebase project and are not secret by design. Data is protected by Firebase Authentication and Firestore Security Rules.

## Author

**Aakanksha**
GitHub: [Aakanksha2412](https://github.com/Aakanksha2412)
