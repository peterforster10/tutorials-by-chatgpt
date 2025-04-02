# **Umfassendes Tutorial: Kubernetes (K3s) auf einem Ubuntu-Server mit einer Express REST API und externer PostgreSQL-Datenbank**  

## **1. Einführung**  
   - Ziel des Tutorials  
   - Was ist Kubernetes (K3s)?  
   - Warum K3s für einen einzelnen Server?  
   - Überblick über die geplante Architektur (Express API + externe PostgreSQL)  

## **2. Voraussetzungen**  
   - Hardware/Software-Anforderungen  
   - Ubuntu Server (aktuelle LTS-Version)  
   - Grundlegende Linux- und Docker-Kenntnisse  
   - SSH-Zugang zum Server  

## **3. Installation und Einrichtung von K3s**  
   - **3.1. Installation von K3s**  
     - Einzeilige Installation mit `curl`  
     - Verifizierung der Installation (`kubectl get nodes`)  
   - **3.2. Konfiguration von `kubectl`**  
     - Benutzerberechtigungen (Zugriff ohne `sudo`)  
     - Überprüfen des Cluster-Status  
   - **3.3. Optional: Kubernetes-Dashboard einrichten**  

## **4. Einrichtung der externen PostgreSQL-Datenbank**  
   - **4.1. Installation von PostgreSQL auf dem Host-System**  
     - Installation über `apt`  
     - Konfiguration (`pg_hba.conf`, `postgresql.conf`)  
   - **4.2. Datenbank und Benutzer anlegen**  
     - Erstellen einer Datenbank für die Express-API  
     - Anlegen eines dedizierten Benutzers mit Berechtigungen  
   - **4.3. Absicherung der PostgreSQL-Instanz**  
     - Firewall-Regeln (nur lokaler Zugriff)  
     - TLS/SSL-Optionen (falls Remote-Zugriff benötigt wird)  

## **5. Entwicklung der Express REST API**  
   - **5.1. Projektstruktur erstellen**  
     - Grundgerüst einer Node.js/Express-Anwendung  
     - Abhängigkeiten (`express`, `pg`, `dotenv`)  
   - **5.2. Verbindung zur PostgreSQL-Datenbank**  
     - Konfiguration des Connection-Pools  
     - Environment-Variablen für DB-Zugriff  
   - **5.3. Implementierung einer einfachen REST-API**  
     - CRUD-Endpoints (z. B. `/users`)  
     - Beispiel-Datenmodell  

## **6. Containerisierung der Express-Anwendung mit Docker**  
   - **6.1. Erstellung des `Dockerfile`**  
     - Multi-Stage Build für optimierte Images  
     - Nutzung von `node:alpine`  
   - **6.2. Bauen und Testen des Docker-Images**  
     - Lokales Ausführen mit `docker run`  
     - Verbindungstest zur PostgreSQL-DB  

## **7. Deployment der Anwendung auf K3s**  
   - **7.1. Erstellung von Kubernetes-Manifesten**  
     - **Deployment** (Express-API)  
     - **Service** (ClusterIP / NodePort / LoadBalancer)  
     - **ConfigMap & Secrets** (für Umgebungsvariablen)  
   - **7.2. Anwendung im Cluster bereitstellen**  
     - `kubectl apply -f deployment.yaml`  
     - Überprüfung der Pods (`kubectl get pods`)  
   - **7.3. Zugriff auf die API testen**  
     - Port-Forwarding (`kubectl port-forward`)  
     - Externe Erreichbarkeit (via NodePort oder Ingress)  

## **8. Optional: Persistenz und Skalierung**  
   - **8.1. Persistente Volumes für zukünftige Anwendungen**  
     - Nutzung von `Local Path Provisioner` in K3s  
   - **8.2. Horizontale Skalierung der Express-API**  
     - Auto-Scaling mit `kubectl scale`  

## **9. Monitoring und Wartung**  
   - **9.1. Logging**  
     - Anzeigen der Pod-Logs (`kubectl logs`)  
   - **9.2. Monitoring-Tools (Prometheus/Grafana mit K3s)**  
     - Einfache Metriken-Sammlung  

## **10. Sicherheitsbest Practices**  
   - **10.1. Absicherung von K3s**  
     - RBAC-Konfiguration  
     - Netzwerk-Policies (falls `cilium`/`calico` installiert)  
   - **10.2. Sichere Kommunikation mit PostgreSQL**  
     - TLS-Verschlüsselung  
     - Firewall-Regeln  

## **11. Troubleshooting & häufige Probleme**  
   - Verbindungsprobleme zwischen API und PostgreSQL  
   - K3s-Installationsfehler  
   - Ressourcenengpässe (CPU/Memory)  

## **12. Fazit & nächste Schritte**  
   - Zusammenfassung des Deployments  
   - Erweiterungsmöglichkeiten (CI/CD, Ingress, HA-Setup)  
   - Weiterführende Ressourcen  

---

### **Anhang**  
- **Beispiel-Code** (Express API, Dockerfile, Kubernetes-Manifeste)  
- **Nützliche Befehle** (kubectl, docker, psql)  
- **Referenz-Links** (Offizielle K3s-Doku, PostgreSQL-Guides)  

---

Diese Gliederung bietet eine schrittweise Anleitung, um eine **Express REST API auf K3s** mit einer **externen PostgreSQL-Datenbank** auf einem einzelnen Ubuntu-Server zu betreiben. Solltest du spezifische Anpassungen wünschen, lass es mich wissen! 🚀



## **1. Einführung**  

### **Ziel des Tutorials**  
Dieses Tutorial führt dich Schritt für Schritt durch die Einrichtung eines **Kubernetes-Clusters mit K3s** auf einem einzelnen **Ubuntu-Server**, auf dem eine **Express REST API** läuft. Die Datenbank (**PostgreSQL**) wird als externer Service betrieben, befindet sich jedoch auf demselben Server, um die Ressourcennutzung zu optimieren.  

Am Ende dieses Guides wirst du in der Lage sein:  
✅ Einen **K3s-Cluster** auf einem Ubuntu-Server zu installieren.  
✅ Eine **Express.js-API** zu entwickeln und in einem **Docker-Container** auszuführen.  
✅ Eine **PostgreSQL-Datenbank** extern (außerhalb von Kubernetes) zu betreiben und mit der API zu verbinden.  
✅ Die Anwendung **mittels Kubernetes-Manifesten** zu deployen und zu verwalten.  

### **Was ist Kubernetes (K3s)?**  
Kubernetes (K8s) ist ein Open-Source-Container-Orchestrierungssystem zur Automatisierung der Bereitstellung, Skalierung und Verwaltung von containerisierten Anwendungen.  

**K3s** ist eine **leichtgewichtige Kubernetes-Distribution** von Rancher Labs, die speziell für Edge-Computing, IoT und ressourcenbeschränkte Umgebungen optimiert ist. Im Vergleich zu Standard-Kubernetes:  
- **Geringerer Ressourcenverbrauch** (ideal für Single-Node-Setups).  
- **Einfachere Installation** (ein einziger Befehl).  
- **Vorkonfigurierte Komponenten** (inkl. Containerd, Traefik als Ingress-Controller).  

### **Warum K3s für einen einzelnen Server?**  
- **Minimaler Overhead**: Ideal für Entwicklungs- und Testumgebungen.  
- **Einfache Verwaltung**: Kein komplexes Multi-Node-Setup nötig.  
- **Production-ready**: Trotz Einfachheit stabil und für kleine Produktionsworkloads geeignet.  

### **Überblick über die Architektur**  
Die geplante Infrastruktur sieht wie folgt aus:  
1. **Ubuntu Server** als Host-System.  
2. **K3s** als Kubernetes-Engine.  
3. **Express REST API** in einem Kubernetes-Pod (containerisiert).  
4. **PostgreSQL** als externer Dienst (außerhalb von K8s, aber auf demselben Server).  

```
+-------------------------------+
| Ubuntu Server                 |
|   +------------------------+ |
|   | K3s Cluster            | |
|   |   +------------------+ | |
|   |   | Express API (Pod)| | |
|   |   +------------------+ | |
|   +------------------------+ |
|                               |
|   +------------------------+ |
|   | PostgreSQL (extern)    | |
|   +------------------------+ |
+-------------------------------+
```

Im nächsten Abschnitt gehen wir auf die **Voraussetzungen** ein, bevor wir mit der Installation beginnen.  

