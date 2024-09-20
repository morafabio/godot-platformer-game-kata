# Platform Game

A kata to demonstrate GitHub Actions.

Original project built: https://github.com/CodingQuests/Platformer-game

### Container
```shell
docker run --rm \
  --platform linux/amd64 \
  -v "$(pwd):/app" -w /app \
  -ti ubuntu:latest \
    /bin/bash
```

#### Base packages
```shell
mkdir -p /opt/godot && cd /opt/godot
```
```shell
apt-get update && apt-get -y upgrade
apt-get install -y --no-install-recommends libfontconfig wget zip unzip file git ca-certificates
```
```shell
godot_url="https://github.com/godotengine/godot/releases/download/4.3-stable/Godot_v4.3-stable_linux.x86_64.zip"
wget -q "${godot_url}" -O godot.zip
unzip godot.zip
mv /opt/godot/Godot_v4.3-stable_linux.x86_64 /usr/local/bin/godot
godot --version --headless
```

### Configurations
```shell
cat export_presets.cfg | grep -e "^name="
```