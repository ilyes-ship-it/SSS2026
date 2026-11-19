# SSS2026 - Strumenti di sviluppo software (CI/CD)

## Lab 1: Git
Commit, branching, push/pull, merge and merge-conflict practice (done on this README).

## Docker Esercitazione: docker-webserver/
Local deploy of a webserver with Docker: own nginx (nginx:alpine) image serving an HTML page.

## Esercitazione 2: somebankingapp-dockerfiles/
Dockerfiles for the SomeBankingApp backend (FastAPI) and frontend (Angular).

## Esercitazione 3: somebankingapp-dockerfiles/

1. Updated the backend and frontend Dockerfiles to clone the app from its original GitHub repository instead of copying local files.
2. Wrote a proxy (nginx) that sends `/` to the frontend and `/api/` to the backend, on port 80.
3. Tagged the three images (`banking-backend:1.0`, `banking-frontend:1.0`, `banking-proxy:1.0`).
4. Wrote a `docker-compose.yaml` that runs all three on one network, with only the proxy reachable from outside.

### Problems I noticed and fixed
- The frontend had the backend address (`http://127.0.0.1:8000`) written in its code, so it skipped the proxy. Replaced it with `/api` in the frontend Dockerfile.
- DevTools showed the live-reload connection failing through the proxy (the app itself worked). Fixed it by forwarding the WebSocket headers in nginx, with the help of Claude Opus 5.5.

![Before](somebankingapp-dockerfiles/docs/images/websocket-blocked.png)
![After](somebankingapp-dockerfiles/docs/images/websocket-fixed.png)

Fix: [a22001d](https://github.com/ilyes-ship-it/SSS2026/commit/a22001d)