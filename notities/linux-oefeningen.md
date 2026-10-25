# Linux-oefeningen (unit 1, les 6)

Deze oefeningen doe je in **Ubuntu (WSL)** op je eigen computer. Typ alles zelf over in plaats van te kopiëren: zo onthoud je het beter. Schrijf bij elke opdracht in je spiekbriefje wat het commando doet.

Begin in je thuismap met een eigen oefenmap:

```bash
cd ~
mkdir oefenen
cd oefenen
```

---

## Deel A: bestandsrechten (± 25 min)

1. Maak een bestand en bekijk de rechten:
   ```bash
   echo "mijn eerste bestand" > notitie.txt
   ls -l notitie.txt
   ```
   Je ziet iets als `-rw-r--r--`. Het eerste teken zegt wat het is (`-` = bestand, `d` = map). Daarna volgen drie groepjes van drie tekens: voor **de eigenaar**, **de groep** en **alle anderen**.
   **Vraag:** wie mag dit bestand lezen? Wie mag erin schrijven?

2. Maak het bestand privé:
   ```bash
   chmod 600 notitie.txt
   ls -l notitie.txt
   ```
   **Vraag:** wat is er veranderd? Wat betekenen de cijfers 6 en 0? (Tip: r = 4, w = 2, x = 1. Tel ze op.)

3. Maak een klein script en probeer het uit te voeren:
   ```bash
   echo 'echo "Hallo vanuit mijn script"' > hallo.sh
   ./hallo.sh
   ```
   Je krijgt `Permission denied`. Geef het bestand uitvoerrechten en probeer het opnieuw:
   ```bash
   chmod +x hallo.sh
   ls -l hallo.sh
   ./hallo.sh
   ```
   **Vraag:** welke letter is erbij gekomen in `ls -l`?

4. Wie ben je, en in welke groepen zit je?
   ```bash
   whoami
   id
   sudo whoami
   ```
   **Vraag:** waarom geeft `sudo whoami` een ander antwoord dan `whoami`?

5. Sommige bestanden zijn alleen voor root:
   ```bash
   ls -l /etc/shadow
   cat /etc/shadow
   ```
   **Vraag:** waarom krijg je `Permission denied`? Zoek op wat er in `/etc/shadow` staat en waarom het belangrijk is dat gewone gebruikers dat niet kunnen lezen.

---

## Deel B: processen en logbestanden (± 20 min)

1. Bekijk welke processen er draaien:
   ```bash
   ps aux | head
   top
   ```
   Je sluit `top` af met `q`.

2. Start een proces op de achtergrond, zoek het op en stop het:
   ```bash
   sleep 300 &
   jobs
   ps aux | grep sleep
   ```
   Zoek in de uitvoer het **PID** (het nummer in de tweede kolom) van `sleep 300` en stop het proces:
   ```bash
   kill <PID>
   jobs
   ```

3. Zorg dat er iets in de logs komt, en bekijk ze:
   ```bash
   sudo apt update
   ls /var/log
   tail -n 20 /var/log/dpkg.log
   ```
   **Vraag:** wat houdt `dpkg.log` bij?

4. Filter met een pipe:
   ```bash
   grep "status installed" /var/log/dpkg.log | tail -n 5
   grep -c "status installed" /var/log/dpkg.log
   ```
   **Vraag:** wat doet `-c` bij `grep`?

---

## Deel C: downloaden, bewerken en je spiekbriefje (± 20 min)

1. Haal de headers van een website op (dit gebruik je weer in unit 2):
   ```bash
   curl -I https://www.python.org
   ```
   **Vraag:** welke statuscode krijg je terug?

2. Download een bestand en bekijk het:
   ```bash
   curl -o robots.txt https://www.python.org/robots.txt
   cat robots.txt
   ```

3. Je Windows-bestanden staan in WSL onder `/mnt/c`. Kopieer het oefen-logbestand uit je repo (vervang `<jouw-gebruikersnaam>` door je eigen Windows-gebruikersnaam; staat er een spatie in, laat de aanhalingstekens dan staan):
   ```bash
   cp "/mnt/c/Users/<jouw-gebruikersnaam>/Documents/-learnhacking/notities/voorbeeld-auth.log" .
   grep -c "Failed password" voorbeeld-auth.log
   ```
   **Vraag:** hoeveel mislukte inlogpogingen staan er in het bestand? (In unit 3 schrijf je hier een Python-script voor.)

4. Tekst bewerken met `nano`:
   ```bash
   nano spiekbriefje.txt
   ```
   Schrijf je **15 belangrijkste commando's** op, elk met één regel uitleg. Opslaan doe je met `Ctrl+O` en Enter. Afsluiten doe je met `Ctrl+X`.

5. Zet je spiekbriefje ook in je repo, bijvoorbeeld als `notities/spiekbriefje-linux.md`, en push het.

---

## Klaar?

Vink de stappen af in de app en doe de quiz. Stuur je antwoorden op de vragen hierboven naar Claude als je ze wilt laten nakijken.
