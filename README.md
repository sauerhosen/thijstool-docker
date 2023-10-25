
---

# Installatie en gebruik van de Thijstool met Docker Compose op een Raspberry Pi

## Stap 1: Installeren van Docker op Raspberry Pi
1. Voer het volgende commando in het systeem helemaal up-to-date te maken: `sudo apt-get update && sudo apt-get upgrade`
2. Download Docker met het volgende commando: `curl -fsSL https://get.docker.com -o get-docker.sh`
3. Installeer Docker met hte volgende commando: `sudo sh get-docker.sh`
4. Wacht tot het installatieproces is voltooid.
5. Voeg je gebruikersnaam toe aan de Dockers groep (anders moet je straks steeds `sudo` gebruiken) met het volgende command: `sudo usermod -aG docker jegebruikersnaam` 
6. Test of Docker werkt met het volgende commando: `docker run hello-world`. Als alles goed werkt dan wordt er een Docker image gedownload en een "Hello from Docker!" bericht wordt getoond.

## Stap 3: Zenrows API key
Goed bezig! Ga nu naar zenrows.com en maar een gratis proefaccount aan. Je ziet na het aanmelden meteen een API key, kopieer deze. Je hebt hem in de volgende stap nodig. 

## Stap 3: Downloaden en instellen van docker-compose.yml bestand
1. Docker Compose gebruikt het bestand **docker-compose.yml** om een Docker image te downloaden, te configueren en te starten. Download eerst het **docker-compose.yml** met het volgende commando: `git clone https://github.com/sauerhosen/thijstool-docker.git`
2. Ga naar de directory waarin het **docker-compose.yml** gedownload is: `cd thijstool-docker`.
3. Open een teksteditor om de instellingen te wijzigen: `nano docker-compose.yml`
4. Vul je eigen IP (externe) adres of domeinnaam in
5. Vul je eigen Zenrows API key in 
6. [Optioneel:] Wijzig de port, bijv naar 443 
7. Sla het bestand `docker-compose.yml` op en sluit de teksteditor (Ctrl-x, gevolgd door y om op te slaa).

## Stap 4: Downloaden en starten van Thijstool image
1. Voer het commando `docker compose pull` in om de image sauerhosen/thijstool-docker te downloaden
2. Als het downloaden afgerond is, start je de tool met het commando `docker compose up -d` 
3. Als alles goed is gegaan, zie je iets dit op je scherm: 
    > ✔ Container podimo             Started
4. Om de tool te stoppen, type: `docker compose down`


## Stap 5: Controleer de logs of de tool werkt
1. Voer het commando `docker compose logs -f` in om de logs te bekijken. 
2. Sluit de logs met Ctrl-C

## [Stap 6 - Optioneel]: Controleer op updates van de tool
1. Voer het commando `docker compose pull` in om evt. nieuwe images van de de Thijstool te downloaden
2. Als het downloaden afgerond is, start je de nieuwe versie van de tool weer met het commando `docker compose up -d` 


Gefeliciteerd! Je hebt de Thijstool in Docker draaien. 

Veel luisterplezier! Vergeet je de [koffie voor Thijs](https://www.buymeacoffee.com/thijsr) niet? En nogmaals: als je er niet uitkomt is er in de Telegram groep altijd wel iemand die wil helpen. Durf te vragen. 😊