# Bollywood Mood Recommender

## Overview

Bollywood Mood Recommender is a voice-activated movie recommendation web application that analyzes user mood through speech input and suggests appropriate Bollywood movies. The system uses browser-native Web Speech API for voice recognition, processes the input through a custom mood detection engine, and returns curated movie recommendations based on the detected emotional state. The application features a modern, responsive interface with animated backgrounds and provides detailed movie information including trailers, ratings, and descriptions.

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

### Frontend Architecture
The frontend uses a modern web stack with Bootstrap 5 for responsive design and vanilla JavaScript for interactivity. The main interface features a microphone button for voice input, animated loading states, and dynamic movie card displays. The application implements the Web Speech API for voice recognition and includes text-to-speech capabilities for enhanced accessibility. CSS animations and gradients create an engaging visual experience with a dark theme optimized for entertainment applications.

### Backend Architecture
The backend is built with Flask following a modular architecture pattern. The main application (`app.py`) handles HTTP routing and request processing, while the mood detection logic is separated into a dedicated `voice_mood` package. This separation allows for easy testing and maintenance of the mood analysis algorithms. The application uses a simple file-based approach for movie data storage with JSON format, making it lightweight and easy to deploy.

### Mood Detection System
The mood detection system consists of two main components: text cleaning utilities and mood extraction algorithms. The system processes voice input through multiple stages - first cleaning and normalizing the text, then matching against predefined mood keyword dictionaries. The mood-to-genre mapping system translates detected emotions into appropriate movie genres, enabling targeted recommendations. The default fallback ensures users always receive suggestions even when mood detection is uncertain.

### Movie Recommendation Engine
The recommendation engine filters the movie database based on detected mood and corresponding genre preferences. Movies are stored with rich metadata including genres, ratings, descriptions, and trailer links. The system supports multiple genres per movie and implements fuzzy matching to improve recommendation accuracy. The filtering algorithm prioritizes genre alignment while maintaining variety in suggestions.

### Data Storage
The application uses a JSON-based file storage system for movie data, located in `data/movies_db.json`. Each movie entry contains comprehensive metadata including title, genres, year, rating, poster URL, description, and trailer link. This approach provides fast read access for recommendations while maintaining simplicity for development and deployment environments.

### Template System
The application uses Jinja2 templating with Bootstrap components for consistent UI rendering. Two main templates handle the application flow: `index.html` for the main interface and `movie_detail.html` for individual movie information. The template system supports dynamic content rendering with proper escaping and includes responsive design elements.

## External Dependencies

### Frontend Libraries
- **Bootstrap 5.3.2**: Provides responsive grid system, components, and utility classes for modern web design
- **Bootstrap Icons 1.10.5**: Icon library for consistent visual elements throughout the interface
- **Google Fonts**: Typography enhancement for improved readability and visual appeal

### Backend Framework
- **Flask**: Lightweight WSGI web application framework providing routing, templating, and request handling
- **Jinja2**: Template engine (included with Flask) for dynamic HTML generation

### Browser APIs
- **Web Speech API**: Browser-native speech recognition for voice input processing
- **Speech Synthesis API**: Text-to-speech functionality for audio feedback and accessibility

### Development Tools
- **Python 3.x**: Core runtime environment for backend processing
- **JSON**: Data serialization format for movie database and API responses

### Media Resources
- **YouTube**: External video hosting for movie trailers embedded via iframe
- **IMDB/External APIs**: Movie poster images and metadata (referenced via URLs)

### Optional Dependencies
- **pyttsx3**: Python text-to-speech library mentioned in project documentation for server-side audio processing (not currently implemented in the active codebase)