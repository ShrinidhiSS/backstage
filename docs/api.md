# 🎨 Artist API Reference

Welcome to the **Artist API** documentation. This API allows consumers to retrieve and manage artist data and their associated artworks.

## 🔗 Base URL

```
http://artist.spotify.net/v1
```

---

## 📘 Endpoints

### 🧾 GET /artists

**Description**: Fetches a list of all registered artists.

**Response**:
```json
[
  {
    "id": "1",
    "name": "Vincent van Gogh",
    "genre": "Post-Impressionism",
    "birthYear": 1853
  }
]
```

---

### 🔍 GET /artists/{id}

**Description**: Retrieves detailed information about a specific artist.

**Path Parameters**:
- `id` (string) — Unique ID of the artist.

**Example**:
```bash
GET /artists/1
```

**Response**:
```json
{
  "id": "1",
  "name": "Vincent van Gogh",
  "genre": "Post-Impressionism",
  "birthYear": 1853,
  "bio": "Vincent van Gogh was a Dutch Post-Impressionist painter..."
}
```

---

### ➕ POST /artists

**Description**: Adds a new artist to the database.

**Request Body**:
```json
{
  "name": "Frida Kahlo",
  "genre": "Surrealism",
  "birthYear": 1907
}
```

**Response**:
```json
{
  "id": "2",
  "message": "Artist created successfully."
}
```

---

### ✏️ PUT /artists/{id}

**Description**: Updates an existing artist's details.

**Request Body**:
```json
{
  "genre": "Modernism",
  "bio": "Updated biography..."
}
```

**Response**:
```json
{
  "message": "Artist updated successfully."
}
```

---

### ❌ DELETE /artists/{id}

**Description**: Removes an artist by their ID.

**Response**:
```json
{
  "message": "Artist deleted successfully."
}
```

---

## 🛑 Error Codes

| Code | Message               | Description                         |
|------|------------------------|-------------------------------------|
| 400  | Bad Request            | Missing or invalid data.            |
| 404  | Not Found              | Artist not found.                   |
| 500  | Internal Server Error  | Something went wrong on the server. |

---

## 🔐 Authentication

All endpoints require a valid API token to be passed in the header:
```http
Authorization: Bearer YOUR_API_TOKEN
```

---

## 📎 Related Docs

- [Getting Started](getting-started.md)
- [Artist Web Overview](index.md)
