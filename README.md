# Setup
## Initial Configuration
Copy the template to a local `.env` and adjust values as needed.
```bash
cp .env.template .env
nano .env
# Change as needed
```

## Startup
Start the application.
```bash
docker-compose up -d
```

## SSL
For using this setup with SSL via `Let’s Encrypt`, see https://github.com/wmnnd/nginx-certbot.
