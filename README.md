# waydroid-panthor-config

Waydroid binder/init service configuration for FydeTab Duo with Panthor GPU.

**Status: Experimental** - This package is in development and has not been fully tested yet.

## Overview

**Specifically designed for FydeTab Duo** with Panthor GPU. Provides systemd units, binderfs setup, and initialization scripts required to run Waydroid with Panthor GPU support.

## Package Contents

### Systemd Units
- `dev-binderfs.mount` - Mounts binderfs at `/dev/binderfs`
- `waydroid-binder-setup.service` - Creates binder device nodes
- `waydroid-panthor-init.service` - Initializes Waydroid for Panthor

### Scripts
- `waydroid-panthor-init` - Initialization script for Waydroid
- `waydroid-test` - Test script for verifying Waydroid setup

### Configuration
- `waydroid.conf` - modules-load.d config to load binder module at boot

## Build

```sh
makepkg -si
```

## Post-Install

After installation, enable and start the services:

```sh
sudo systemctl enable --now dev-binderfs.mount
sudo systemctl enable --now waydroid-binder-setup.service
```

## Related Packages

- `waydroid` - Required base Waydroid package
- `waydroid-panthor-images` - Required Android images with Panthor GPU support

## License

MIT
