
---

# Installatie en gebruik van Docker Compose op een Raspberry Pi

## Stap 1: Installeren van Docker op Raspberry Pi
1. Voer het volgende commando in het systeem helemaal up-to-date te maken: `sudo apt-get update && sudo apt-get upgrade`
2. Download Docker met het volgende commando: `curl -fsSL https://get.docker.com -o get-docker.sh`
3. Installeer Docker met hte volgende commando: `sudo sh get-docker.sh`
4. Wacht tot het installatieproces is voltooid.
5. Voeg je gebruikersnaam toe aan de Dockers groep (anders moet je straks steeds `sudo` gebruiken) met het volgende command: `sudo usermod -aG docker jegebruikersnaam` 
6. Test of Docker werkt met het volgende commando: `docker run hello-world`. Als alles goed werkt dan wordt er een Docker image gedownload en een "Hello from Docker!" bericht wordt getoond.


## Stap 2: Downloaden en instellen van docker- compose.yml bestand
1. Docker Compose gebruikt het bestand **docker-compose.yml** om een Docker image te downloaden, te configueren en te starten. Download eerst het **docker-compose.yml** met het volgende commando: `git clone `
2. Wacht tot het installatieproces is voltooid.

## Stap 3: Controleren van de installatie
1. Voer het commando `docker compose version` in om te controleren of Docker Compose correct is geïnstalleerd.
2. Je zou de versie van Docker Compose moeten zien die je zojuist hebt geïnstalleerd.

## Stap 4: Uitvoeren van een Docker-afbeelding met Docker Compose
1. Maak een nieuw bestand `docker-compose.yml` aan met de volgende inhoud:

    ```yaml
    version: '3'
    services:
    app:
        image: okkepodimo/image-name
        ports:
        - 1234:80
    ```

   Vervang `okkepodimo/image-name` door de werkelijke naam van de Docker-afbeelding die je wilt downloaden. Zorg ervoor dat de afbeelding beschikbaar is in een Docker-registry.

2. Sla het bestand `docker-compose.yml` op en sluit de teksteditor.

## Stap 5: Starten en uitvoeren van de Docker-afbeelding
1. Ga naar de terminal of SSH-client en navigeer naar de locatie waar je het `docker-compose.yml`-bestand hebt opgeslagen.
2. Voer het commando `docker compose up` in om de Docker-afbeelding te downloaden en starten.
3. Wacht tot het proces is voltooid en controleer de uitvoer op eventuele foutmeldingen of meldingen.

Gefeliciteerd! Je hebt