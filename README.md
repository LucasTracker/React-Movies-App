# Movie Search App

This React application allows users to search for movies and displays trending movies. It utilizes the TMDB API for movie data and Appwrite for storing and retrieving trending movie data.

## Features

*   **Movie Search:** Search for movies by title using the search bar.
*   **Debounced Search:** Prevents excessive API calls by delaying the search until the user finishes typing.
*   **Trending Movies:** Displays a list of trending movies fetched from Appwrite.
*   **Loading State:** Shows a spinner while movie data is being fetched.
*   **Error Handling:** Displays error messages if the API request fails.
*   **Movie Cards:** Displays movie information in a card format, including title and poster.

## Technologies Used

*   **React:** JavaScript library for building user interfaces.
*   **react-use:** Provides useful React hooks, including `useDebounce`.
*   **Appwrite:** Backend-as-a-service for storing and retrieving trending movie data.
*   **TMDB API:** The Movie Database API for fetching movie information.

## Installation

1.  Clone the repository:

    ```bash
    git clone [https://github.com/YOUR_USERNAME/YOUR_REPOSITORY_NAME.git](https://www.google.com/search?q=https://github.com/YOUR_USERNAME/YOUR_REPOSITORY_NAME.git)
    ```

2.  Navigate to the project directory:

    ```bash
    cd movie-search-app
    ```

3.  Install dependencies:

    ```bash
    npm install
    ```

4.  Set up environment variables:

    *   Create a `.env` file in the root directory.
    *   Add your TMDB API key:

        ```
        VITE_TMDB_API_KEY=YOUR_TMDB_API_KEY
        VITE_APPWRITE_PROJECT_ID = YOUR_PROJECT_ID
        VITE_APPWRITE_DATABASE_ID YOUR_DATABASE_ID
        VITE_APPWRITE_COLLECTION_ID = YOUR_COLLECTION_ID
        ```

    *   Set up Appwrite and add the necessary environment variables for connecting to your Appwrite database.  You'll need to configure a database and collection within Appwrite to store your trending movies.  The code expects a `poster_url` and `title` field (and an `$id` field which Appwrite automatically adds) in the documents of your Appwrite collection.

5.  Start the development server:

    ```bash
    npm run dev
    ```

## Usage

1.  Open the application in your browser.
2.  Use the search bar to search for movies.
3.  The results will be displayed below the search bar.
4.  The "Trending Movies" section displays trending movies fetched from Appwrite.

## Code Structure

*   `src/App.jsx`: The main component that handles state, API calls, and rendering.
*   `src/components/Search.jsx`: Component for the search bar.
*   `src/components/Spinner.jsx`: Component for the loading spinner.
*   `src/components/MovieCard.jsx`: Component for displaying movie information.
*   `src/appwrite.js`: Contains functions for interacting with the Appwrite backend.

## API Calls

*   **TMDB API:**
    *   `GET /search/movie?query={query}`: Searches for movies based on the query.
    *   `GET /discover/movie?sort_by=popularity.desc`: Fetches popular movies (used as a fallback if no search term).
*   **Appwrite:**
    *   `getTrendingMovies()`: Fetches trending movies from the Appwrite database.
    *   `updateSearchCount(query, movie)`: Updates the search count for a given movie (this function is currently called but its implementation details are not fully shown in the provided code snippet).

## Notes

*   Ensure that you have a valid TMDB API key.
*   Configure the Appwrite connection and database/collection correctly.
*   The `updateSearchCount` function's implementation is not fully provided in the original code, so you'll need to fill in the Appwrite logic for that.  It appears it is intended to track movie search counts.
*   This README provides a basic overview of the application.  More detailed information can be added as needed.

This improved README provides a more comprehensive guide to the application, including installation instructions, usage details, code structure, and API calls.  It also highlights key aspects of the code and any missing or assumed details.