---  
**➡️ Weiter zu [2. Voraussetzungen](#2-voraussetzungen)**  

*(Hinweis: Dieser Aufbau ermöglicht später eine einfache Migration der Datenbank in einen separaten Server oder Managed Service wie AWS RDS.)*




## **2. Voraussetzungen**  

Bevor wir mit der Installation von **K3s**, der **Express REST API** und **PostgreSQL** beginnen, müssen folgende Voraussetzungen erfüllt sein.  

---

### **2.1. Hardware- & Software-Anforderungen**  
#### **Minimale Systemanforderungen:**  
- **Betriebssystem:** Ubuntu Server 22.04 LTS oder 24.04 LTS (amd64/arm64)  
- **CPU:** 1–2 vCPUs (mindestens x86_64 oder ARMv8)  
- **RAM:** 2 GB (4 GB empfohlen für bessere Performance)  
- **Speicher:** 20 GB freier Festplattenspeicher  
- **Netzwerk:** Internetzugang für Paketinstallationen  

#### **Empfohlene Umgebung für Produktion:**  
- **CPU:** 2–4 vCPUs  
- **RAM:** 4 GB+  
- **SSD-Speicher** für bessere Datenbank-Performance  

---

### **2.2. Ubuntu Server vorbereiten**  
#### **1. Systemaktualisierung durchführen**  
```bash
sudo apt update && sudo apt upgrade -y
sudo apt install -y curl wget git docker.io
```  

#### **2. Firewall konfigurieren (falls aktiviert)**  
```bash
sudo ufw allow 22/tcp          # SSH
sudo ufw allow 6443/tcp       # Kubernetes API
sudo ufw allow 5432/tcp       # PostgreSQL (falls remote zugänglich)
sudo ufw enable
```  

#### **3. Docker als Laufzeitumgebung nutzen (optional, falls nicht containerd)**  
```bash
sudo systemctl enable --now docker
```  

*(K3s verwendet standardmäßig **containerd**, aber Docker kann manuell als Laufzeit eingebunden werden.)*  

---

### **2.3. SSH-Zugang & Benutzerberechtigungen**  
- **SSH-Zugriff** auf den Server sollte eingerichtet sein.  
- **Sudo-Berechtigungen** für den Benutzer:  
  ```bash
  sudo usermod -aG sudo $USER
  ```  
- **Ohne Passwort-Sudo (optional für Skripte):**  
  ```bash
  echo "$USER ALL=(ALL) NOPASSWD:ALL" | sudo tee /etc/sudoers.d/$USER
  ```  

---

### **2.4. Optional: PostgreSQL vorinstallieren (falls nicht später gewünscht)**  
Falls PostgreSQL direkt auf dem Host laufen soll (nicht in Kubernetes), kann es vorab installiert werden:  
```bash
sudo apt install -y postgresql postgresql-contrib
sudo systemctl enable --now postgresql
```  

*(Hinweis: Die detaillierte PostgreSQL-Konfiguration folgt in [Abschnitt 4](#4-einrichtung-der-externen-postgresql-datenbank).)*  

---

### **2.5. Überprüfung der Umgebung**  
- **Kernel-Version:**  
  ```bash
  uname -r  # Mindestens 5.x empfohlen
  ```  
- **Docker-Laufzeit testen:**  
  ```bash
  docker run hello-world
  ```  
- **Speicher & CPU prüfen:**  
  ```bash
  free -h && lscpu
  ```  

---

### **Zusammenfassung**  
✅ Aktuelles Ubuntu-System mit SSH-Zugang  
✅ Docker/containerd als Container-Laufzeit  
✅ Firewall-Regeln für Kubernetes & PostgreSQL  
✅ Optional: PostgreSQL vorinstalliert  

**➡️ Im nächsten Abschnitt installieren wir K3s: [3. Installation und Einrichtung von K3s](#3-installation-und-einrichtung-von-k3s).**  

*(Falls Probleme auftreten, siehe [Abschnitt 11: Troubleshooting](#11-troubleshooting-häufige-probleme).)*



## **3. Installation und Einrichtung von K3s**  

In diesem Abschnitt installieren wir **K3s** – die leichtgewichtige Kubernetes-Distribution – auf unserem Ubuntu-Server und richten die notwendigen Tools für die Verwaltung ein.

---

### **3.1. Installation von K3s**  
K3s kann mit einem einzigen Befehl installiert werden:

#### **1. K3s installieren (mit containerd als Laufzeit)**
```bash
curl -sfL https://get.k3s.io | sh -
```

#### **2. Installation verifizieren**
```bash
sudo k3s kubectl get nodes
```
Erwartete Ausgabe:
```
NAME        STATUS   ROLES                  AGE   VERSION
ubuntu      Ready    control-plane,master   1m    v1.28.5+k3s2
```

#### **3. K3s als Systemdienst verwalten**
```bash
sudo systemctl status k3s  # Status prüfen
sudo systemctl stop k3s    # Dienst stoppen
sudo systemctl start k3s   # Dienst starten
```

---

### **3.2. kubectl Konfiguration**  
Standardmäßig benötigt `kubectl` Root-Rechte. Wir passen dies für den normalen Benutzer an:

#### **1. kubeconfig kopieren**
```bash
mkdir -p ~/.kube
sudo cp /etc/rancher/k3s/k3s.yaml ~/.kube/config
sudo chown $USER:$USER ~/.kube/config
```

#### **2. Umgebungsvariable setzen**
```bash
export KUBECONFIG=~/.kube/config
echo 'export KUBECONFIG=~/.kube/config' >> ~/.bashrc
```

#### **3. Test des kubectl-Zugriffs**
```bash
kubectl cluster-info
kubectl get pods -A
```

---

### **3.3. Optional: Kubernetes Dashboard einrichten**  
Für eine visuelle Oberfläche installieren wir das Dashboard:

#### **1. Dashboard installieren**
```bash
GITHUB_URL=https://github.com/kubernetes/dashboard/releases
VERSION=$(curl -w '%{url_effective}' -I -L -s -S ${GITHUB_URL}/latest -o /dev/null | sed -e 's|.*/||')
kubectl apply -f https://raw.githubusercontent.com/kubernetes/dashboard/${VERSION}/aio/deploy/recommended.yaml
```

#### **2. Admin-User erstellen**
```bash
cat <<EOF | kubectl apply -f -
apiVersion: v1
kind: ServiceAccount
metadata:
  name: admin-user
  namespace: kubernetes-dashboard
EOF
```

#### **3. Zugriffstoken anzeigen**
```bash
kubectl -n kubernetes-dashboard create token admin-user
```

#### **4. Dashboard zugänglich machen**
```bash
kubectl port-forward -n kubernetes-dashboard service/kubernetes-dashboard 8080:443 --address 0.0.0.0
```
Zugriff via: `https://<server-ip>:8080` (Token-Login verwenden)

---

### **3.4. Wichtige K3s-Komponenten**  
K3s bringt bereits vorkonfigurierte Komponenten mit:
- **Traefik**: Ingress-Controller (Ports 80/443)
- **Local Path Provisioner**: Persistente Volumes
- **Metrics Server**: Ressourcenüberwachung

#### **Installierte Komponenten prüfen**
```bash
kubectl get pods -n kube-system
```

---

### **Troubleshooting**  
Falls Probleme auftreten:
- **K3s Logs einsehen**:  
  ```bash
  journalctl -u k3s -f
  ```
- **Firewall prüfen**:  
  ```bash
  sudo ufw status
  ```
- **Bei Installationsfehlern**:  
  ```bash
  sudo /usr/local/bin/k3s-uninstall.sh
  ```

---

### **Zusammenfassung**  
✅ K3s erfolgreich installiert  
✅ `kubectl` für den Benutzer konfiguriert  
✅ Optional: Kubernetes Dashboard eingerichtet  
✅ Systembereit für App-Deployment  

**➡️ Weiter zu [4. Einrichtung der externen PostgreSQL-Datenbank](#4-einrichtung-der-externen-postgresql-datenbank)**


## **4. Einrichtung der externen PostgreSQL-Datenbank**

In diesem Abschnitt richten wir eine PostgreSQL-Datenbank ein, die außerhalb von Kubernetes auf demselben Server läuft, aber von unserer Express-API in K3s genutzt werden kann.

---

### **4.1. Installation von PostgreSQL**

#### **1. PostgreSQL installieren**
```bash
sudo apt update
sudo apt install -y postgresql postgresql-contrib
```

#### **2. PostgreSQL-Dienst starten und aktivieren**
```bash
sudo systemctl start postgresql
sudo systemctl enable postgresql
```

#### **3. Installationsstatus überprüfen**
```bash
sudo systemctl status postgresql
psql --version
```

---

### **4.2. Datenbank und Benutzer anlegen**

#### **1. Zum PostgreSQL-Systembenutzer wechseln**
```bash
sudo -u postgres psql
```

#### **2. Datenbank und Benutzer erstellen**
```sql
CREATE DATABASE express_api;
CREATE USER api_user WITH PASSWORD 'sicheres_passwort';
GRANT ALL PRIVILEGES ON DATABASE express_api TO api_user;
\q
```

#### **3. Verbindungstest durchführen**
```bash
psql -h localhost -U api_user -d express_api -W
```

---

### **4.3. Konfiguration für Remote-Zugriff**

#### **1. PostgreSQL Konfigurationsdatei anpassen**
```bash
sudo nano /etc/postgresql/14/main/postgresql.conf
```
Ändern Sie:
```ini
listen_addresses = 'localhost,127.0.0.1'
```

#### **2. Zugriffsregeln anpassen**
```bash
sudo nano /etc/postgresql/14/main/pg_hba.conf
```
Fügen Sie hinzu:
```ini
# Erlaube Zugriff von Kubernetes-Pods
host    express_api    api_user    127.0.0.1/32    md5
```

#### **3. PostgreSQL neustarten**
```bash
sudo systemctl restart postgresql
```

---

### **4.4. Firewall-Konfiguration**

#### **1. Firewall für PostgreSQL öffnen (falls aktiviert)**
```bash
sudo ufw allow 5432/tcp
sudo ufw reload
```

#### **2. Portüberprüfung**
```bash
ss -tulnp | grep 5432
```

---

### **4.5. Kubernetes-Secret für Datenbankzugang**

#### **1. Secret erstellen**
```bash
kubectl create secret generic db-credentials \
  --from-literal=DB_HOST=127.0.0.1 \
  --from-literal=DB_NAME=express_api \
  --from-literal=DB_USER=api_user \
  --from-literal=DB_PASS='sicheres_passwort'
```

#### **2. Secret überprüfen**
```bash
kubectl get secrets
kubectl describe secret db-credentials
```

---

### **4.6. Verbindungstest von Kubernetes aus**

#### **1. Temporären Test-Pod erstellen**
```bash
kubectl run psql-test --rm -it --image=postgres:alpine -- /bin/sh
```

#### **2. Im Test-Pod Verbindung prüfen**
```bash
psql -h 127.0.0.1 -U api_user -d express_api -W
```

---

### **Troubleshooting**

**Problem:** Verbindungsfehler von Kubernetes-Pods  
**Lösung:**
1. PostgreSQL-Logs prüfen:
```bash
sudo tail -f /var/log/postgresql/postgresql-14-main.log
```
2. Netzwerkverbindung testen:
```bash
kubectl exec -it <pod-name> -- nc -zv 127.0.0.1 5432
```

---

### **Zusammenfassung**
✅ PostgreSQL erfolgreich installiert und konfiguriert  
✅ Datenbank und Benutzer für die Express-API angelegt  
✅ Sicherer Zugriff von Kubernetes-Pods eingerichtet  
✅ Datenbankzugangsdaten als Kubernetes-Secret gespeichert  

**➡️ Weiter zu [5. Entwicklung der Express REST API](#5-entwicklung-der-express-rest-api)**



## **5. Entwicklung der Express REST API**

In diesem Abschnitt erstellen wir eine einfache Express.js-Anwendung, die sich mit unserer PostgreSQL-Datenbank verbindet und CRUD-Endpunkte bereitstellt.

---

### **5.1. Projektstruktur erstellen**

#### **1. Projektverzeichnis anlegen**
```bash
mkdir express-api && cd express-api
npm init -y
```

#### **2. Abhängigkeiten installieren**
```bash
npm install express pg dotenv cors
npm install --save-dev nodemon
```

#### **3. Grundlegende Dateistruktur**
```
express-api/
├── .env
├── .gitignore
├── package.json
├── src/
│   ├── app.js
│   ├── server.js
│   ├── db/
│   │   └── pool.js
│   ├── routes/
│   │   └── users.js
│   └── controllers/
│       └── users.js
```

---

### **5.2. Datenbankverbindung einrichten**

#### **1. Datenbank-Pool konfigurieren (`src/db/pool.js`)**
```javascript
const { Pool } = require('pg');
require('dotenv').config();

const pool = new Pool({
  host: process.env.DB_HOST,
  database: process.env.DB_NAME,
  user: process.env.DB_USER,
  password: process.env.DB_PASS,
  port: 5432,
});

module.exports = pool;
```

#### **2. Umgebungsvariablen setzen (`.env`)**
```ini
DB_HOST=127.0.0.1
DB_NAME=express_api
DB_USER=api_user
DB_PASS=sicheres_passwort
PORT=3000
```

#### **3. .gitignore anlegen**
```ini
node_modules/
.env
```

---

### **5.3. Express-Server einrichten

#### **1. Basis-Server (`src/server.js`)**
```javascript
const app = require('./app');
const port = process.env.PORT || 3000;

app.listen(port, () => {
  console.log(`Server running on port ${port}`);
});
```

#### **2. App-Konfiguration (`src/app.js`)**
```javascript
const express = require('express');
const cors = require('cors');
const usersRouter = require('./routes/users');

const app = express();

app.use(cors());
app.use(express.json());

app.use('/api/users', usersRouter);

module.exports = app;
```

---

### **5.4. CRUD-Endpunkte implementieren

#### **1. Controller (`src/controllers/users.js`)**
```javascript
const pool = require('../db/pool');

const getAllUsers = async (req, res) => {
  try {
    const { rows } = await pool.query('SELECT * FROM users');
    res.json(rows);
  } catch (err) {
    res.status(500).send(err.message);
  }
};

const createUser = async (req, res) => {
  const { name, email } = req.body;
  try {
    const { rows } = await pool.query(
      'INSERT INTO users (name, email) VALUES ($1, $2) RETURNING *',
      [name, email]
    );
    res.status(201).json(rows[0]);
  } catch (err) {
    res.status(500).send(err.message);
  }
};

module.exports = { getAllUsers, createUser };
```

#### **2. Routes (`src/routes/users.js`)**
```javascript
const express = require('express');
const { getAllUsers, createUser } = require('../controllers/users');

const router = express.Router();

router.get('/', getAllUsers);
router.post('/', createUser);

module.exports = router;
```

---

### **5.5. Datenbanktabelle erstellen**

#### **1. SQL-Skript ausführen**
```bash
sudo -u postgres psql -d express_api -c "
CREATE TABLE IF NOT EXISTS users (
  id SERIAL PRIMARY KEY,
  name VARCHAR(100) NOT NULL,
  email VARCHAR(100) UNIQUE NOT NULL,
  created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);"
```

#### **2. Testdaten einfügen**
```bash
sudo -u postgres psql -d express_api -c "
INSERT INTO users (name, email) VALUES 
('Max Mustermann', 'max@example.com'),
('Erika Musterfrau', 'erika@example.com');"
```

---

### **5.6. Entwicklungsserver starten**

#### **1. package.json Skripte hinzufügen**
```json
"scripts": {
  "start": "node src/server.js",
  "dev": "nodemon src/server.js"
}
```

#### **2. Anwendung testen**
```bash
npm run dev
```

#### **3. Endpunkte testen**
```bash
curl http://localhost:3000/api/users
curl -X POST -H "Content-Type: application/json" -d '{"name":"Test","email":"test@example.com"}' http://localhost:3000/api/users
```

---

### **5.7. Fehlerbehandlung erweitern**

#### **1. Middleware für Fehlerbehandlung (`src/app.js`)**
```javascript
// Nach den Routes
app.use((err, req, res, next) => {
  console.error(err.stack);
  res.status(500).send('Something broke!');
});
```

#### **2. Validierungsmiddleware (`src/middleware/validate.js`)**
```javascript
const validateUser = (req, res, next) => {
  if (!req.body.name || !req.body.email) {
    return res.status(400).json({ error: 'Name and email are required' });
  }
  next();
};

module.exports = { validateUser };
```

---

### **Zusammenfassung**
✅ Express.js-Projekt mit vollständiger CRUD-API erstellt  
✅ PostgreSQL-Datenbankanbindung implementiert  
✅ Strukturierte Code-Organisation mit Routes und Controllern  
✅ Entwicklungsumgebung mit Hot-Reload eingerichtet  

**➡️ Weiter zu [6. Containerisierung der Express-Anwendung mit Docker](#6-containerisierung-der-express-anwendung-mit-docker)**



## **6. Containerisierung der Express-Anwendung mit Docker**

In diesem Abschnitt verpacken wir unsere Express-Anwendung in einen Docker-Container, der später in unser K3s-Cluster deployed werden kann.

---

### **6.1. Dockerfile erstellen**

#### **1. Basis-Dockerfile (optimiert für Produktion)**
```dockerfile
# Build-Stage
FROM node:18-alpine AS builder
WORKDIR /app
COPY package*.json ./
RUN npm ci
COPY . .
RUN npm run build || echo "Kein Build-Skript vorhanden"

# Runtime-Stage
FROM node:18-alpine
WORKDIR /app
ENV NODE_ENV=production

# Nur notwendige Dateien kopieren
COPY --from=builder /app/node_modules ./node_modules
COPY --from=builder /app/package*.json ./
COPY --from=builder /app/src ./src
COPY --from=builder /app/.env ./

# Sicherheitsoptimierungen
RUN apk add --no-cache tini
USER node
EXPOSE 3000
ENTRYPOINT ["/sbin/tini", "--"]
CMD ["node", "src/server.js"]
```

#### **2. .dockerignore hinzufügen**
```ini
node_modules
npm-debug.log
.git
.env.local
Dockerfile
.dockerignore
```

---

### **6.2. Docker Build optimieren**

#### **1. Multi-Stage Build für Entwicklung**
```dockerfile
# Development-Stage
FROM node:18-alpine AS dev
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
EXPOSE 3000
CMD ["npm", "run", "dev"]
```

#### **2. Build-Argumente für unterschiedliche Umgebungen**
```dockerfile
ARG NODE_ENV=production
ENV NODE_ENV=${NODE_ENV}
```

---

### **6.3. Docker-Compose für lokale Entwicklung**

#### **1. docker-compose.yml erstellen**
```yaml
version: '3.8'

services:
  api:
    build:
      context: .
      target: dev
    volumes:
      - ./:/app
      - /app/node_modules
    ports:
      - "3000:3000"
    environment:
      - NODE_ENV=development
    depends_on:
      - db

  db:
    image: postgres:15-alpine
    environment:
      POSTGRES_DB: express_api
      POSTGRES_USER: api_user
      POSTGRES_PASSWORD: sicheres_passwort
    volumes:
      - postgres_data:/var/lib/postgresql/data
    ports:
      - "5432:5432"

volumes:
  postgres_data:
```

#### **2. Kommandos für die lokale Entwicklung**
```bash
docker-compose build  # Images erstellen
docker-compose up    # Container starten
docker-compose down  # Container stoppen
```

---

### **6.4. Image bauen und testen**

#### **1. Produktions-Image bauen**
```bash
docker build -t express-api:1.0.0 .
```

#### **2. Container testen**
```bash
docker run -p 3000:3000 \
  -e DB_HOST=host.docker.internal \
  -e DB_NAME=express_api \
  -e DB_USER=api_user \
  -e DB_PASS=sicheres_passwort \
  express-api:1.0.0
```

#### **3. Image verifizieren**
```bash
docker images
docker history express-api:1.0.0
```

---

### **6.5. Sicherheitsbest Practices**

#### **1. Nicht-root User verwenden**
```dockerfile
RUN addgroup -S appgroup && adduser -S appuser -G appgroup
USER appuser
```

#### **2. Image Scanning durchführen**
```bash
docker scan express-api:1.0.0
```

#### **3. Signaturen verifizieren**
```dockerfile
COPY --chown=appuser:appgroup . .
```

---

### **6.6. Push zu einer Container Registry**

#### **1. Tagging für Docker Hub**
```bash
docker tag express-api:1.0.0 <username>/express-api:1.0.0
```

#### **2. Authentifizierung und Push**
```bash
docker login
docker push <username>/express-api:1.0.0
```

#### **3. Alternative: Lokale Registry in K3s**
```bash
k3s crictl pull express-api:1.0.0
```

---

### **Troubleshooting**

**Problem:** Container startet nicht  
**Lösung:**
```bash
docker logs <container-id>
docker inspect <container-id>
```

**Problem:** Datenbankverbindung fehlgeschlagen  
**Lösung:**
```bash
docker exec -it <container-id> sh
nc -zv host.docker.internal 5432
```

---

### **Zusammenfassung**
✅ Multi-Stage Dockerfile für Entwicklung und Produktion  
✅ Docker-Compose für lokale Entwicklung mit DB  
✅ Sicherheitsoptimierte Container-Konfiguration  
✅ Image-Build und Push zu einer Registry  

**➡️ Weiter zu [7. Deployment der Anwendung auf K3s](#7-deployment-der-anwendung-auf-k3s)**



## **7. Deployment der Anwendung auf K3s**

In diesem Abschnitt deployen wir unsere containerisierte Express-Anwendung in den K3s-Cluster und machen sie über einen Service zugänglich.

---

### **7.1. Kubernetes Manifeste erstellen**

#### **1. Deployment-Konfiguration (`deployment.yaml`)**
```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: express-api
  labels:
    app: express-api
spec:
  replicas: 2
  selector:
    matchLabels:
      app: express-api
  template:
    metadata:
      labels:
        app: express-api
    spec:
      containers:
      - name: express-api
        image: <username>/express-api:1.0.0
        imagePullPolicy: IfNotPresent
        ports:
        - containerPort: 3000
        envFrom:
        - secretRef:
            name: db-credentials
        resources:
          requests:
            cpu: "100m"
            memory: "128Mi"
          limits:
            cpu: "500m"
            memory: "512Mi"
      securityContext:
        runAsNonRoot: true
        runAsUser: 1000
```

#### **2. Service-Konfiguration (`service.yaml`)**
```yaml
apiVersion: v1
kind: Service
metadata:
  name: express-api
spec:
  selector:
    app: express-api
  ports:
    - protocol: TCP
      port: 80
      targetPort: 3000
  type: NodePort
```

#### **3. Ingress-Route (`ingress.yaml`) - Optional**
```yaml
apiVersion: networking.k8s.io/v1
kind: Ingress
metadata:
  name: express-api
  annotations:
    traefik.ingress.kubernetes.io/router.entrypoints: web
spec:
  rules:
  - host: api.example.com
    http:
      paths:
      - path: /
        pathType: Prefix
        backend:
          service:
            name: express-api
            port:
              number: 80
```

---

### **7.2. Anwendung im Cluster bereitstellen**

#### **1. Manifeste anwenden**
```bash
kubectl apply -f deployment.yaml
kubectl apply -f service.yaml
# Optional:
kubectl apply -f ingress.yaml
```

#### **2. Deployment-Status überprüfen**
```bash
kubectl get deployments
kubectl get pods -o wide
kubectl describe deployment express-api
```

#### **3. Service-Informationen anzeigen**
```bash
kubectl get services
kubectl describe service express-api
```

---

### **7.3. Zugriff auf die API testen**

#### **1. Temporärer Port-Forward**
```bash
kubectl port-forward svc/express-api 8080:80
```
Zugriff unter: `http://localhost:8080/api/users`

#### **2. NodePort direkt testen**
```bash
curl http://<node-ip>:<node-port>/api/users
```

#### **3. Ingress testen (falls konfiguriert)**
```bash
# Hosts-Eintrag hinzufügen
echo "<node-ip> api.example.com" | sudo tee -a /etc/hosts
curl http://api.example.com/api/users
```

---

### **7.4. Rolling Updates durchführen**

#### **1. Neue Image-Version deployen**
```bash
kubectl set image deployment/express-api express-api=<username>/express-api:1.1.0
```

#### **2. Update-Status überwachen**
```bash
kubectl rollout status deployment/express-api
kubectl get pods -w
```

#### **3. Bei Problemen: Rollback durchführen**
```bash
kubectl rollout undo deployment/express-api
```

---

### **7.5. Autoscaling konfigurieren**

#### **1. Horizontal Pod Autoscaler hinzufügen**
```bash
kubectl autoscale deployment express-api --cpu-percent=50 --min=2 --max=5
```

#### **2. HPA-Status überprüfen**
```bash
kubectl get hpa
kubectl describe hpa express-api
```

---

### **Troubleshooting**

**Problem:** Pods starten nicht  
**Lösung:**
```bash
kubectl logs <pod-name>
kubectl describe pod <pod-name>
```

**Problem:** Dienst nicht erreichbar  
**Lösung:**
```bash
kubectl get endpoints
kubectl describe endpoints express-api
```

---

### **Zusammenfassung**
✅ Express-Anwendung erfolgreich im K3s-Cluster deployed  
✅ Service für Zugriff auf die API eingerichtet  
✅ Optional: Ingress für externen Zugriff konfiguriert  
✅ Update-Strategien und Autoscaling implementiert  

**➡️ Weiter zu [8. Optional: Persistenz und Skalierung](#8-optional-persistenz-und-skalierung)**



## **8. Erweiterte Konfiguration: Persistenz und Skalierung**

In diesem Abschnitt optimieren wir unsere Bereitstellung durch Persistenz-Lösungen und erweiterte Skalierungsmechanismen.

---

### **8.1. Persistente Volumes für Anwendungsdaten**

#### **1. PersistentVolumeClaim erstellen (`pvc.yaml`)**
```yaml
apiVersion: v1
kind: PersistentVolumeClaim
metadata:
  name: api-data-pvc
spec:
  accessModes:
    - ReadWriteOnce
  resources:
    requests:
      storage: 1Gi
  storageClassName: local-path
```

#### **2. Deployment mit Volume-Mounts erweitern**
```yaml
# In deployment.yaml unter spec.template.spec
volumes:
- name: api-storage
  persistentVolumeClaim:
    claimName: api-data-pvc

# Unter containers.volumeMounts
volumeMounts:
- mountPath: "/app/data"
  name: api-storage
```

#### **3. PVC anwenden und prüfen**
```bash
kubectl apply -f pvc.yaml
kubectl get pvc
kubectl describe pvc api-data-pvc
```

---

### **8.2. Horizontale Skalierung automatisieren**

#### **1. Resource Limits optimieren**
```yaml
# In deployment.yaml
resources:
  limits:
    cpu: "1"
    memory: "1Gi"
  requests:
    cpu: "200m"
    memory: "256Mi"
```

#### **2. Autoscaling Policy anpassen**
```bash
kubectl autoscale deployment express-api \
  --cpu-percent=60 \
  --min=2 \
  --max=5 \
  --namespace=default
```

#### **3. Lasttest durchführen**
```bash
kubectl run -i --tty load-generator --rm --image=busybox --restart=Never -- \
  /bin/sh -c "while true; do wget -q -O- http://express-api/api/users; done"
```

---

### **8.3. Vertikale Skalierung (VPA)**

#### **1. Vertical Pod Autoscaler installieren**
```bash
kubectl apply -f https://github.com/kubernetes/autoscaler/releases/download/vertical-pod-autoscaler-0.13.0/vertical-pod-autoscaler-crd.yaml
```

#### **2. VPA Konfiguration erstellen (`vpa.yaml`)**
```yaml
apiVersion: autoscaling.k8s.io/v1
kind: VerticalPodAutoscaler
metadata:
  name: express-api-vpa
spec:
  targetRef:
    apiVersion: "apps/v1"
    kind: Deployment
    name: express-api
  updatePolicy:
    updateMode: "Auto"
```

---

### **8.4. Readiness/Liveness Probes**

#### **1. Health-Check Endpoint in Express
```javascript
// In app.js
app.get('/health', (req, res) => {
  res.status(200).json({ status: 'healthy' });
});
```

#### **2. Probes im Deployment konfigurieren
```yaml
livenessProbe:
  httpGet:
    path: /health
    port: 3000
  initialDelaySeconds: 30
  periodSeconds: 10

readinessProbe:
  httpGet:
    path: /health
    port: 3000
  initialDelaySeconds: 5
  periodSeconds: 5
```

---

### **8.5. Zero-Downtime Deployments**

#### **1. Rolling Update Strategie
```yaml
strategy:
  type: RollingUpdate
  rollingUpdate:
    maxSurge: 25%
    maxUnavailable: 25%
```

#### **2. Blue/Green Deployment vorbereiten
```bash
kubectl apply -f deployment-green.yaml
kubectl patch service express-api \
  -p '{"spec":{"selector":{"app":"express-api-green"}}}'
```

---

### **Troubleshooting**

**Problem:** PVC bleibt im Pending-Status  
**Lösung:**
```bash
kubectl describe pvc api-data-pvc
kubectl get storageclass
```

**Problem:** Autoscaler reagiert nicht  
**Lösung:**
```bash
kubectl describe hpa express-api
kubectl top pods
```

---

### **Zusammenfassung**
✅ Persistente Speicherung mit Local Path Provisioner  
✅ Automatische horizontale und vertikale Skalierung  
✅ Gesundheitschecks für stabile Bereitstellung  
✅ Zero-Downtime Deployment Strategien  

**➡️ Weiter zu [9. Monitoring und Wartung](#9-monitoring-und-wartung)**



## **8. Erweiterte Cluster-Konfiguration und Optimierungen**

Nachdem unsere Basis-Infrastruktur steht, optimieren wir nun den K3s-Cluster für Produktionsbetrieb mit Fokus auf Performance, Sicherheit und Ausfallsicherheit.

---

### **8.1. Persistent Volume Configuration**

#### **1. Lokale Storage Class erweitern**
```bash
cat <<EOF | kubectl apply -f -
apiVersion: storage.k8s.io/v1
kind: StorageClass
metadata:
  name: local-storage
provisioner: kubernetes.io/no-provisioner
volumeBindingMode: WaitForFirstConsumer
EOF
```

#### **2. Persistent Volume für lokalen Storage**
```yaml
apiVersion: v1
kind: PersistentVolume
metadata:
  name: local-pv
spec:
  capacity:
    storage: 10Gi
  accessModes:
  - ReadWriteOnce
  persistentVolumeReclaimPolicy: Retain
  storageClassName: local-storage
  local:
    path: /mnt/data
  nodeAffinity:
    required:
      nodeSelectorTerms:
      - matchExpressions:
        - key: kubernetes.io/hostname
          operator: In
          values:
          - ubuntu  # Ihr Hostname
```

#### **3. Verwendung im Deployment**
```yaml
volumes:
- name: app-data
  persistentVolumeClaim:
    claimName: app-pvc
```

---

### **8.2. Advanced Scheduling**

#### **1. Node Affinity Rules**
```yaml
affinity:
  nodeAffinity:
    requiredDuringSchedulingIgnoredDuringExecution:
      nodeSelectorTerms:
      - matchExpressions:
        - key: node-role
          operator: In
          values:
          - worker
```

#### **2. Pod Anti-Affinity für Hochverfügbarkeit**
```yaml
podAntiAffinity:
  preferredDuringSchedulingIgnoredDuringExecution:
  - weight: 100
    podAffinityTerm:
      labelSelector:
        matchExpressions:
        - key: app
          operator: In
          values:
          - express-api
      topologyKey: kubernetes.io/hostname
```

---

### **8.3. Network Policies**

#### **1. Datenbank-Isolation**
```yaml
apiVersion: networking.k8s.io/v1
kind: NetworkPolicy
metadata:
  name: db-isolation
spec:
  podSelector:
    matchLabels:
      app: postgres
  policyTypes:
  - Ingress
  ingress:
  - from:
    - podSelector:
        matchLabels:
          app: express-api
    ports:
    - protocol: TCP
      port: 5432
```

#### **2. API Zugriffsbeschränkung**
```yaml
apiVersion: networking.k8s.io/v1
kind: NetworkPolicy
metadata:
  name: api-access
spec:
  podSelector:
    matchLabels:
      app: express-api
  ingress:
  - from:
    - namespaceSelector: {}
    ports:
    - protocol: TCP
      port: 3000
```

---

### **8.4. Resource Monitoring Stack**

#### **1. K3s Metrics Server aktivieren**
```bash
kubectl top nodes
kubectl top pods
```

#### **2. Prometheus-Stack installieren**
```bash
helm repo add prometheus-community https://prometheus-community.github.io/helm-charts
helm install prometheus prometheus-community/kube-prometheus-stack
```

#### **3. Custom Metrics für HPA**
```yaml
metrics:
- type: Resource
  resource:
    name: cpu
    target:
      type: Utilization
      averageUtilization: 60
- type: Pods
  pods:
    metric:
      name: http_requests
    target:
      type: AverageValue
      averageValue: 500m
```

---

### **8.5. Security Hardening**

#### **1. Pod Security Standards**
```yaml
apiVersion: policy/v1beta1
kind: PodSecurityPolicy
metadata:
  name: restricted
spec:
  privileged: false
  allowPrivilegeEscalation: false
  requiredDropCapabilities:
    - ALL
  volumes:
    - 'configMap'
    - 'emptyDir'
    - 'secret'
```

#### **2. Security Context im Deployment**
```yaml
securityContext:
  runAsNonRoot: true
  runAsUser: 1000
  fsGroup: 2000
  capabilities:
    drop:
    - ALL
```

---

### **8.6. Backup-Strategien**

#### **1. Velero installieren**
```bash
velero install \
  --provider aws \
  --plugins velero/velero-plugin-for-aws:v1.0.0 \
  --bucket k3s-backups \
  --secret-file ./credentials-velero \
  --use-volume-snapshots=false \
  --backup-location-config region=minio,s3ForcePathStyle="true",s3Url=http://minio.example.com
```

#### **2. Scheduled Backups**
```bash
velero schedule create daily-backup --schedule="@every 24h"
```

---

### **Troubleshooting Advanced**

**Problem:** Persistent Volume Claims unbound  
**Lösung:**
```bash
kubectl describe pvc <pvc-name>
kubectl get storageclass
```

**Problem:** Netzwerk-Policies blockieren Traffic  
**Lösung:**
```bash
kubectl describe networkpolicy
kubectl run -it --rm --image=alpine network-test -- sh
```

---

### **Zusammenfassung**
✅ Erweiterte Storage-Optionen mit lokalen Volumes  
✅ Intelligentes Scheduling mit Affinity Rules  
✅ Netzwerk-Sicherheit durch Policies  
✅ Umfassendes Monitoring mit Prometheus  
✅ Produktionsreife Sicherheitskonfiguration  
✅ Automatisierte Backup-Strategien  

**➡️ Weiter zu [9. Monitoring und Wartung](#9-monitoring-und-wartung)**


## **9. Monitoring und Wartung des K3s-Clusters**

Nachdem unsere Anwendung läuft, implementieren wir nun ein umfassendes Monitoring-System und etablieren Wartungsprozesse für einen stabilen Produktionsbetrieb.

---

### **9.1. Cluster-Monitoring mit Prometheus und Grafana**

#### **1. Monitoring-Stack installieren**
```bash
helm repo add prometheus-community https://prometheus-community.github.io/helm-charts
helm install k3s-monitoring prometheus-community/kube-prometheus-stack \
  --namespace monitoring \
  --create-namespace \
  --set prometheus.prometheusSpec.serviceMonitorSelectorNilUsesHelmValues=false
```

#### **2. Grafana Dashboard zugänglich machen**
```yaml
apiVersion: networking.k8s.io/v1
kind: Ingress
metadata:
  name: grafana-ingress
  namespace: monitoring
  annotations:
    traefik.ingress.kubernetes.io/router.entrypoints: web
spec:
  rules:
  - host: grafana.example.com
    http:
      paths:
      - path: /
        pathType: Prefix
        backend:
          service:
            name: k3s-monitoring-grafana
            port:
              number: 80
```

#### **3. Wichtige Dashboards importieren**
- Kubernetes Cluster (ID: 315)
- Node Exporter (ID: 11074)
- K3s Performance (ID: 13770)

---

### **9.2. Log-Management mit Loki**

#### **1. Loki Stack installieren**
```bash
helm install loki grafana/loki-stack \
  --namespace monitoring \
  --set promtail.enabled=true \
  --set grafana.enabled=false
```

#### **2. Log-Abfragen in Grafana**
```logql
{namespace="default", pod=~"express-api-.*"} |= "error"
```

#### **3. Log-Retention konfigurieren**
```yaml
loki:
  config:
    table_manager:
      retention_deletes_enabled: true
      retention_period: 720h
```

---

### **9.3. Automatisierte Wartungsaufgaben**

#### **1. CronJobs für regelmäßige Tasks**
```yaml
apiVersion: batch/v1
kind: CronJob
metadata:
  name: db-backup
spec:
  schedule: "0 2 * * *"
  jobTemplate:
    spec:
      template:
        spec:
          containers:
          - name: backup
            image: postgres:15-alpine
            command: ["pg_dump", "-h", "postgres-host", "-U", "user", "-d", "dbname", "-f", "/backup/db-$(date +%Y-%m-%d).sql"]
            volumeMounts:
            - mountPath: /backup
              name: backup-volume
          restartPolicy: OnFailure
          volumes:
          - name: backup-volume
            persistentVolumeClaim:
              claimName: backup-pvc
```

#### **2. Automatische Zertifikatsverwaltung**
```bash
kubectl apply -f https://github.com/cert-manager/cert-manager/releases/download/v1.11.0/cert-manager.yaml
```

---

### **9.4. Performance-Optimierungen**

#### **1. K3s-Tuning Parameter**
```bash
cat <<EOF | sudo tee /etc/systemd/system/k3s.service.env
K3S_KUBELET_ARGS=--kube-reserved cpu=500m,memory=512Mi --system-reserved cpu=250m,memory=256Mi
EOF
sudo systemctl daemon-reload
sudo systemctl restart k3s
```

#### **2. etcd Maintenance (bei HA-Setup)**
```bash
k3s etcd-snapshot save --name pre-upgrade-backup
k3s etcd-defrag
```

---

### **9.5. Sicherheitsüberwachung**

#### **1. Falco für Runtime Security**
```bash
helm install falco falcosecurity/falco \
  --namespace falco \
  --create-namespace \
  --set ebpf.enabled=true
```

#### **2. Kubernetes Audit Logging**
```yaml
apiVersion: audit.k8s.io/v1
kind: Policy
rules:
- level: Metadata
  resources:
  - group: ""
    resources: ["secrets", "configmaps"]
```

---

### **9.6. Upgrade-Strategien**

#### **1. K3s Version Upgrade**
```bash
curl -sfL https://get.k3s.io | INSTALL_K3S_VERSION=v1.28.5+k3s1 sh -
```

#### **2. Zero-Downtime Upgrade Prozess**
1. Backup erstellen
2. Einzelne Nodes nacheinander updaten
3. Komponenten-Tests durchführen
4. Rollback planen

---

### **Troubleshooting Toolkit**

#### **1. Diagnose-Befehle**
```bash
# Cluster-Status
kubectl get --raw='/readyz?verbose'

# Ressourcenanalyse
kubectl top pods --sort-by=memory

# Netzwerkprobleme
kubectl run net-tester --image=nicolaka/netshoot --rm -it -- /bin/bash
```

#### **2. Debug-Pod Template**
```yaml
apiVersion: v1
kind: Pod
metadata:
  name: debug-pod
spec:
  containers:
  - name: tools
    image: rancherlabs/support-tools
    command: ["sleep", "infinity"]
```

---

### **Zusammenfassung**
✅ Umfassendes Monitoring mit Prometheus/Grafana  
✅ Zentrale Logverwaltung mit Loki  
✅ Automatisierte Wartungsroutinen  
✅ Leistungsoptimierungen für Produktionsbetrieb  
✅ Sicherheitsüberwachung in Echtzeit  
✅ Strukturierte Upgrade-Prozesse  

**➡️ Weiter zu [10. Sicherheitsbest Practices](#10-sicherheitsbest-practices)**  

*(Hinweis: Alle Konfigurationen sind auch für Einzel-Node-Setups optimiert.)*




## **10. Sicherheitsbest Practices für Produktionsbetrieb**

In diesem kritischen Abschnitt härten wir unseren K3s-Cluster für den Produktionseinsatz ab und implementieren Enterprise-grade Sicherheitsmaßnahmen.

---

### **10.1. Cluster-Härtung**

#### **1. CIS Benchmark Compliance**
```bash
# CIS Scan durchführen
curl -sfL https://raw.githubusercontent.com/k3s-io/k3s/master/install.sh | INSTALL_K3S_SELINUX_WARN=true sh -s - --cis-mode
kubectl apply -f https://raw.githubusercontent.com/rancher/cis-operator/master/deploy/manifests/operator.yaml
```

#### **2. API-Server Secure Flags**
```yaml
# /etc/rancher/k3s/config.yaml
kube-apiserver-arg:
- "--authorization-mode=Node,RBAC"
- "--enable-admission-plugins=NodeRestriction,PodSecurityPolicy"
- "--tls-cipher-suites=TLS_ECDHE_ECDSA_WITH_AES_128_GCM_SHA256"
```

---

### **10.2. Netzwerk-Sicherheit**

#### **1. Network Policies für Namespaces**
```yaml
apiVersion: networking.k8s.io/v1
kind: NetworkPolicy
metadata:
  name: default-deny-all
spec:
  podSelector: {}
  policyTypes:
  - Ingress
  - Egress
```

#### **2. Service Mesh mit Istio**
```bash
istioctl install --set profile=minimal -y
kubectl label namespace default istio-injection=enabled
```

---

### **10.3. Secrets Management**

#### **1. Vault Integration**
```bash
helm install vault hashicorp/vault --set "server.dev.enabled=true"
kubectl exec -it vault-0 -- vault secrets enable kubernetes
```

#### **2. Secrets Rotation Automatisierung**
```yaml
apiVersion: external-secrets.io/v1beta1
kind: ExternalSecret
metadata:
  name: db-credentials
spec:
  refreshInterval: 1h
  secretStoreRef:
    name: vault
    kind: SecretStore
  target:
    name: db-secret
  data:
  - secretKey: DB_PASSWORD
    remoteRef:
      key: secrets/data/db
      property: password
```

---

### **10.4. Pod Security Standards**

#### **1. PodSecurity Admission**
```yaml
apiVersion: apiserver.config.k8s.io/v1
kind: AdmissionConfiguration
plugins:
- name: PodSecurity
  configuration:
    apiVersion: pod-security.admission.config.k8s.io/v1beta1
    kind: PodSecurityConfiguration
    defaults:
      enforce: "restricted"
      enforce-version: "latest"
```

#### **2. Security Context Constraints**
```bash
kubectl apply -f - <<EOF
apiVersion: security.openshift.io/v1
kind: SecurityContextConstraints
metadata:
  name: restricted
allowPrivilegedContainer: false
runAsUser:
  type: MustRunAsNonRoot
EOF
```

---

### **10.5. Compliance & Auditing**

#### **1. Kubernetes Audit Logging**
```yaml
# /etc/rancher/k3s/audit-policy.yaml
apiVersion: audit.k8s.io/v1
rules:
- level: Metadata
  resources:
  - group: ""
    resources: ["secrets"]
  - group: ""
    resources: ["configmaps"]
    namespaces: ["kube-system"]
```

#### **2. Compliance Scans mit kube-bench**
```bash
docker run --rm --pid=host -v /etc:/etc:ro -v /var:/var:ro aquasec/kube-bench:latest run --targets node
```

---

### **10.6. Notfall-Wiederherstellung**

#### **1. Disaster Recovery Plan**
```bash
# Vollständiger Cluster-Backup
k3s etcd-snapshot save --name disaster-recovery
# Wiederherstellung:
k3s server --cluster-restore --cluster-init --etcd-snapshot-name=disaster-recovery
```

#### **2. Security Incident Response**
1. Verdächtige Pods isolieren
2. Kompromittierte Secrets rotieren
3. Audit-Logs analysieren
4. CVE-Patches anwenden

---

### **Sicherheits-Checkliste**

✅ **Authentifizierung**  
- [ ] RBAC mit minimalen Rechten  
- [ ] ServiceAccount Token Rotation  

✅ **Netzwerk**  
- [ ] Network Policies für alle Namespaces  
- [ ] Ingress TLS mit validen Zertifikaten  

✅ **Workload-Sicherheit**  
- [ ] Read-only Root Filesystem  
- [ ] Nicht-root User für alle Container  

✅ **Monitoring**  
- [ ] Sicherheitsrelevante Events in SIEM  
- [ ] Ungewöhnliche Aktivitätsalarme  

---

### **Troubleshooting Sicherheitsprobleme**

**Problem:** Pod startet nicht wegen SecurityContext  
**Lösung:**
```bash
kubectl get events --sort-by=.metadata.creationTimestamp
kubectl describe pod <problem-pod>
```

**Problem:** Netzwerk-Policy blockiert Traffic  
**Lösung:**
```bash
kubectl run -it --rm --image=nicolaka/netshoot debug-pod -- bash
curl -v http://express-api.default
```

---

### **Zusammenfassung**
✅ CIS-härtung des K3s-Clusters  
✅ Zero-Trust Netzwerkpolitiken  
✅ Enterprise Secrets Management  
✅ Strikte Pod-Sicherheitsrichtlinien  
✅ Compliance-Auditing und Forensik  
✅ Disaster-Recovery Verfahren  

**➡️ Weiter zu [11. Troubleshooting & häufige Probleme](#11-troubleshooting-häufige-probleme)**  

*(Hinweis: Diese Maßnahmen entsprechen BSI-Grundschutz und NIST-Richtlinien.)*



## **11. Troubleshooting & häufige Probleme**

In diesem Abschnitt behandeln wir Lösungen für typische Probleme, die bei der Arbeit mit K3s und unserer Express-API auftreten können.

---

### **11.1. Cluster-Probleme**

#### **1. K3s startet nicht**
**Symptome:**
- `systemctl status k3s` zeigt Fehler
- `journalctl -u k3s -f` zeigt Port-Konflikte

**Lösungen:**
```bash
# Port-Konflikte identifizieren
sudo ss -tulnp | grep -E '6443|10250'

# K3s zurücksetzen
sudo /usr/local/bin/k3s-uninstall.sh
sudo rm -rf /etc/rancher/k3s/
```

#### **2. Nodes im NotReady-Status**
```bash
# Kubelet Logs prüfen
journalctl -u k3s-agent -f

# Netzwerkverbindung testen
kubectl run -it --rm --image=alpine network-test -- ping <control-plane-ip>
```

---

### **11.2. Netzwerkprobleme**

#### **1. Pods können sich nicht verbinden**
**Diagnose:**
```bash
# DNS-Auflösung testen
kubectl run -it --rm --image=busybox dns-test -- nslookup kubernetes.default

# Service Discovery prüfen
kubectl get endpoints
```

**Lösung für CoreDNS-Probleme:**
```bash
kubectl -n kube-system edit configmap coredns
# StubDomains für benutzerdefinierte DNS-Einträge hinzufügen
```

#### **2. Ingress funktioniert nicht**
```bash
# Traefik Logs anzeigen
kubectl logs -n kube-system -l app.kubernetes.io/name=traefik

# Ingress Controller Status
kubectl -n kube-system get pods -l app.kubernetes.io/name=traefik
```

---

### **11.3. Persistent Volume Probleme**

#### **1. PVC bleibt im Pending-Status**
```bash
kubectl describe pvc <pvc-name>
kubectl get storageclass

# Bei local-path Provisioner:
sudo chmod -R 777 /var/lib/rancher/k3s/storage/
```

#### **2. Datenverlust nach Pod-Neustart**
```yaml
# deployment.yaml sicherheitshalber anpassen:
volumeMounts:
  mountPath: /data
  subPath: express-data  # Vermeidet Überschreiben
```

---

### **11.4. Datenbankverbindungsfehler**

#### **1. Connection Refused von API zu PostgreSQL**
```bash
# Port-Forwarding testen
kubectl port-forward svc/express-api 8080:80
curl -v http://localhost:8080/api/users

# Datenbank-Logs prüfen
sudo tail -f /var/log/postgresql/postgresql-14-main.log
```

#### **2. TLS-Verbindungsprobleme**
```yaml
# db-connection.js anpassen
const pool = new Pool({
  ssl: {
    rejectUnauthorized: false,
    ca: fs.readFileSync('/certs/ca.crt').toString()
  }
});
```

---

### **11.5. Performance-Probleme**

#### **1. Hohe CPU-Auslastung**
```bash
# Top Pods identifizieren
kubectl top pods --sort-by=cpu

# Profiling für Node.js App
kubectl exec <pod-name> -- node --inspect-brk=0.0.0.0:9229 server.js
```

#### **2. Memory Leaks**
```yaml
# Deployment um OOM-Killer Limits erweitern
resources:
  limits:
    memory: "512Mi"
  requests:
    memory: "256Mi"
```

---

### **11.6. Upgrade-Probleme**

#### **1. Inkompatible API-Versionen**
```bash
# API-Ressourcen prüfen
kubectl api-resources --verbs=list -o name | xargs -n 1 kubectl get --show-kind --ignore-not-found -n default

# K3s Version rückwärtskompatibel?
k3s --version
```

#### **2. Custom Resource Definitions (CRDs)**
```bash
# CRDs vor Upgrade sichern
kubectl get crds -o yaml > crds-backup.yaml
```

---

### **11.7. Debugging Toolkit**

#### **1. Nützliche Diagnose-Container**
```bash
# Netzwerk-Tests
kubectl run -it --rm --image=nicolaka/netshoot debug -- bash

# K8s API Tests
kubectl run -it --rm --image=bitnami/kubectl debug -- bash
```

#### **2. Cluster-Info sammeln**
```bash
# Support-Bundle erstellen
kubectl get all --all-namespaces -o yaml > cluster-state.yaml
kubectl describe nodes > nodes-describe.txt
```

---

### **Häufige Fehlermeldungen und Lösungen**

| Fehler | Lösung |
|--------|--------|
| `ImagePullBackOff` | `kubectl describe pod <pod>` → Image-Tag prüfen |
| `CrashLoopBackOff` | `kubectl logs --previous <pod>` → Letzte Logs |
| `FailedScheduling` | `kubectl describe pod <pod>` → Ressourcen prüfen |
| `403 Forbidden` | RBAC-Rollen überprüfen |
| `Connection timed out` | Netzwerk-Policies und Service-Endpoints prüfen |

---

### **Zusammenfassung**
✅ Systematische Fehlerdiagnose für alle Komponenten  
✅ Bewährte Lösungen für häufige Cluster-Probleme  
✅ Datenbank-spezifische Troubleshooting-Methoden  
✅ Performance-Optimierung bei Ressourcenengpässen  
✅ Upgrade- und Kompatibilitätsprobleme lösen  

**➡️ Weiter zu [12. Fazit & nächste Schritte](#12-fazit--nächste-schritte)**  

*(Tipp: Für komplexe Probleme `kubectl get events --sort-by=.metadata.creationTimestamp` verwenden)*




## **12. UFW Firewall Konfiguration für K3s**

Bei der Verwendung von UFW (Uncomplicated Firewall) mit K3s sind spezielle Konfigurationen notwendig, um sicherzustellen, dass der Kubernetes-Cluster korrekt funktioniert, während die Sicherheit gewährleistet bleibt.

---

### **12.1. Kritische Ports für K3s**

K3s benötigt folgende Ports für den Betrieb:

| Port | Protokoll | Zweck                         |
|------|-----------|-------------------------------|
| 6443 | TCP       | Kubernetes API Server         |
| 8472 | UDP       | Flannel VXLAN (Netzwerk-Overlay) |
| 10250 | TCP      | Kubelet API (Metriken/Exec)   |
| 2379-2380 | TCP | etcd Server (nur HA-Modus)    |
| 30000-32767 | TCP | NodePort Services            |

---

### **12.2. Grundlegende UFW Konfiguration**

#### **1. UFW zurücksetzen (falls bereits konfiguriert)**
```bash
sudo ufw reset
sudo ufw default deny incoming
sudo ufw default allow outgoing
```

#### **2. Notwendige Ports freigeben**
```bash
# K3s Core-Ports
sudo ufw allow 6443/tcp
sudo ufw allow 8472/udp
sudo ufw allow 10250/tcp

# NodePort Range (optional)
sudo ufw allow 30000:32767/tcp
```

#### **3. SSH-Zugang sicher erlauben**
```bash
sudo ufw limit 22/tcp  # Schutz gegen Brute-Force
```

---

### **12.3. Spezielle K3s-Konfiguration mit UFW**

#### **1. CNI-Spezifische Ports (Flannel/Calico)**
```bash
# Für Flannel:
sudo ufw allow 8472/udp

# Für Calico:
sudo ufw allow 179/tcp
sudo ufw allow 4789/udp
```

#### **2. Probleme mit Kube-Proxy vermeiden**
```bash
# IPTables-Policy anpassen (wichtig!)
echo -e "*filter\n:INPUT ACCEPT [0:0]\n:FORWARD ACCEPT [0:0]\n:OUTPUT ACCEPT [0:0]\nCOMMIT" | sudo tee /etc/ufw/before.rules
```

#### **3. UFW nach Konfiguration aktivieren**
```bash
sudo ufw enable
sudo systemctl restart k3s  # Neustart für Änderungen
```

---

### **12.4. Häufige Probleme und Lösungen**

#### **1. Pods können nicht kommunizieren**
**Symptom:**  
- NetworkPolicy-Verletzungen
- `kubectl get pods` zeigt `ContainerCreating` oder `CrashLoopBackOff`

**Lösung:**
```bash
# UFW Logging aktivieren
sudo ufw logging on
sudo tail -f /var/log/ufw.log

# Temporär alle internen Verbindungen erlauben
sudo ufw allow from 10.42.0.0/16  # K3s Standard-Pod-Netzwerk
```

#### **2. Kubelet kann API-Server nicht erreichen**
```bash
# Firewall-Status prüfen
sudo ufw status numbered

# Falls blockiert:
sudo ufw insert 1 allow in on cni0  # CNI-Interface
```

---

### **12.5. Sicherheitsoptimierungen**

#### **1. Eingeschränkter Zugriff auf API-Server**
```bash
# Nur von bestimmten IPs erlauben
sudo ufw allow from 192.168.1.100 to any port 6443 proto tcp
```

#### **2. Monitoring-Ports absichern**
```bash
# Metrics Server schützen
sudo ufw allow from 10.42.0.0/16 to any port 10250 proto tcp
```

#### **3. Regelprioritäten beachten**
```bash
# Regeln in korrekter Reihenfolge einfügen
sudo ufw insert 1 deny 10250/tcp  # Zuerst verweigern
sudo ufw insert 2 allow from 10.42.0.0/16 to any port 10250 proto tcp  # Dann spezifisch erlauben
```

---

### **12.6. Debugging-Tools**

#### **1. Verbindungen testen**
```bash
# Von einem Pod aus
kubectl run -it --rm --image=nicolaka/netshoot testpod -- curl -v https://kubernetes.default:6443

# Vom Host aus
sudo nc -zv 127.0.0.1 6443
```

#### **2. UFW Regeln überprüfen**
```bash
sudo ufw status verbose
sudo ufw show added  # Alle aktiven Regeln
```

---

### **Best Practices Checkliste**

✅ **Grundkonfiguration**  
- [ ] Default Policy: `deny incoming`, `allow outgoing`  
- [ ] SSH-Zugang mit `limit` gesichert  

✅ **K3s-spezifisch**  
- [ ] Alle notwendigen Ports für CNI freigegeben  
- [ ] IPTables-Policy in `before.rules` angepasst  

✅ **Sicherheit**  
- [ ] API-Server Zugriff eingeschränkt  
- [ ] Inter-Pod-Kommunikation getestet  

✅ **Wartung**  
- [ ] UFW-Logs aktiviert  
- [ ] Regeln dokumentiert  

---

### **Zusammenfassung**
Mit diesen UFW-Konfigurationen erreichen Sie:  
🔒 **Sichere Grundkonfiguration** für Ihren Server  
🔄 **Unterbrechungsfreien Betrieb** von K3s  
🔍 **Transparentes Logging** für Problemdiagnosen  
🚀 **Optimale Performance** ohne Netzwerk-Engpässe  

**➡️ Diese Einstellungen sollten vor dem K3s-Installation vorgenommen werden!**  

*(Tipp: Bei Problemen temporär `sudo ufw disable` testen, um Firewall-Konflikte auszuschließen.)*



## **13. CI/CD Deployment mit GitLab Pipeline**

In diesem Abschnitt automatisieren wir das Deployment unserer Express-API in den K3s-Cluster über eine GitLab CI/CD-Pipeline für professionelle Entwicklungsworkflows.

---

### **13.1. Vorbereitungen in GitLab**

#### **1. Repository-Struktur**
```
.gitlab-ci.yml
kubernetes/
  ├── deployment.yaml
  ├── service.yaml
  └── ingress.yaml
Dockerfile
src/
  └── (Express-App Code)
```

#### **2. Umgebungsvariablen in GitLab hinterlegen**
```
Settings → CI/CD → Variables
- KUBE_URL: https://<your-server-ip>:6443
- KUBE_TOKEN: <service-account-token>
- DOCKER_USER: <registry-user>
- DOCKER_PASS: <registry-pw>
- DB_SECRET: <base64-encoded-secret>
```

---

### **13.2. GitLab CI/CD Pipeline Konfiguration**

#### **1. Basis `.gitlab-ci.yml`**
```yaml
stages:
  - build
  - test
  - deploy

variables:
  DOCKER_IMAGE: registry.gitlab.com/<your-group>/<your-project>
  KUBE_NAMESPACE: express-api

build:
  stage: build
  image: docker:20.10
  services:
    - docker:20.10-dind
  script:
    - docker login -u $DOCKER_USER -p $DOCKER_PASS registry.gitlab.com
    - docker build -t $DOCKER_IMAGE:$CI_COMMIT_SHA .
    - docker push $DOCKER_IMAGE:$CI_COMMIT_SHA
  only:
    - main

deploy:
  stage: deploy
  image: bitnami/kubectl:latest
  script:
    - kubectl config set-cluster k3s --server="$KUBE_URL" --insecure-skip-tls-verify=true
    - kubectl config set-credentials gitlab --token="$KUBE_TOKEN"
    - kubectl config set-context default --cluster=k3s --user=gitlab
    - kubectl config use-context default
    
    # Kubernetes Manifest aktualisieren
    - sed -i "s|{{IMAGE}}|$DOCKER_IMAGE:$CI_COMMIT_SHA|g" kubernetes/deployment.yaml
    - kubectl apply -f kubernetes/
    
    # Rollout Status überwachen
    - kubectl rollout status deployment/express-api -n $KUBE_NAMESPACE --timeout=120s
  only:
    - main
```

---

### **13.3. Kubernetes RBAC für GitLab**

#### **1. ServiceAccount erstellen**
```bash
kubectl create serviceaccount gitlab-deployer -n express-api
```

#### **2. RoleBinding konfigurieren**
```yaml
apiVersion: rbac.authorization.k8s.io/v1
kind: Role
metadata:
  namespace: express-api
  name: gitlab-deployer-role
rules:
- apiGroups: ["", "apps"]
  resources: ["deployments", "services", "pods"]
  verbs: ["get", "list", "watch", "create", "update", "patch"]

---
apiVersion: rbac.authorization.k8s.io/v1
kind: RoleBinding
metadata:
  name: gitlab-deployer-binding
  namespace: express-api
subjects:
- kind: ServiceAccount
  name: gitlab-deployer
  namespace: express-api
roleRef:
  kind: Role
  name: gitlab-deployer-role
  apiGroup: rbac.authorization.k8s.io
```

#### **3. Token für GitLab extrahieren**
```bash
kubectl -n express-api describe secret $(kubectl -n express-api get secret | grep gitlab-deployer | awk '{print $1}')
```

---

### **13.4. Erweiterte Pipeline-Features**

#### **1. Blue/Green Deployment**
```yaml
deploy-blue:
  script:
    - kubectl apply -f kubernetes/blue-deployment.yaml
    - kubectl apply -f kubernetes/blue-service.yaml
    - ./wait-for-200.sh http://blue-service

deploy-green:
  script:
    - kubectl apply -f kubernetes/green-deployment.yaml
    - kubectl patch service main-service -p '{"spec":{"selector":{"version":"green"}}}'
```

#### **2. Automatische Rollback bei Fehlern**
```yaml
rollback:
  stage: deploy
  script:
    - kubectl rollout undo deployment/express-api
  when: on_failure
```

---

### **13.5. Sicherheitsbest Practices**

#### **1. Container Scanning**
```yaml
container_scan:
  stage: test
  image: docker:stable
  services:
    - docker:stable-dind
  script:
    - docker run --rm -v "$PWD:/app" aquasec/trivy:latest image --exit-code 1 $DOCKER_IMAGE:$CI_COMMIT_SHA
```

#### **2. Kubernetes Manifest Validation**
```yaml
validate_manifests:
  stage: test
  image: instrumenta/kubeval
  script:
    - kubeval -d kubernetes/ --ignore-missing-schemas
```

---

### **13.6. Troubleshooting der Pipeline**

#### **1. Häufige Fehler**
- **ImagePullBackOff**: Registry Authentifizierung prüfen
- **403 Forbidden**: RBAC Rechte des ServiceAccounts überprüfen
- **Connection Timeout**: Firewall-Regeln für GitLab-Runner

#### **2. Debug Kommandos**
```bash
kubectl get events --sort-by=.metadata.creationTimestamp
kubectl describe pod -l app=express-api
```

---

### **Zusammenfassung**
✅ Vollautomatisiertes Build & Deployment  
✅ Sichere RBAC-Konfiguration für GitLab  
✅ Blue/Green Deployment Strategien  
✅ Integrierte Security Scans  
✅ Automatisches Rollback bei Fehlern  

**➡️ Pipeline-Beispiel komplett verfügbar im [GitLab-Repository](#)**  

*(Tipp: Für erste Tests `manual`-Stages verwenden bevor Automatisierung aktiviert wird)*



## **14. HTTPS-Sicherung für Express-API in K3s**

Für eine Produktionsumgebung ist HTTPS essentiell. Hier zeigen wir drei bewährte Methoden zur Absicherung Ihrer Express-API:

---

### **14.1. Let's Encrypt mit Traefik Ingress (Automatisiert)**

#### **1. Traefik Ingress Controller konfigurieren**
```yaml
apiVersion: traefik.containo.us/v1alpha1
kind: IngressRoute
metadata:
  name: express-api-https
spec:
  entryPoints:
    - websecure
  routes:
  - match: Host(`api.example.com`)
    kind: Rule
    services:
    - name: express-api
      port: 3000
  tls:
    certResolver: letsencrypt
```

#### **2. ClusterIssuer für Let's Encrypt**
```yaml
apiVersion: cert-manager.io/v1
kind: ClusterIssuer
metadata:
  name: letsencrypt-prod
spec:
  acme:
    email: admin@example.com
    server: https://acme-v02.api.letsencrypt.org/directory
    privateKeySecretRef:
      name: letsencrypt-prod
    solvers:
    - http01:
        ingress:
          class: traefik
```

#### **3. Cert-Manager installieren**
```bash
helm install cert-manager jetstack/cert-manager \
  --namespace cert-manager \
  --create-namespace \
  --version v1.11.0 \
  --set installCRDs=true
```

---

### **14.2. Manuelles Zertifikat mit Kubernetes Secrets**

#### **1. Zertifikat erstellen (OpenSSL)**
```bash
openssl req -x509 -nodes -days 365 -newkey rsa:2048 \
  -keyout tls.key -out tls.crt \
  -subj "/CN=api.example.com" -addext "subjectAltName=DNS:api.example.com"
```

#### **2. Kubernetes TLS-Secret anlegen**
```bash
kubectl create secret tls api-tls \
  --cert=tls.crt \
  --key=tls.key \
  -n express-api
```

#### **3. Ingress mit TLS konfigurieren**
```yaml
apiVersion: networking.k8s.io/v1
kind: Ingress
metadata:
  name: express-api
spec:
  tls:
  - hosts:
    - api.example.com
    secretName: api-tls
  rules:
  - host: api.example.com
    http:
      paths:
      - path: /
        pathType: Prefix
        backend:
          service:
            name: express-api
            port:
              number: 3000
```

---

### **14.3. HTTPS direkt in Express (Fallback-Lösung)**

#### **1. SSL-Middleware in Express**
```javascript
const https = require('https');
const fs = require('fs');

const options = {
  key: fs.readFileSync('/etc/ssl/private.key'),
  cert: fs.readFileSync('/etc/ssl/certificate.crt')
};

https.createServer(options, app).listen(443);
```

#### **2. Deployment-Update für Zertifikatsmount**
```yaml
volumes:
- name: ssl-certs
  secret:
    secretName: api-tls
    items:
    - key: tls.crt
      path: certificate.crt
    - key: tls.key
      path: private.key
```

---

### **14.4. Sicherheitsheader (OWASP Empfehlungen)**

#### **1. Helmet.js in Express**
```javascript
const helmet = require('helmet');
app.use(helmet({
  contentSecurityPolicy: {
    directives: {
      defaultSrc: ["'self'"],
      scriptSrc: ["'self'", "'unsafe-inline'"]
    }
  },
  hsts: {
    maxAge: 63072000,
    includeSubDomains: true,
    preload: true
  }
}));
```

#### **2. Traefik Middleware für Sicherheitsheader**
```yaml
apiVersion: traefik.containo.us/v1alpha1
kind: Middleware
metadata:
  name: security-headers
spec:
  headers:
    sslRedirect: true
    stsSeconds: 31536000
    browserXssFilter: true
    contentTypeNosniff: true
    frameDeny: true
```

---

### **14.5. Zertifikatsrotation & Verlängerung**

#### **1. Automatische Verlängerung prüfen**
```bash
kubectl get certificates -n express-api
kubectl describe certificate api-tls-cert
```

#### **2. Manuelle Verlängerung erzwingen**
```bash
kubectl delete secret api-tls-cert
# Cert-Manager erstellt automatisch neues Zertifikat
```

---

### **Sicherheits-Checkliste**

✅ **Zertifikatsvalidierung**  
- [ ] Gültige CA-Signierung  
- [ ] Korrekte SANs (Subject Alternative Names)  

✅ **Verschlüsselung**  
- [ ] TLS 1.2/1.3 nur  
- [ ] Starke Cipher Suites (ECDHE, AES-GCM)  

✅ **Sicherheitsheader**  
- [ ] HSTS aktiviert  
- [ ] CSP konfiguriert  

✅ **Monitoring**  
- [ ] Zertifikatsablauf überwacht  
- [ ] Automatische Erneuerung getestet  

---

### **Troubleshooting**

**Problem:** `NET::ERR_CERT_AUTHORITY_INVALID`  
**Lösung:**
```bash
kubectl describe certificaterequest -n express-api
kubectl logs -n cert-manager -l app=cert-manager
```

**Problem:** Traefik verwendet falsches Zertifikat  
**Lösung:**
```bash
kubectl describe ingressroute express-api-https
openssl s_client -connect api.example.com:443 -servername api.example.com | openssl x509 -noout -text
```

---

### **Zusammenfassung**
🔒 **Automatisierte Zertifikate** mit Let's Encrypt  
📜 **Manuelle Zertifikate** für interne PKI  
🚀 **Performance-Optimierungen** durch TLS 1.3  
🛡️ **Härtung** nach OWASP Standards  
🔄 **Automatische Rotation** für kontinuierliche Sicherheit  

**➡️ Für Produktionsumgebungen wird die Let's Encrypt Methode empfohlen!**  

*(Tipp: Testen Sie mit `ssllabs.com/ssltest` vor dem Go-Live)*