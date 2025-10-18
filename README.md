# Public API Endpoints

| Method | Endpoint | Description |
|--------|---------|-------------|
| POST | /auth/register | Register new user (returns token) |
| POST | /auth/login | Login (returns token) |
| GET  | /players | List all players |
| GET  | /players/:id | Get single player info |
| GET  | /games | List all games |
| GET  | /players/:id/achievements | Player achievements |
| GET  | /leaderboard/:gameId | Game leaderboard |
| POST | /scores | Submit a score |

# Secure Endpoints (Admin Only)

| Method | Endpoint | Description |
|--------|---------|-------------|
| POST | /games | Add a new game |
| POST | /achievements | Add a new achievement |

> Requires **Bearer token** in header

*Notes for testing*

# cURL Example — Register User
curl -X POST http://localhost:8080/auth/register \
-H "Content-Type: application/json" \
-d '{"name":"TestPlayer","email":"test@test.com","password":"1234"}'

#cURL Example - Login 
curl -X POST http://localhost:8080/auth/login \
-H "Content-Type: application/json" \
-d '{"email":"test@test.com","password":"1234"}'
Response: {
  "token": "eyJ0eXAiOiJKV1QiLCJhbGci..."
}

#cURL Example - Get All Players
curl -X GET http://localhost:8080/players \
-H "Authorization: Bearer YOUR_TOKEN_HERE"
Response: [
  {"id":1,"name":"TestPlayer","level":5,"joined_at":"2025-10-17 20:58:35"}
]

#cURL Example — Get Single Player
curl -X GET http://localhost:8080/players/1 \
-H "Authorization: Bearer YOUR_TOKEN_HERE"
Respoonse:{"id":1,"name":"TestPlayer","level":5,"joined_at":"2025-10-17 20:58:35"}

#cURL Example — Submit Score
curl -X POST http://localhost:8080/scores/submit.php \
-H "Content-Type: application/json" \
-H "Authorization: Bearer YOUR_TOKEN_HERE" \
-d '{"player_id":1,"game_id":1,"score":1500}'
Response:{"score_id":2}

#Admin cURL Example — Add Game
curl -X POST http://localhost:8080/games/add.php \
-H "Content-Type: application/json" \
-H "Authorization: Bearer ADMIN_TOKEN_HERE" \
-d '{"title":"New Game"}'
Response: {"game_id":3,"title":"New Game"}

