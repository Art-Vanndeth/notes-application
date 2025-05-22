# Notes Application

A full-stack Notes Application built with **Vue 3 + TypeScript + Tailwind CSS** for the frontend and **ASP.NET Core Web API (C#)** with **Dapper** and **SQL Server** for the backend.

## Features

- **Create Note:** Title (required), content (optional), auto-generated created/updated timestamps.
- **Read Notes:** List and view details of your notes, including creation date and content.
- **Update Note:** Edit the note's title/content; updated timestamp auto-refreshes.
- **Delete Note:** Remove notes from your list.
- **User Authentication:** (Optional for junior position) Register/login to manage your own notes.
- **Filtering, Sorting, and Search:** Quickly find notes with responsive UX.
- **Authorization:** (Optional for junior position) Users can only manage their own notes.

## Tech Stack

- **Frontend:** Vue 3, TypeScript, Pinia (state management), Tailwind CSS, Axios, Vite
- **Backend:** ASP.NET Core Web API (C#), Dapper ORM
- **Database:** SQL Server
- **Dev Tools:** Docker (for SQL Server), ESLint, Prettier

---

## Project Structure

```
notes-application/
├── notes-app/           # Frontend (Vue 3 + TypeScript + Tailwind CSS)
└── NotesApi/            # Backend (ASP.NET Core Web API + Dapper)
```

---

## Getting Started

### Prerequisites

- Node.js >= 18.x (for frontend)
- .NET 8 SDK (for backend)
- Docker (for SQL Server containerized DB)
- SQL Server tools (optional, for local DB access)

---

### 1. Clone the Repository

```sh
git clone https://github.com/Art-Vanndeth/notes-application.git
cd notes-application
```

---

### 2. Backend Setup (ASP.NET Core API)

#### a) Configure Database

- Use Docker Compose to spin up a SQL Server instance:

```sh
cd NotesApi
docker compose up -d
```

- By default, the DB is accessible at `localhost:1433` with credentials as in `NotesApi/appsettings.json`:
  - **User:** sa
  - **Password:** StrongP@ssw0rd!  
  > ⚠️ Change the default password before deploying to production.

#### b) Restore and Run the API

```sh
dotnet restore
dotnet build
dotnet run
```

- The API will be available at: `https://localhost:5112` (see `NotesApi/Program.cs`)

---

### 3. Frontend Setup (Vue 3 + Tailwind)

```sh
cd ../notes-app
npm install
npm run dev
```

- The app will run on Vite's default port (likely `http://localhost:5173`).

#### Project Scripts

- `npm run dev` - Start dev server
- `npm run build` - Production build
- `npm run lint` - Lint code with ESLint
- `npm run format` - Format code with Prettier

---

## API Integration

- The frontend uses Axios/fetch to connect to the backend.
- Adjust API base URLs in the frontend as needed for local or deployment environments.

---

## Development Notes

- **CORS:** The backend is configured to accept requests from the frontend dev server (`http://localhost:5173`).
- **ORM:** Backend uses Dapper for database access (see `NotesApi/NotesApi.csproj`).
- **Authentication:** JWT-based authentication/authorization is scaffolded in the backend.
- **State Management:** Frontend uses Pinia for state.

---

## Extending the Project

- Add authentication/authorization flows and UI.
- Improve filtering, sorting, and UX.
- Add unit/integration tests.

---

## License

This project is currently unlicensed. Please add a license file if you intend to open source.

---

## Contributing

Feel free to open issues or submit PRs!

---

## Author

[Art-Vanndeth](https://github.com/Art-Vanndeth)

---

## Useful Links

- [Backend Source](https://github.com/Art-Vanndeth/notes-application/tree/main/NotesApi)
- [Frontend Source](https://github.com/Art-Vanndeth/notes-application/tree/main/notes-app)
- [Docker Compose for SQL Server](https://github.com/Art-Vanndeth/notes-application/blob/main/NotesApi/docker-compose.yml)
