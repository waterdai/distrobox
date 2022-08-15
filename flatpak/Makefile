HOST_SPAWN_VERSION=1.2.1

all:
	mkdir -p dist
	wget --no-verbose -c "https://github.com/1player/host-spawn/releases/download/${HOST_SPAWN_VERSION}/host-spawn-$$(uname -m)" -O ./host-spawn
	flatpak-builder --disable-rofiles-fuse --user --repo=dist/repo --state-dir=dist/.flatpak-builder --force-clean dist/tmp/ io.github.luca.distrobox.yml
	flatpak build-bundle dist/repo/ dist/io.github.luca.distrobox.flatpak io.github.luca.distrobox

install:
	flatpak install --user -y dist/io.github.luca.distrobox.flatpak

clean:
	rm -rf dist
	mkdir -p dist
	rm -f host-spawn
