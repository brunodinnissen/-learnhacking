# Installatie

Alles hieronder is gratis. Je hoeft niet alles meteen te installeren: de kolom *Nodig vanaf* zegt wanneer je het gebruikt. Download alleen van de officiële sites.

| Programma | Waarvoor | Nodig vanaf | Officiële site |
|---|---|---|---|
| VS Code | Notities en scripts schrijven | Unit 0 | https://code.visualstudio.com/ |
| Python 3 | Eigen scripts | Unit 0 | https://www.python.org/downloads/ |
| Git | Je repo met notities | Unit 0 | https://git-scm.com/downloads |
| Wireshark | Netwerkverkeer bekijken | Unit 2 | https://www.wireshark.org/download.html |
| Burp Suite Community | Webverkeer bekijken in de PortSwigger-labs | Unit 5 | https://portswigger.net/burp/communitydownload |
| VirtualBox | Virtuele machines voor je lab | Unit 6 | https://www.virtualbox.org/wiki/Downloads |
| Kali Linux (VM) | Linux met securitytools, als VM | Unit 6 | https://www.kali.org/get-kali/ |
| Docker Desktop (optioneel) | OWASP Juice Shop draaien | Unit 6 | https://www.docker.com/products/docker-desktop/ |
| Nmap | Diensten in je eigen lab ontdekken (zit al in Kali) | Unit 6 | https://nmap.org/download |
| CyberChef | Coderen, decoderen, hashen (webtool, niets te installeren) | Unit 7 | https://gchq.github.io/CyberChef/ |

## Windows

Open **PowerShell** en voer de regels uit die je nodig hebt. `winget` zit standaard in Windows 10 en 11.

```powershell
# Basis (unit 0 t/m 2)
winget install Microsoft.VisualStudioCode
winget install Python.Python.3.12
winget install Git.Git
winget install WiresharkFoundation.Wireshark

# Later (unit 5 en 6)
winget install PortSwigger.BurpSuite.Community
winget install Oracle.VirtualBox
winget install Docker.DockerDesktop   # optioneel
```

Vindt `winget` een pakket niet, zoek dan de juiste naam op met bijvoorbeeld `winget search wireshark`, of download het programma via de officiële site uit de tabel.

## macOS

Installeer eerst [Homebrew](https://brew.sh/) als je dat nog niet hebt. Daarna in de Terminal:

```bash
# Basis (unit 0 t/m 2)
brew install python git
brew install --cask visual-studio-code
# Wireshark: download de macOS-versie via https://www.wireshark.org/download.html

# Later (unit 5 en 6)
brew install --cask burp-suite
```

**Mac met M-chip (Apple Silicon):** gebruik voor je lab [UTM](https://mac.getutm.app/) (`brew install --cask utm`) of VirtualBox 7.1 of nieuwer, en kies bij Kali de **ARM64**-versie.

## Linux (Ubuntu / Debian)

```bash
sudo apt update
sudo apt install -y python3 python3-pip git wireshark
# VS Code: https://code.visualstudio.com/  (of: sudo snap install code --classic)
# VirtualBox: https://www.virtualbox.org/wiki/Linux_Downloads
```

## Je repo naar je computer halen

```bash
git clone https://github.com/brunodinnissen/-learnhacking.git
cd -learnhacking
```

Na elke write-up:

```bash
git add notities/
git commit -m "Write-up: <naam van de uitdaging>"
git push
```

## Kali Linux in VirtualBox (unit 6)

1. Download op https://www.kali.org/get-kali/ onder *Virtual Machines* de **VirtualBox**-versie.
2. Pak het archief uit en dubbelklik op het `.vbox`-bestand. Hij verschijnt dan in VirtualBox.
3. Start de VM. De standaard login staat op de downloadpagina. Verander het wachtwoord meteen met `passwd`.
4. Installeer de updates: `sudo apt update && sudo apt full-upgrade -y`.
5. Maak een snapshot: *Machine → Snapshot maken*, met de naam `schone installatie`.

## OWASP Juice Shop (unit 6)

Met Docker:

```bash
docker run --rm -p 127.0.0.1:3000:3000 bkimminich/juice-shop
```

Open daarna http://localhost:3000 in je browser. Door `127.0.0.1:` is de shop alleen vanaf je eigen computer bereikbaar.
Zonder Docker: volg de Node.js-instructies op https://owasp.org/www-project-juice-shop/.
