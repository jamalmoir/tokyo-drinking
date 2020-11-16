# Tokyo Drinking

An app to find places to drink Tokyo when you can't decide where to go, or want to find somewhere new.

---

## Requirements

### To-Do
 1. As a non-registered user, I want to sign up so I can search for and save places to drink.
 2. As a registered user, I want to find drinking places near a location, so that I can find new places to drink.
 3. As a registered user, I want to save and rate places, so that I can look back at and remember places I've been to.
 4. As a registered user, I want to add places that I want to go to, so that I can search for places before hand, and go to them later.
 5. As a registered user, I want to be able to see all the places that I have saved in a list.
 6. As a registered user, I want to choose a buget, so that I can find a drinking place that I can afford.
 7. As a registered user, I want to check and change my registered information to keep it up to date.
 8. As a registered user, I want to edit saved places so that I can update my rating if my experience at the place changes.

### Done
BLANK

---

## API

### Resource: User
```
int id
String email
String username
String password
String displayName
```

#### Endpoints

##### POST /users/
Create a new User.

Allows a user to register to the app.

Stories: 1

##### GET /users/{id}
Get a User by id.

Allows a user to view their registered information.

Stories: 7

##### PUT /users/{id}
Update a User by id.

Allows a user to change their registered information.

Stories: 7


### Resource: Place
```
int id
String name
Double longitude
Double lattitude
String googleMapsRef
```

#### Endpoints

##### GET /places/{id}
Get a Place by id.

Allows a user to view a place's details

Stories: 2

##### GET /places/search
Search for Places.

Allows a user to search for places filtering by certain criteria such as location and budget.

Stories: 2, 6


### Resource: SavedPlace
```
String id
Place place
User user
int rating
int budget
String environment
String description
String notes
boolean anonymous
 ```

#### Endpoints

##### POST /saved-places/
Create a new SavedPlace.

Allows a user to save and rate places. If the place doesn't exist in the places table, it should be created.

Stories: 3, 4, 5

##### GET /saved-places/{id}
Get a SavedPlace by id.

Allows a user to view a saved place.

Stories: 3, 4, 5

##### PUT /saved-places/{id}
Update a SavedPlace by id.

Allows a user to change a rating and details of a place they have saved.

Stories: 8

##### GET /saved-places/search
Search for SavedPlaces.

Allows a user to search for saved places and filter them by certain criteria.

Stories: 2, 5, 6