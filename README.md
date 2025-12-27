
# Flight Reservation System

A web application for managing flight reservations, built as a project for Applied Software Engineering course.

## 📋 Project Overview

This application simulates an online flight reservation system with three user roles: Guest (Unauthenticated), Registered User (Passenger), and Administrator. The system handles flights, reservations, airlines, and reviews with full CRUD operations.

## 🚀 Technologies Used

- **Backend**: ASP.NET Web API 2 (REST API)
- **Frontend**: HTML5, CSS3, JavaScript, jQuery, Bootstrap 5.3.3
- **Data Storage**: JSON files (persistent text-based storage)
- **Architecture**: RESTful API with AJAX calls
- **Session Management**: ASP.NET Session State

## ✨ Key Features

### For All Users (Guest & Registered)
- **Home Page**: View all active flights with airline information
- **Search & Filter**: 
  - Search flights by departure/arrival locations, dates, and airline
  - Combined search with multiple parameters
  - Sort flights by price (ascending/descending)
- **Airline Information**: Browse airlines and view approved reviews
- **User Registration & Login**: Secure authentication system

### For Registered Users (Passengers)
- **Profile Management**: View and edit personal information
- **Flight Overview**: View active, completed, and cancelled flights
- **Reservation System**:
  - Create reservations for active flights
  - Automatic seat availability updates
  - View all personal reservations with status filtering
- **Cancel Reservations**: Cancel reservations up to 24 hours before departure
- **Review System**: Leave reviews for airlines after completing flights

### For Administrators
- **User Management**:
  - View all system users
  - Search users by name, surname, and date range
  - Sort users by name or birth date
- **Airline Administration**:
  - Add, edit, and view airlines
  - Search airlines by name, address, and contact info
  - Logical deletion (only airlines without active flights)
- **Flight Management**:
  - Add new flights for airlines
  - Edit flight information (with restrictions on flights with active reservations)
  - Logical deletion (only flights without pending/approved reservations)
  - Automatic status updates (Active → Completed)
  - Search flights by location and date
- **Reservation Management**:
  - View all system reservations
  - Approve or cancel pending reservations
  - Automatic seat management
- **Review Moderation**:
  - Approve or reject user reviews
  - Approved reviews become visible to all users


## 🔧 Setup Instructions

### Prerequisites
- Visual Studio 2019 or later
- .NET Framework 4.7.2 or higher
- IIS Express (included with Visual Studio)

### Installation Steps

1. **Clone the repository**
```bash
git clone [your-gitlab-repo-url]
cd MyWebApp
```

2. **Open the solution**
   - Open `MyWebApp.sln` in Visual Studio

3. **Restore NuGet packages**
   - Right-click on solution → Restore NuGet Packages

4. **Build the solution**
   - Build → Build Solution (Ctrl+Shift+B)

5. **Run the application**
   - Press F5 or click Start in Visual Studio
   - The application will open in your default browser

### Default Test Data

The application comes with pre-loaded test data including:
- Administrator account: `admin` / `admin123`
- Sample passenger accounts
- Multiple airlines with flights
- Sample reservations and reviews

## 🌐 API Endpoints

### Authentication
- `GET /api/login?username={username}&password={password}` - User login
- `POST /api/users/register` - User registration
- `GET /api/users/logout` - User logout

### Users
- `GET /api/users/profile` - Get current user profile
- `GET /api/users/all` - Get all users (Admin only)
- `GET /api/users/searchUsers` - Search users with filters
- `PUT /api/users/izmena` - Update user profile
- `PUT /api/users/put` - Create reservation
- `PUT /api/users/cancel` - Cancel reservation

### Flights
- `GET /api/letovi/all` - Get all active flights
- `GET /api/letovi/getLetovi` - Search flights with filters
- `GET /api/letovi/allAdmin` - Get all flights (Admin)
- `GET /api/letovi/{id}` - Get flight by ID
- `POST /api/letovi/post` - Add new flight
- `PUT /api/letovi/put/izmena` - Update flight
- `DELETE /api/letovi/delete/{id}` - Delete flight

### Airlines
- `GET /api/aviokompanije/all` - Get all airlines
- `POST /api/aviokompanije/post` - Add airline
- `PUT /api/aviokompanije/put` - Update airline
- `DELETE /api/aviokompanije/delete/{id}` - Delete airline

### Reservations
- `GET /api/rezervacije/all` - Get all reservations
- `PUT /api/rezervacije/approve` - Approve/cancel reservation

### Reviews
- `GET /api/recenzije/all` - Get all reviews
- `POST /api/recenzije/post` - Create review
- `PUT /api/recenzije/approve` - Approve/reject review

## 💾 Data Persistence

All data is stored in JSON format in the `App_Data` folder:
- `users.json` - User accounts and profiles
- `letovi.json` - Flights information
- `aviokompanije.json` - Airlines data
- `rezervacije.json` - Reservations
- `recenzije.json` - Reviews

## 🎯 Key Features Implementation

### Automatic Status Management
- Flights automatically change status from Active to Completed after arrival time
- Reservations update seat availability in real-time

### Business Rules
- Reservations can only be cancelled 24+ hours before departure
- Flight prices cannot be changed if there are pending/approved reservations
- Flights cannot be deleted if they have pending/approved reservations
- Airlines cannot be deleted if they have active flights
- Only completed flights allow passengers to leave reviews

### Search & Filter
- Combined search with multiple parameters
- Real-time filtering by status
- Sorting by price, name, and date
- Date range filtering

## 📝 Project Scoring

This project uses:
- ✅ jQuery library
- ✅ REST API (ASP.NET Web API 2)
- ✅ AJAX calls
- ✅ JSON data exchange between client and server

## 🎨 UI/UX Features

- Responsive design with Bootstrap 5
- Clean and intuitive navigation
- Form validation
- Dynamic table updates
- Real-time data refresh
- Status indicators with color coding

## 🔒 Security Features

- Session-based authentication
- Password-protected accounts
- Role-based access control
- Input validation on both client and server
- Logical deletion for data integrity


**Note**: This is a demonstration project for educational purposes. Not intended for production use.
