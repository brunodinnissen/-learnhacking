# Leerpad Ethisch Hacken

Mijn persoonlijke leerpad om ethisch hacken te leren: elke dag een uurtje (of minder als het druk is), in een vaste volgorde, met voortgang die ik kan bijhouden.

## Hoe het werkt

1. **Open de leerapp** (`app/leerpad.html`, gepubliceerd als Claude-artifact). Daarin staan:
   - **Vandaag**: je dagplan. Kies hoeveel tijd je hebt (15–90 min) en de app kiest de volgende stappen die daarin passen.
   - **Leerpad**: 11 units en 52 lessen op een rij, van de basis naar gevorderd.
   - **Gereedschap**: alle programma's en gratis oefenplatforms, met per item de unit waarin je het nodig hebt.
   - **Voortgang**: XP, niveau, weekreeks, activiteit en badges.
   - **Instellingen**: dagtijd, weekdoel en een back-up van je voortgang.
2. **Vink stappen af** als je ze gedaan hebt. Na elke les volgt een korte quiz.
3. **Weinig tijd?** Doe een *korte herhaling* (5 vragen, ongeveer 8 minuten). Die telt ook als actieve dag.
4. **Schrijf write-ups** in de map [`notities/`](notities/) met het [template](notities/_template-writeup.md).

### Flexibel met tijd

- De **weekreeks** telt hoeveel weken op rij je je weekdoel haalt. Heb je een drukke periode, zet je weekdoel dan op bijvoorbeeld 3 dagen. Je reeks blijft gewoon staan.
- Lessen bestaan uit stappen van 5 tot 45 minuten. Met 15 minuten per dag kom je dus ook vooruit, alleen langzamer.

## De route

| Unit | Onderwerp | Waar je oefent |
|---|---|---|
| 0 | Start & spelregels: wat mag wel en niet, werkplek klaarzetten | – |
| 1 | Linux & de terminal | TryHackMe, OverTheWire Bandit |
| 2 | Netwerken: IP, TCP/UDP, DNS, HTTP, Wireshark | TryHackMe Pre Security, Wireshark |
| 3 | Python, met twee mini-projecten | Python for Everybody |
| 4 | Het web van binnenuit: HTTP, cookies, SQL, OWASP Top 10 | MDN, SQLBolt, OWASP |
| 5 | Websecurity | PortSwigger Web Security Academy |
| 6 | Je eigen lab: VirtualBox, Kali, Juice Shop, Nmap | Je eigen computer |
| 7 | Cryptografie | CyberChef, CryptoHack |
| 8 | Capture the Flag | picoCTF, CTFtime |
| 9 | Verdedigen (blue team) | Je eigen VM, Wireshark, TryHackMe SOC |
| 10 | Het volgende niveau | Hack The Box Starting Point, Hacker101 |

Bij een uur per dag en 5 dagen per week duurt het hele pad ongeveer 3 maanden.

## Spelregels

Ik oefen **alleen** op systemen die van mij zijn of waarvoor ik uitdrukkelijk toestemming heb: mijn eigen VM's en lab, en oefenplatforms die daarvoor gemaakt zijn. Hacken zonder toestemming is strafbaar (computervredebreuk, art. 138ab Sr). Vind ik ergens per ongeluk een lek, dan test ik niet verder en meld ik het netjes (coordinated vulnerability disclosure). Zie ook [`notities/hackerscode.md`](notities/hackerscode.md).

Alles in dit pad is gratis. Er is geen betaald abonnement nodig.

## Mappen

```
app/leerpad.html        de leerapp (bron van het artifact)
SETUP.md                alle programma's installeren, per besturingssysteem
notities/               write-ups, spiekbriefjes en de hackerscode
  _template-writeup.md  vaste opbouw voor een write-up
  voorbeeld-auth.log    nep-logbestand voor het Python-project in unit 3
scripts/                je eigen Python-scripts
```
