# Tactigon SDK con Docker - Guida all'Installazione

Questa guida spiega come eseguire Tactigon SDK con Docker su Linux senza dover effettuare configurazioni aggiuntive come l’installazione di Python o altri software.

---

## Indice
- [Tactigon SDK con Docker - Guida all'Installazione](#tactigon-sdk-con-docker---guida-allinstallazione)
  - [Indice](#indice)
  - [Scopo](#scopo)
  - [Campo di Applicazione](#campo-di-applicazione)
  - [Definizioni e Abbreviazioni](#definizioni-e-abbreviazioni)
  - [Riferimenti Applicabili](#riferimenti-applicabili)
  - [Istruzioni per l'Installazione di Docker e l'Esecuzione di Tactigon SDK](#istruzioni-per-linstallazione-di-docker-e-lesecuzione-di-tactigon-sdk)
    - [Step 1: Installare Docker e Docker Compose (se non esistono)](#step-1-installare-docker-e-docker-compose-se-non-esistono)
    - [Step 2: Clonare il Progetto Tactigon SDK](#step-2-clonare-il-progetto-tactigon-sdk)
    - [Step 3: Build ed Esecuzione del Container Docker](#step-3-build-ed-esecuzione-del-container-docker)
  - [Conclusione](#conclusione)

---

## Scopo
L'obiettivo di questo documento è eseguire Tactigon SDK con Docker senza dover effettuare configurazioni complesse o installare software aggiuntivi come Python.

---

## Campo di Applicazione
Questo documento fornisce le istruzioni per installare Docker su Linux e per eseguire Tactigon SDK tramite Docker.

---

## Definizioni e Abbreviazioni
- **Docker**: Piattaforma software che consente di creare, testare e distribuire applicazioni utilizzando container.  
- **Docker Compose**: Strumento per definire ed eseguire applicazioni multi-container in modo semplice.

---

## Riferimenti Applicabili
- [Sito Ufficiale di Docker per l'Installazione](https://docs.docker.com/get-docker/)

---

## Istruzioni per l'Installazione di Docker e l'Esecuzione di Tactigon SDK

### Step 1: Installare Docker e Docker Compose (se non esistono)

1. **Rimuovere eventuali pacchetti in conflitto:**

   ```bash
   for pkg in docker.io docker-doc docker-compose docker-compose-v2 podman-docker containerd runc; do sudo apt-get remove $pkg; done
   ```

2. **Configurare il repository apt di Docker:**

   ```bash
   sudo apt-get update
   sudo apt-get install ca-certificates curl
   sudo install -m 0755 -d /etc/apt/keyrings
   sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
   sudo chmod a+r /etc/apt/keyrings/docker.asc
   ```

3. **Aggiungere il repository di Docker alle sorgenti di apt:**

   ```bash
   echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
   sudo apt-get update
   ```

4. **Installare Docker e Docker Compose:**

   ```bash
   sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
   ```

5. **Verificare l'installazione:**

   ```bash
   docker version
   docker compose version
   ```

---

### Step 2: Clonare il Progetto Tactigon SDK
  
1. Nel terminale, eseguire il seguente comando:

   ```bash
   git clone https://github.com/TactigonTeam/Tactigon-SDK.git
   cd Tactigon-SDK
   ```


---

### Step 3: Build ed Esecuzione del Container Docker

1. Eseguire il contenitore utilizzando il seguente comando:

   ```bash
   sudo docker compose up --build
   ```

---

## Conclusione
Seguendo questi passaggi, è possibile eseguire con successo Tactigon SDK su un sistema Linux utilizzando Docker, garantendo un ambiente coerente senza configurazioni manuali delle dipendenze.
