# Quotes REST API

A small Express server with in-memory CRUD for quotes.

## Install and Run
```bash
npm install
npm start          # or: npm run dev (auto-restart)
```
Server runs at `http://localhost:3000`.

## Endpoints

| Method | Route | Description | Status |
|--------|-------|-------------|--------|
| GET | /quotes | Get all quotes (supports `?author=Jobs`) | 200 |
| GET | /quotes/:id | Get one quote | 200 / 404 |
| POST | /quotes | Add a quote | 201 / 400 |
| PUT | /quotes/:id | Update a quote | 200 / 400 / 404 |
| DELETE | /quotes/:id | Delete a quote | 204 / 404 |

## Example Requests

**GET /quotes/2**
```json
{ "id": 2, "text": "Simplicity is the ultimate sophistication.", "author": "Leonardo da Vinci" }
```

**POST /quotes**
```json
{ "text": "Premature optimization is the root of all evil.", "author": "Donald Knuth" }
```
Response: `201 Created` with the new quote including its `id`.

**PUT /quotes/1**
```json
{ "text": "Stay hungry, stay foolish.", "author": "Steve Jobs" }
```

**DELETE /quotes/1** → `204 No Content`

**GET /quotes?author=Jobs** → quotes whose author contains "Jobs"

## Notes
Data is stored in memory, so it resets whenever the server restarts.