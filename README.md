# Feed-The-Beast Sky Odyssey (Modded Minecraft 1.12) in Docker
To pull the image:
```
docker pull audiohacked/ftb_sky_odyssey:stable
```

It's highly recommended run a named data volume:
```
docker volume create minecraft_ftb_sky_odyssey_data
docker volume create minecraft_ftb_sky_odyssey_backups
```

Then, run the server container:
```
docker run --detach --interactive --tty \
    --name ftb_sky_odyssey \
    --volume minecraft_ftb_sky_odyssey_data:/minecraft/world \
    --volume minecraft_ftb_sky_odyssey_backups:/minecraft/backups \
    --publish 25565:25565 \
    --env EULA=TRUE \
    audiohacked/ftb_sky_odyssey:stable
```
