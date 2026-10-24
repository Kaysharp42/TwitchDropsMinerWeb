# TwitchDropsMinerWeb

Enhanced fork of [TwitchDropsMiner](https://github.com/DevilXD/TwitchDropsMiner) with improved web interface capabilities and Docker support.

## Web Interface Features

The web interface allows you to:

- Monitor and control the miner from any browser
- View active drop campaigns and progress
- Check available channels and their status
- View claimed and pending drops in your inventory
- Manage login and authentication
- Configure application settings

## Windows executable

Build with `build.bat` after installing `requirements.txt` in the virtual environment, then run:

```powershell
& ".\dist\Twitch Drops Miner (by DevilXD).exe" --web --web-host 127.0.0.1 --web-port 8080
```

`--web` enables web-only mode. The host defaults to `127.0.0.1` and the port to `8080`.
Open `http://localhost:8080` in your browser. Use `--web-host 0.0.0.0` to allow
connections from other machines; only expose it on a trusted network.
Without `--web`, the executable opens the desktop interface as before.
Web credentials and `.env` are read from beside the executable, not its temporary extraction folder.

## Docker Deployment

This fork adds comprehensive Docker support for easy deployment in containers. The app automatically runs in web-only mode when deployed in Docker:

1. **Quick Start:**
   ```powershell
   # Create necessary directories
   .\docker-setup.ps1 setup

   # Start the container
   .\docker-setup.ps1 start
   ```

2. **Access the Interface:**
   Open your browser and go to: `http://localhost:8080`

## GitHub Container Registry

Pre-built images are available on GitHub Container Registry:
```bash
docker pull ghcr.io/kaysharp42/twitchdropsminer-web:latest
```

## Configuration

All settings can be configured via the web interface. The application stores:
- Logs in `./data/logs/`
- Cache in `./data/cache/`
- Settings in `./data/settings.json`
- Authentication in `./data/cookies.jar`

See the [Docker Usage Guide](DOCKER.md) for detailed instructions.
