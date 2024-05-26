# pirateapps
Arr apps, Deluge, Tautulli and Flaresolverr all behind PIA VPN

# Comprehensive Guide to Docker Compose Setup for Deluge and Associated Services

This Docker Compose configuration enables you to deploy Deluge along with various complementary services using Docker containers. Below is a detailed guide on configuring the variables and volumes in the docker-compose.yaml file.
Variable Configuration
VPN Service (vpn)

    LOC: Location of the VPN server. Assign a specific location code (e.g., swiss).
    USER: Your VPN username.
    PASS: Your VPN password.
    LOCAL_NETWORK (Optional): Specify your local network address range. For example: 192.168.1.0/24.
    PORT_FORWARDING (Optional): Set to 1 to enable port forwarding.
    VPNDNS (Optional): VPN DNS server address. Example: 10.0.0.241 (PIA DNS+MACE).

Flaresolverr Service (flaresolverr)

    LOG_LEVEL: Log level for Flaresolverr. Default is info.
    LOG_HTML: Set to true to enable HTML logging.
    CAPTCHA_SOLVER: Specify captcha solver. Default is none.
    TZ: Timezone. Example: America/New_York.

Homarr Service (homarr)

    No specific environment variables provided.

Overseerr Service (overseerr)

    LOG_LEVEL: Log level for Overseerr. Default is debug.
    TZ: Timezone. Example: America/New_York.
    PORT (Optional): Port for the Overseerr service.

Prowlarr Service (prowlarr)

    PUID: User ID.
    PGID: Group ID.
    TZ: Timezone. Example: America/New_York.

Radarr, Readarr, Sonarr, and Tautulli Services (radarr, readarr, sonarr, tautulli)

    PUID: User ID.
    PGID: Group ID.
    TZ: Timezone. Example: America/New_York.

Deluge Service (deluge)

    PUID: User ID.
    PGID: Group ID.
    TZ: Timezone. Example: America/New_York.
    DELUGE_LOGLEVEL (Optional): Log level for Deluge. Default is error.

Volume Configuration

    Replace </path/on/host/pc> with the corresponding path on your host PC for storing service data.

Common Volumes

    /var/run/docker.sock:/var/run/docker.sock: Optional volume for Docker integration in the Homarr service.

Specific Volumes

    vpn and pia-shared: Volumes for the VPN service.
    pcoverseer: Volume for the Overseerr service.
    prowlarr: Volume for the Prowlarr service.
    radarr: Volume for the Radarr service.
    readarr: Volume for the Readarr service.
    sonarr: Volume for the Sonarr service.
    tautulli: Volume for the Tautulli service.
    deluge: Volume for the Deluge service.

Usage

    Configure environment variables and volumes in the docker-compose.yaml file as described above.
    Run docker-compose up -d to start all services defined in the Docker Compose file.
