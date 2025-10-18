---
marp: true
theme: default
class: lead
paginate: true
---

# 🎮 Game API Project

**By:** Jacob Robbins  
**Tech Stack:** PHP, NGINX, MySQL, Postman  
**Date:** October 2025

---

## Overview

This project is a RESTful API for a gaming platform.  
It allows users to:
- Register and login
- View player stats
- Fetch game data
- Access leaderboards

---

## Tools & Technologies

- **PHP** — backend logic and database operations  
- **MySQL** — player and game data  
- **NGINX** — web server handling API requests  
- **Postman** — endpoint testing  
- **GitHub** — version control and hosting

---

## API Endpoints

| Method | Endpoint | Description |
|--------|-----------|-------------|
| POST | /auth/register | Register a new user |
| POST | /auth/login | Authenticate a user |
| GET | /players | Retrieve all players |
| GET | /players/:id | Retrieve a specific player |
| GET | /games | Get list of all games |
| GET | /leaderboard/:gameId | Fetch game leaderboard |

---

## Authentication

Users receive a **JWT token** upon login.  
Include it in headers for protected endpoints:

