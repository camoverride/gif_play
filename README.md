# Gif player

## Setup

Place the file `combined_gif.gif` in the home directory: `/home/pi/combined_gif.gif`

Start a service with *systemd*. This will start the program when the computer starts and revive it when it dies:

- `mkdir -p ~/.config/systemd/user`

- Paste the contents of `display_gif.service` into `~/.config/systemd/user/display_gif.service`

Start the service using the commands below:

- `systemctl --user daemon-reload`
- `systemctl --user enable display_gif.service`
- `systemctl --user start display_gif.service`

Start it on boot: `sudo loginctl enable-linger pi`

Get the logs: `journalctl --user -u display.service`