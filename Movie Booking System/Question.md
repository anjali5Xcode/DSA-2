# Movie Booking System  

## Problem Statement  
Design and implement a **Movie Booking System** with the following functionalities:  

1. **Add Movie**:  
   Add a movie with details like its name, showtime, and number of available seats.  

2. **Book Ticket**:  
   Book a ticket for a specific movie and showtime, reducing the seat count.  

3. **Cancel Ticket**:  
   Cancel a ticket for a specific movie and showtime, releasing the seat.  

4. **View Available Shows**:  
   Display a list of all movies, their showtimes, and available seats.  

5. **Search Movie by Name**:  
   Search for a movie by its title and display its details if found.  

---

## Concepts Used  
- **Hash Maps**: For efficient storage and retrieval of movie details.  
- **Arrays**: To manage seating arrangements.  
- **String Matching**: For the movie search functionality.  

---

## Features and Example Workflows  

### 1. Add Movie  
**Functionality:** Add a new movie with its name, showtime, and available seats.  

```java
// Code
system.addMovie("Inception", "7 PM", 50);

// Output
Movie added successfully.
```

### 2. Book Ticket
**Functionality:** Book a ticket for a specific movie and showtime, reducing the available seat count.

```java
// Code
system.bookTicket("Inception");

// Output (if seats are available)
Booking confirmed. Seats Left: 49

// Output (if no seats are available)
Booking failed. No seats available.
```

### 3. Cancel Ticket
**Functionality:** Cancel a ticket for a specific movie and showtime, increasing the available seat count.
```java
// Code
system.cancelTicket("Inception");

// Output (if ticket cancellation is valid)
Ticket canceled. Seats Left: 50

// Output (if no tickets are booked)
Cancellation failed. No tickets to cancel.

```
### 4. View Available Shows
**Functionality:** Display all movies with their showtimes and available seats.

```java
// Code
system.viewAvailableShows();

// Output
"Inception" - Showtime: 7 PM - Seats Left: 49
"Titanic" - Showtime: 6 PM - Seats Left: 30

```
### 5. Search Movie by Name
**Functionality:** Search for a movie by its title and display its details if found.

```java
// Code
system.searchMovie("Inception");

// Output (if movie is found)
Movie Found:
"Inception" - Showtime: 7 PM - Seats Left: 49

// Output (if movie is not found)
Movie not found.

```