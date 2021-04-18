# WikiJS
WikiJS Docker-Compose


Default Container recommendations

Version 2 Docker-Compose Config
---
version: "2.1"
services:
  wikijs:
    image: ghcr.io/linuxserver/wikijs
    container_name: wikijs
    environment:
      - PUID=1000
      - PGID=1000
      - TZ=Europe/London
    volumes:
      - <path to config>:/config
      - <path to data>:/data
    ports:
      - 3000:3000
    restart: unless-stopped
  
  Docker CLI
  
  docker run -d \
  --name=wikijs \
  -e PUID=1000 \
  -e PGID=1000 \
  -e TZ=Europe/London \
  -p 3000:3000 \
  -v <path to config>:/config \
  -v <path to data>:/data \
  --restart unless-stopped \
  ghcr.io/linuxserver/wikijs
