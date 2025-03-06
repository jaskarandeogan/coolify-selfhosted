# Coolify Self-Hosted Setup

This repository contains configuration files for setting up a self-hosted [Coolify](https://coolify.io/) instance using Docker.

## What is Coolify?

Coolify is an open-source, self-hostable Heroku/Netlify alternative. It allows you to deploy applications, databases, and other services to your own servers with a simple UI.

## Prerequisites

- Docker installed on your machine
- At least 2GB RAM available
- Access to ports 8000 (or your preferred port)

## Quick Start

1. Clone this repository:
```bash
git clone https://github.com/jaskarandeogan/coolify-selfhosted
cd coolify-selfhosted
```

2. Run the setup using Docker Compose:
```bash
docker-compose up -d
```

3. Access the Coolify dashboard:
```
http://localhost:8000
```

4. Complete the setup by following the on-screen instructions, including:
   - Creating an admin account
   - Setting up SSH keys
   - Adding your first server

## Configuration

The Docker Compose file includes:

- PostgreSQL database for data persistence
- Redis for caching and queues
- Coolify application container

You can customize the configuration by modifying the environment variables in the `docker-compose.yml` file.

## Important Notes

- The SSH key warning is normal during the initial setup. You'll need to add an SSH key through the web interface.
- If you're deploying in production, make sure to change the default passwords and keys.
- Coolify requires access to the Docker socket to function properly, which means it has container management privileges on your host.

## Troubleshooting

### Port Conflicts
If you already have services running on ports 8000, 5432, or 6379, you can change the port mappings in the `docker-compose.yml` file.

### Connection Issues
If you're having trouble connecting to the dashboard, check the Coolify logs:
```bash
docker-compose logs coolify
```

### Database Issues
If there are issues with the database, you can check its logs:
```bash
docker-compose logs coolify-db
```

## License

Coolify is licensed under the Apache License 2.0. See [Coolify's GitHub repository](https://github.com/coollabsio/coolify) for more information.
