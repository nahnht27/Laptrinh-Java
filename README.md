# Smart Heritage

University project — Smart Heritage platform.

## Project Structure

```
├── backend/     → Spring Boot API (Java 17, Maven)
├── frontend/    → React (npm, chạy local)
├── mobile/      → React Native (npm, chạy local)
└── docker-compose.yml
```

## Quick Start (Docker)

Chỉ cần Docker Desktop đang chạy, rồi:

```bash
# Build & chạy cả PostgreSQL + Backend
docker-compose up --build

# Chạy nền (detached)
docker-compose up --build -d
```

> Nếu dùng Docker Compose V2 plugin, thay `docker-compose` bằng `docker compose` (không có dấu `-`).

Sau khi chạy xong:

| Service    | URL                                  |
|------------|--------------------------------------|
| Backend    | http://localhost:8080                 |
| Health     | http://localhost:8080/api/health      |
| PostgreSQL | localhost:5432 (db: `smart_heritage`) |

### Verify

```bash
curl http://localhost:8080/api/health
# → {"status":"UP","timestamp":"..."}
```

### Dừng

```bash
# Dừng containers
docker-compose down

# Dừng + xóa data PostgreSQL
docker-compose down -v
```

## Docker Services

| Service    | Image / Build         | Port |
|------------|----------------------|------|
| `postgres` | postgres:16-alpine   | 5432 |
| `backend`  | ./backend (Dockerfile) | 8080 |

## Chạy Frontend / Mobile (local, không Docker)

```bash
# Frontend
cd frontend
npm install
npm run dev

# Mobile
cd mobile
npm install
npm start
```

## Database

- **DB name**: `smart_heritage`
- **Username**: `postgres`
- **Password**: `postgres`
- **Port**: `5432`

Docker tự tạo database khi chạy lần đầu. Data được lưu trong Docker volume `postgres_data`.

## Lưu ý cho team

- **Không cần cài Java hay Maven** trên máy — Docker lo hết phần backend.
- **Không cần cài PostgreSQL** trên máy — Docker lo luôn.
- Chỉ cần cài **Docker Desktop** + **Node.js** (cho frontend/mobile).
- Lần build đầu tiên sẽ lâu (~2-5 phút) vì tải dependencies. Lần sau nhanh hơn nhờ Docker cache.
