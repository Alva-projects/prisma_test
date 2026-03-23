# UserLanguage API

An API where you can create users with name, email, languages and age. Built with Node.js, Express, Prisma and PostgreSQL.

---

## How to run the server

1. Install dependencies:
```bash
npm install
```

2. Create a `.env` file and add your database connection:
```
DATABASE_URL="postgresql://USER:PASSWORD@localhost:5432/your_database"
```

3. Run migrations:
```bash
npx prisma migrate dev
```

4. Start the server:
```bash
node index.js
```

Server runs on http://localhost:3000

---

## How to test

I used Insomnia to test all routes. Set the body to JSON format for POST and PUT requests.

---

## Routes I created

### Get all users
```
GET /userlanguages
```

### Get one user by email
```
GET /userlanguages/alva@test.se
```

### Create a user
```
POST /userlanguages
```
```json
{
  "name": "Alva",
  "email": "alva@test.se",
  "languages": "Svenska, engelska",
  "age": 25
}
```

### Update languages for a user
```
PUT /userlanguages/alva@test.se
```
```json
{
  "languages": "Svenska, spanska, japanska"
}
```
Finds the user by email and updates their languages.

### Delete users under 18
```
DELETE /userlanguages/underage
```
Returns how many users were deleted:
```json
{
  "message": "2 users deleted"
}
```