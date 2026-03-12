# Spotify Clone

A Spotify-inspired Android music player application built with Kotlin and Jetpack Compose. Users can browse album sections, view playlists, play songs with a built-in audio player, and favorite albums for offline access.

## Tech Stack

| Layer | Technology |
|-------|------------|
| Language | Kotlin |
| UI | Jetpack Compose + XML (hybrid) |
| Architecture | MVVM (ViewModel + StateFlow + Repository) |
| DI | Dagger Hilt |
| Networking | Retrofit 2 + Gson + OkHttp |
| Database | Room (SQLite) |
| Image Loading | Coil |
| Audio | ExoPlayer 2.18.2 |
| Navigation | Jetpack Navigation (Safe Args) |
| Build | Gradle, AGP 7.4.2, Kotlin 1.7.0 |

## Features

- **Home Feed** — Browse curated album sections ("Top mixes", "Made for you", "This Is: K-Music") fetched from the backend `/feed` endpoint.
- **Playlist View** — Tap into an album to see its songs, fetched from `/playlist/{id}`.
- **Music Player** — Persistent player bar at the bottom with play/pause, seek, and progress tracking powered by ExoPlayer.
- **Favorites** — Favorite/unfavorite albums stored locally in Room with reactive `Flow` updates.

## Project Structure

```
app/src/main/java/com/laioffer/spotify/
├── MainActivity.kt              # Entry point, bottom nav + player bar
├── MainApplication.kt           # Hilt application
├── database/                    # Room DB, DAO, Hilt module
├── datamodel/                   # Album, Song, Playlist, Section
├── network/                     # Retrofit API interface + Hilt module
├── player/                      # PlayerBar (Compose), PlayerViewModel, ExoPlayer module
├── repository/                  # HomeRepository, PlaylistRepository, FavoriteAlbumRepository
└── ui/
    ├── home/                    # HomeFragment, HomeScreen, HomeViewModel
    ├── playlist/                # PlaylistFragment, PlaylistScreen, PlaylistViewModel
    ├── favorite/                # FavoriteFragment, FavoriteScreen, FavoriteViewModel
    └── theme/                   # Compose theme
```

## Getting Started

### Prerequisites

- Android Studio (Arctic Fox or later)
- Android SDK 33+
- JDK 11+

### Run

1. Clone the repository.
2. Start the [spotify_backend](https://github.com/xiao4Ricardo/spotify_backend) server.
3. Open the project in Android Studio.
4. Run on an emulator (the app connects to `http://10.0.2.2:8080/` by default).

## Backend

This app requires the companion [spotify_backend](https://github.com/xiao4Ricardo/spotify_backend) server to serve music feed data and audio files.

## License

This project is for educational purposes.
