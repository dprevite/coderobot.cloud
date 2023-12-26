# The Plan

A repository with ansible playbooks, docker-compose files, and other configuration 
files to fully automate the deployment of my home network. Repeatable, testable, self-documenting,
and easy to maintain.

This is a very early work in progress. I'm still figuring out how to do a lot of this stuff.

## Installation
If everything goes well you will be able to:

1. Install Proxmox on a new machine
2. Install Ansible on your local machine
3. Clone this repo
4. Bring everything up with `ansible-playbook -i master.yml --ask-vault-pass --extra-vars "@secret.yml" -vvv`

## Services
- [ ] Pi-hole
  - [ ] DNS
- [ ] Plex
- [ ] Snipe-IT (Inventory)
- [ ] Docusaurus (Documentation about how this all works)
- [ ] Home Dashboard (custom static site with a directory of all services)
- [ ] Authelia (Centralized Auth with 2FA)
- [ ] Bitwarden (Password Manager)
- [ ] FreshRSS (RSS reader)
- [ ] Gitlab (Git repo, CI/CD, Docker registry)
- [ ] Home Assistant
- [ ] LetsEncrypt (SSL)
- [ ] Minio (S3 compatible storage)
- [ ] OwnCast (Self hosted live streaming)
- [ ] Portainer
- [ ] Proxmox (Hypervisor on Desktop and Dell Optiplex)
    - [ ] Ubuntu cloud init template
    - [ ] Ubuntu cloud init instance with docker and docker-compose
- [ ] Ptonomy (Custom self-hosted notes and knowledge base) 
- [ ] Tailscale (Private VPN for remote access)
- [ ] Tautulli (Plex stats)
- [ ] Traefik (Reverse Proxy, SSL)
- [ ] Uptime Kuma (Uptime monitoring)

## Hardware
- Proxmox Playground: Dell OptiPlex 7040m Micro Ultra Small Form Factor (USFF)
  - i5-6500T 2.5GHz 
  - 16GB 
  - 1TB SSD 
- Desktop Server: Dell XPS 8930 Desktop (Proxmox)
  - Processor: 9th Gen Intel® Core™ i9 9900 (8-Core)
  - GPU: NVIDIA GeForce RTX 2060 6GB GDDR6
  - Memory: 32GB DDR4 at 2666MHz
  - Hard Drive: 
    - 512GB M.2 PCIe NVMe SSD (Boot) 
    - 2TB 7200RPM 3.5" SATA HDD (Storage)
  - Wireless: Killer™ Wi-Fi 6 AX1650, 2 x 2, Bluetooth 5.0
  - CD/DVD/BDRE Drive (Reads and Writes to Blu-Ray disks)
- Unifi Dream Machine Pro SE
- Access Point U6 Long-Range (U6-LR-US)
- Motorola MB8611 2.5Gbps Cable Modem
- Netgear 48 port gigabit switch
- Gargantua-1: Synology DS1815+ (Current Plex, Synology Surveillance Station)
  - Intel Atom C2538 Quad Core 2.4GHz
  - DDR3 2 GB
  - Gigabit X 4
  - Storage Pool 1 - Plex Media, Photo Backups - 50.5 TB (77% used)
    - Drive 1: Red WDC WD140EFGX-68B0GN0 (12.7 TB)
    - Drive 2: Red WDC WD140EFGX-68B0GN0 (12.7 TB)
    - Drive 3: Red WDC WD140EFGX-68B0GN0 (12.7 TB)
    - Drive 6: Red WDC WD140EFGX-68B0GN0 (12.7 TB)
    - Drive 7: Red WDC WD140EFGX-68B0GN0 (12.7 TB)
  - Storage Pool 2 - Surveillance Station - 14.3 TB (59% used)
    - Drive 4: Purple WDC WD121PURZ-85GUCY0 (10.9 TB)
    - Drive 5: Purple WDC WD60EFRX-68MYMN1 (5.5 TB)
    - Drive 8: Purple WDC WD102PURZ-85BXPY0 (9.1 TB)
  - Gargantua-2: Synology DS1823xs+ (New media storage for new Plex, backups)
    - AMD Ryzen V1780B 4-core 3.35 (base) / 3.6 (turbo) GHz
    - 8 GB (8 GB x 1)
    - 2 1GbE with Link Aggregation / Failover support
    - 1 10GbE

## To Figure Out
- How to get a wildcard SSL cert for `*.home.coderobot.cloud`?
- How to do centralized auth for all services?
- Email server, sendgrid, something? I want to be able to send emails from my domain.
- Centralized logging, something like papertrail
- Backups: local + off site + AWS Glacier
- How to test backups
- Centralized alerts and monitoring, something like new relic
- Centralized secret management, something like vault, does bitwarden help
- SSH access to all servers with the same user and ssh key
- Cloudflare tunnel for remote access to public services and websites
- Does tailscale help with remote access to private services when connected to tailscale?
- Something to replace Day One for journaling
- Some way to do tighter integration with the Synology or Unifi Dream Machine Pro SE
- How can I utilize the Dell 8930 desktop's 2060 GPU for transcoding in Plex?
- I have a Windows 10 Pro license, I should use it for a Windows VM on the desktop
- Add additional 32GB of RAM to the desktop
- Add 2 TB SSD to the desktop, nvme?
- Upgrade Gargantua-1 and Gargantua-2 to max RAM, ssd cache?
- Upgrade ram in playground to max, at least 32GB
- Move Plex storage from Gargantua-1 to Gargantua-2 once I have hard drives, move Plex server 
  to a Docker container on the desktop server.
  - I don't want to lose watch history, play history, etc.
  - Network speed between NAS and Desktop fast enough?
  - Benchmark ffmpeg on desktop vs NAS to see if it's worth it
- how to securely give access to some services to friends and family?
- intrusion detection, fail2ban, etc
- how to do home assistant via ansible

## Domains for DNS and Traefik
- [ ] desktop.home.coderobot.cloud (Proxmox) 
- [ ] docs.home.coderobot.cloud (Docusaurus) 
- [ ] home.coderobot.cloud (Home Dashboard) 
- [ ] inventory.desktop.home.coderobot.cloud (Snipe-IT) 
- [ ] dns.desktop.home.coderobot.cloud (Pi-hole)) 
- [ ] plex.desktop.home.coderobot.cloud 
- [ ] plex.gargantua-1.home.coderobot.cloud 
- [ ] plex.gargantua-2.home.coderobot.cloud 

Denon Speakers UI: 192.168.2.79:10443







