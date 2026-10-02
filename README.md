# Umami Template

Self-hosted [Umami](https://umami.is) analytics with PostgreSQL via Docker Compose.

## Deployment

1. Copy the example environment file and fill in the values:

   ```sh
   cp env.example .env
   ```

   Generate secrets with:

   ```sh
   openssl rand -hex 32   # use for APP_SECRET and TWO_FACTOR_ENCRYPTION_KEY
   ```

2. Start the stack:

   ```sh
   docker compose up -d
   ```

3. Open `http://localhost:3000` and log in with the default credentials
   `admin` / `umami` — change the password immediately.

## Operations

```sh
docker compose logs -f      # follow logs
docker compose pull && docker compose up -d   # update to latest image
docker compose down         # stop (database volume is preserved)
```

PostgreSQL data is stored in the `umami-db-data` named volume. To remove it
along with the containers, run `docker compose down -v`.
