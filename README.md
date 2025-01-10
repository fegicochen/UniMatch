
# UniMatch

This project implements a matchmaking system backend service built with Node.js, Express, and Oracle Database. The system helps match users based on their personality traits, preferences, and compatibility scores.

## Features

- **User Management**
  - User registration and profile creation.
  - Profile updates and deletion.
  - Stores user details including email, name, gender, age, and location.

- **Personality Assessment**
  - Personality quiz with 5 key questions.
  - Tracks traits like:
    - Introversion/Extroversion
    - Intuitive/Observant
    - Thinking/Feeling
    - Judging/Prospecting
    - Turbulent/Assertive

- **Location Services**
  - Postal code-based location tracking.
  - Groups users by cities (e.g., Vancouver, Burnaby, Victoria).
  - Location-based filtering.

- **Matchmaking**
  - Compatibility score calculation based on personality traits.
  - Gender and sexuality preference matching.
  - Location-based matching options.

## Technical Stack

- **Backend**: Node.js with Express.
- **Database**: Oracle Database.
- **API**: RESTful endpoints.
- **Connection Pooling**: Oracle connection pool for efficient database management.

## Key API Endpoints

```javascript
// User Management
POST /submit-survey        // Register new user
POST /updateUser          // Update user profile
DELETE /deleteUser        // Remove user

// Matching
POST /getMatchHeteroMale  // Get matches for user
GET /counthomosexuals     // Get homosexual user count
GET /countheterosexuals   // Get heterosexual user count

// Data Operations
POST /selectUser          // Query users
POST /projectUser         // Project user fields
POST /joinAndGetUserAnswers // Get user quiz answers
```

## Database Schema

The system uses multiple interconnected tables:
- **Users**: Core user data.
- **Profile**: User preferences and additional details.
- **Personality**: Stores personality traits data.
- **UserGender**: Gender information.
- **UserPostalCode**: User location data.
- **Question**: Personality assessment questions.
- **UserAnswer**: User responses to personality quiz.
- **Matches**: Compatibility score records.

## Project Structure

```
├── appController.js    // API route handlers
├── appService.js       // Business logic and database operations
├── server.js           // Express server setup
├── userData.js         // User data operations
└── utils/
    └── envUtil.js      // Environment configuration utilities
```

## Setup

1. **Clone the repository:**
```sh
git clone https://github.com/fegicochen/matchmaking-app-backend.git
```

2. **Navigate to the project directory:**
```sh
cd matchmaking-app-backend
```

3. **Install dependencies:**
```sh
npm install
```

4. **Set up environment variables:**
   - Create a `.env` file in the root directory.
   - Define the following variables:
     ```env
     DB_USER=<your_database_user>
     DB_PASSWORD=<your_database_password>
     DB_HOST=<your_database_host>
     DB_PORT=<your_database_port>
     DB_NAME=<your_database_name>
     ```

5. **Start the server:**
```sh
npm start
```

6. **Access the API:**
   - By default, the server runs on `http://localhost:3000`.

## Contributing

Feel free to submit issues or pull requests to improve this project. Contributions are always welcome!

## License

This project is licensed under the ISC License.
