# Aerofoil Self-Hosted

This repository contains the configuration to self-host Aerofoil using Docker Compose. It is configured to use a `macvlan` network, which is ideal for assigning a dedicated static IP to the container on your local network (commonly used on Synology NAS devices or dedicated home servers).

## Getting Started

1. Copy the example environment file to create your own configuration:

   ```bash
   cp .env.example .env
   ```

2. Edit the newly created `.env` file with your preferred credentials and correct network parameters for your local environment (e.g., matching your router's subnet and gateway).

3. Review `docker-compose.yml` to ensure the host volume paths (e.g., `/volume1/nsw` and `/volume1/docker/aerofoil/...`) match your server's directory structure.

4. Start the container:
   ```bash
   docker compose up -d
   ```

## Security Notes

- The game directory is mounted as read-only (`:ro`) to prevent accidental modifications to your media.
- Do not commit your `.env` file to version control, as it contains your passwords.
