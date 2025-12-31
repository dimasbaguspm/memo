Ghost CMS (Docker Compose)

Quick start

1. Copy the example env file and edit secrets:

```bash
cp .env.example .env
# edit .env and set SITE_URL, MYSQL_ROOT_PASSWORD, MYSQL_PASSWORD
```

2. Start services:

```bash
docker compose up -d
```

3. Open your site: http://localhost:2368

Admin: http://localhost:2368/ghost

Access environment variables inside the container

```bash
# open a shell in the running Ghost container
docker compose exec ghost /bin/sh
# then inside the container
echo "$SITE_URL"
```

Notes

- `ghost_content` and `db_data` volumes persist content and database.
- Use a secure, random password for `MYSQL_ROOT_PASSWORD` and `MYSQL_PASSWORD`.
- For production, set `SITE_URL` to your public domain and put a reverse proxy (e.g., nginx) or SSL in front of Ghost.
