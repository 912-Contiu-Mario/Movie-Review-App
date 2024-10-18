# Movie Review App

## Project Overview
The Movie Review App is a mobile application designed for movie enthusiasts who want to keep track of their watched movies and reviews. Users can manage their movie reviews both online and offline, with automatic synchronization when internet connection is restored. This app is built with simplicity in mind, making it easy to use for people without technical background.

## Domain Details

### Movie Review Entity
Each movie review contains the following fields:
- **Title** (String, Required): The name of the movie
- **Release Year** (Integer, Required): Year when the movie was released
- **Rating** (Integer, Required): User rating from 1 to 5 stars
- **Genre** (String, Required): Movie genre category
- **Watch Date** (Date, Required): Date when the user watched the movie
- **Review** (String, Optional): User's written thoughts about the movie
- **ID** (String, Required): Unique identifier for the review
- **Last Modified** (Date, Required): Timestamp of last modification

## CRUD Operations

### Create
- Users can add new movie reviews through a form
- Data is saved both locally and synced to server when online
- Offline: Reviews are stored locally and marked for sync
- Input validation ensures all required fields are filled

### Read
- Main screen displays a list of all movie reviews
- Each review shows title, year, rating, and genre
- Detailed view available for full review information
- Offline: Access to all locally stored reviews

### Update
- Users can edit any field of existing reviews
- Changes are saved locally and synced to server
- Offline: Updates are stored locally and marked for sync
- Modification timestamp is updated automatically

### Delete
- Users can remove reviews from their collection
- Deletion is reflected both locally and on server
- Offline: Marked for deletion and synced when online
- Confirmation required before permanent deletion

## Persistence Details

### Local Database
- All reviews are stored in local device database
- Immediate access to data without internet connection
- Automatic synchronization with server when online
- Conflict resolution based on last modified timestamp

### Server Storage
- Remote backup of all review data
- Synchronization across multiple devices
- Secure data storage and retrieval
- API endpoints for all CRUD operations

### Offline Functionality

#### Creating Reviews Offline
- Reviews can be created normally
- Stored in local database
- Marked for server sync
- Uploaded when connection restored

#### Reading Reviews Offline
- Full access to locally stored reviews
- Cached data available immediately
- Search and filter functionality maintained
- No degradation in read performance

#### Updating Reviews Offline
- Modifications saved to local database
- Changes marked for synchronization
- Conflict resolution on reconnection
- Last modified timestamp tracked

#### Deleting Reviews Offline
- Marked for deletion locally
- Remains in local database until sync
- Removed from server on reconnection
- Can be restored if connection lost during sync
