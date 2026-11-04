# Lab 3: REST API, query parameters, validation, debugging

**Name:** YOUR NAME  
**Registration number:** YOUR REG NO  
**Section:** YOUR SECTION

**Live link:** https://YOUR-APP-NAME.onrender.com  
(If not deployed, write the reason here and rely on the Postman screenshots below.)

## How to run

```bash
cd lab-03
npm install
cp .env.example .env     # on Windows: copy .env.example .env
npm start
```

Environment variables (see `.env.example`):

| Variable | Meaning | Example |
|----------|---------|---------|
| `PORT` | Port the server listens on | `3000` |

The server opens at http://localhost:3000. A SQLite file `books.db` is created automatically and filled with sample books on first run.

## Endpoints

| Method | Path | Description |
|--------|------|-------------|
| GET | `/books` | List books. Supports `search_q`, `order_by`, `order`, `limit`, `offset`, `min_price`, `max_price` |
| GET | `/books/:id` | Get one book (404 if missing) |
| POST | `/books` | Create a book (201, or 400 if title/author/price is invalid) |
| PUT | `/books/:id` | Update a book (200, 400, or 404) |
| DELETE | `/books/:id` | Delete a book (200, or 404) |

Query parameter defaults on `GET /books`: `order_by=id`, `order=ASC`, `limit=10`, `offset=0`. `search_q`, `min_price` and `max_price` are optional.

## Screenshots

### Server running
![Server running](screenshots/01-server-running.png)

### GET /books (list with defaults)
![GET all books](screenshots/02-get-all-books.png)

### Search with search_q
![Search](screenshots/03-search.png)

### Sorting (order_by and order)
![Sorting](screenshots/04-sort.png)

### Pagination (limit and offset)
![Pagination](screenshots/05-pagination.png)

### Price range filter
![Price filter](screenshots/06-price-filter.png)

### GET /books/:id
![Get by id](screenshots/07-get-by-id.png)

### POST success (201)
![POST 201](screenshots/08-post-201.png)

### POST validation errors (400)
![POST missing title](screenshots/09-post-400-missing-title.png)
![POST bad price](screenshots/10-post-400-bad-price.png)

### PUT success (200)
![PUT 200](screenshots/11-put-200.png)

### DELETE success (200)
![DELETE 200](screenshots/12-delete-200.png)

### 404 for a missing id
![404](screenshots/13-get-404.png)

### Database view
![Database](screenshots/14-database-view.png)

### Debugging exercise
![EADDRINUSE](screenshots/15-debug-eaddrinuse.png)
![Wrong import path](screenshots/16-debug-import-path.png)
![No such table](screenshots/17-debug-no-such-table.png)
![Missing await](screenshots/18-debug-missing-await.png)
![After fixes](screenshots/19-debug-fixed.png)

### Deployment
![Render live](screenshots/20-render-live.png)
![Postman on live URL](screenshots/21-postman-live.png)

## Notes: problems faced and how I solved them

- (Write 3 to 4 lines in your own words. For example: the port conflict, the wrong import path, the table typo and the missing await, and how you fixed each.)
