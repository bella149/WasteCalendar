# WasteCalendar
The waste calendar displays the individual disposal dates for all waste containers, only for Illertissen

# Used tools
- Java 21
- Spring Boot 4.0.1
- Node.js 24.12.0
- Vue.js 3.5.26
- VS Code 1.107.1

# Build Backend
```sh
cd backend
.\mvnw clean install
```

# Build Frontend
```sh
cd frontend
npm install
npm build
```

# Run for Development

```sh
#
cd frontend & npm run dev
cd backend & ./mvnw spring-boot:run
```

Note:
- Frontend runs at http://localhost:5173/
- Backend runs at http://localhost:8090/
