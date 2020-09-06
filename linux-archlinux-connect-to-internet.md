---
title: [linux] archlinux connect to internet
date: 2020-09-06 19:15:40
tags: linux
---

## Prerequisites

1. iwlist
2. wpa_passphrase
3. wpa_supplicant

## Steps

### For the first time


```bash
# turn on netword interface
ip link               # show all network interfaces, e.g. wlan0
ip link set wlan0 up  # turn on network interface
ip link               # check interface status is up

# show all available networks
iwlist wlan0 scan | grep ESSID  # get available networks, e.g. SomeWiFi

# connect to network
wpa_passphrase SomeWiFi <password> > ~/wifi.conf  # save network info to file
wpa_supplicant -c ~/wifi.conf -i wlan0 &          # connect to network

# allocate ip address
dhcpcd &

# check network
ping www.bing.com
```

### For the second time and later

```bash
ip link set wlan0 up
wpa_supplicant -c ~/wifi.conf -i wlan0 &
dhcpcd &
```

