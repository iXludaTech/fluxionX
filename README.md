![FluxionX logo](logos/logo.jpg)

# FluxionX — MITM WPA/WPA2 security auditing tool

FluxionX is a modern fork of Fluxion, a security auditing and social-engineering research tool. It is a remake of linset by vk496 with fewer bugs and more functionality. The script attempts to retrieve the WPA/WPA2 key from a target access point by means of a social engineering (phishing) attack. It is compatible with the latest release of Kali (rolling). FluxionX's attacks' setup is mostly manual, but experimental auto-mode handles some of the attacks' setup parameters.

## Installation

**Download the latest revision**
```bash
git clone https://github.com/iXluda-Tech/fluxionX.git
```

**Switch to tool's directory**
```bash
cd fluxionX
```

**Run fluxionX (it will check dependencies and prompt to install any that are missing)**
```bash
./fluxion.sh
```

**To install/check dependencies only without running attacks**
```bash
./fluxion.sh -i
```

**FluxionX is also available on Arch Linux**
```bash
cd bin/arch
makepkg
```

## Changelog

FluxionX is actively maintained with new features, improvements, and bugfixes. Be sure to check the [changelog](https://github.com/iXluda-Tech/fluxionX/commits/main).

## How to contribute

All contributions are welcome! Code, documentation, graphics, or even design suggestions are welcome. Submit pull requests, contribute tutorials, or other content — whatever you have to offer, it will be appreciated.

## How it works

1. Scan for a target wireless network.
2. Launch the `Handshake Snooper` attack.
3. Capture a handshake (necessary for password verification).
4. Launch `Captive Portal` attack.
5. Spawns a rogue (fake) AP, imitating the original access point.
6. Spawns a DNS server, redirecting all requests to the attacker's host running the captive portal.
7. Spawns a web server, serving the captive portal which prompts users for their WPA/WPA2 key.
8. Spawns a jammer, deauthenticating all clients from original AP and luring them to the rogue AP.
9. All authentication attempts at the captive portal are checked against the handshake file captured earlier.
10. The attack will automatically terminate once a correct key has been submitted.
11. The key will be logged and clients will be allowed to reconnect to the target access point.

## Requirements

A Linux-based operating system. We recommend Kali Linux. An external wifi card is recommended.

## Credits

### iXluda-Tech maintainers
- FluxionX is maintained by [iXluda-Tech](https://github.com/iXluda-Tech)

### Original Fluxion contributors
1. l3op - contributor
2. dlinkproto - contributor
3. vk496 - developer of linset
4. Derv82 - @Wifite/2
5. Princeofguilty - @webpages and @buteforce
6. Ons Ali @wallpaper
7. PappleTec @sites
8. MPX4132 - Fluxion V3
9. usama7628674 - contributor
10. cjb900 - moderator

## Disclaimer

Authors do not own the logos under the `/attacks/Captive Portal/sites/` directory. Copyright Disclaimer Under Section 107 of the Copyright Act 1976, allowance is made for "fair use" for purposes such as criticism, comment, news reporting, teaching, scholarship, and research.

The usage of FluxionX for attacking infrastructures without prior mutual consent could be considered an illegal activity and is highly discouraged by its authors/developers. It is the end user's responsibility to obey all applicable local, state and federal laws. Authors assume no liability and are not responsible for any misuse or damage caused by this program.

## Note

- Beware of sites pretending to be related with the Fluxion Project. These may be delivering malware.
- For WN722n V2/V3 VISIT — https://github.com/aircrack-ng/rtl8188eus
- FluxionX **DOES NOT WORK** on Windows Subsystem for Linux (WSL/WSL2), because the subsystem does not allow access to wireless network interfaces.
