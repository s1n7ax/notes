# Fixing Network Issue on Orange PI

## Network Manager old vs new interface naming

- **OLD** `wlan0`, `wlan1`: Used for Wireless interfaces.
- **NEW** `wlP2p33s0`: Used for Wireless interfaces.

Wireless interfaces (`wlpXsY`)

- `wl` for wireless (WiFi)
- `pX` indicates the PCI bus or physical location
- `sY` indicates the slot number

Orange Pi shows two interfaces for WIFI.

- `wlan0` / `wlan1`
- `wlP2p33s0`

## Issue

When the exact interface is not used with network manager, it seems to switch
between interfaces. As a result it fails to network and the device network
cannot be accessed.

> WARNING!
> do not use `wlan0` with network manager because on reboot it will switch to
> `wlan1` and vice versa.

## Solution

- `sudo nmtui`
- Go to `Edit a connection`
- Select the interface `wlP2p33s0`
- Save and exit
