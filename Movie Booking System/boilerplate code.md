# Movie Booking System - Boilerplate Code

This repository contains **boilerplate code** for a **Movie Booking System** implemented in three different programming languages: **Java**, **C++**, and **Python**. This code provides the core functionality required for building a movie ticket booking system.


## Code Overview

### 1. **Java**
```java
import java.util.*;

class MovieBookingSystem {
    private static class Movie {
        String name;
        String showtime;
        int seats;

        Movie(String name, String showtime, int seats) {
            this.name = name;
            this.showtime = showtime;
            this.seats = seats;
        }
    }

    private Map<String, Movie> movies = new HashMap<>();

    public void addMovie(String name, String showtime, int seats) {
        movies.put(name, new Movie(name, showtime, seats));
        System.out.println("Movie added successfully.");
    }

    public void bookTicket(String name) {
        Movie movie = movies.get(name);
        if (movie != null && movie.seats > 0) {
            movie.seats--;
            System.out.println("Booking confirmed. Seats Left: " + movie.seats);
        } else {
            System.out.println("Booking failed. No seats available.");
        }
    }

    public void cancelTicket(String name) {
        Movie movie = movies.get(name);
        if (movie != null && movie.seats < 50) {
            movie.seats++;
            System.out.println("Ticket canceled. Seats Left: " + movie.seats);
        } else {
            System.out.println("Cancellation failed. No tickets to cancel.");
        }
    }

    public void viewAvailableShows() {
        for (Movie movie : movies.values()) {
            System.out.println(movie.name + " - Showtime: " + movie.showtime + " - Seats Left: " + movie.seats);
        }
    }

    public void searchMovie(String name) {
        Movie movie = movies.get(name);
        if (movie != null) {
            System.out.println("Movie Found: " + movie.name + " - Showtime: " + movie.showtime + " - Seats Left: " + movie.seats);
        } else {
            System.out.println("Movie not found.");
        }
    }

    public static void main(String[] args) {
        MovieBookingSystem system = new MovieBookingSystem();
        system.addMovie("Inception", "7 PM", 50);
        system.bookTicket("Inception");
        system.viewAvailableShows();
        system.cancelTicket("Inception");
    }
}

```

### 2. **C++**
```c++
#include <iostream>
#include <unordered_map>
#include <string>
using namespace std;

class MovieBookingSystem {
private:
    struct Movie {
        string name;
        string showtime;
        int seats;
    };
    unordered_map<string, Movie> movies;

public:
    void addMovie(string name, string showtime, int seats) {
        movies[name] = {name, showtime, seats};
        cout << "Movie added successfully." << endl;
    }

    void bookTicket(string name) {
        if (movies.find(name) != movies.end() && movies[name].seats > 0) {
            movies[name].seats--;
            cout << "Booking confirmed. Seats Left: " << movies[name].seats << endl;
        } else {
            cout << "Booking failed. No seats available." << endl;
        }
    }

    void cancelTicket(string name) {
        if (movies.find(name) != movies.end() && movies[name].seats < 50) {
            movies[name].seats++;
            cout << "Ticket canceled. Seats Left: " << movies[name].seats << endl;
        } else {
            cout << "Cancellation failed. No tickets to cancel." << endl;
        }
    }

    void viewAvailableShows() {
        for (const auto& pair : movies) {
            const Movie& movie = pair.second;
            cout << movie.name << " - Showtime: " << movie.showtime << " - Seats Left: " << movie.seats << endl;
        }
    }

    void searchMovie(string name) {
        if (movies.find(name) != movies.end()) {
            const Movie& movie = movies[name];
            cout << "Movie Found: " << movie.name << " - Showtime: " << movie.showtime << " - Seats Left: " << movie.seats << endl;
        } else {
            cout << "Movie not found." << endl;
        }
    }
};

int main() {
    MovieBookingSystem system;
    system.addMovie("Inception", "7 PM", 50);
    system.bookTicket("Inception");
    system.viewAvailableShows();
    system.cancelTicket("Inception");

    return 0;
}
```

### 3. **Python**
```python
class MovieBookingSystem:
    class Movie:
        def __init__(self, name, showtime, seats):
            self.name = name
            self.showtime = showtime
            self.seats = seats

    def __init__(self):
        self.movies = {}

    def add_movie(self, name, showtime, seats):
        self.movies[name] = self.Movie(name, showtime, seats)
        print("Movie added successfully.")

    def book_ticket(self, name):
        if name in self.movies and self.movies[name].seats > 0:
            self.movies[name].seats -= 1
            print(f"Booking confirmed. Seats Left: {self.movies[name].seats}")
        else:
            print("Booking failed. No seats available.")

    def cancel_ticket(self, name):
        if name in self.movies and self.movies[name].seats < 50:
            self.movies[name].seats += 1
            print(f"Ticket canceled. Seats Left: {self.movies[name].seats}")
        else:
            print("Cancellation failed. No tickets to cancel.")

    def view_available_shows(self):
        for movie in self.movies.values():
            print(f"{movie.name} - Showtime: {movie.showtime} - Seats Left: {movie.seats}")

    def search_movie(self, name):
        if name in self.movies:
            movie = self.movies[name]
            print(f"Movie Found: {movie.name} - Showtime: {movie.showtime} - Seats Left: {movie.seats}")
        else:
            print("Movie not found.")


if __name__ == "__main__":
    system = MovieBookingSystem()
    system.add_movie("Inception", "7 PM", 50)
    system.book_ticket("Inception")
    system.view_available_shows()
    system.cancel_ticket("Inception")
```
