# Infrastructure BI sécurisée & supervisée

Ce projet déploie une pile complète pour la Business Intelligence, incluant un serveur Web, une DB et une stack de monitoring complète. Tout ça orchestré par Docker.

## Architecture
- **Proxy Inverse :** Nginx (on centralise les flux sur le port 80) ;
- **Serveur Web :** Apache2 (hébergement du dashboard BI) ; 
- **DB:** MariaDB (isolée dans le réseau backend) ;
- **Monitoring (LGTM) :** Prometheus, Node Exporter & Grafana.

## Sécurité
- **Segmentation réseau :** Séparation `frontend` / `backend` pour isoler la DB ;
- **Accès restreint :** Seuls les ports 80 (Web) et 3000 (Grafana) sont exposés via Nginx ;
- **Supervision :** Tableau de bord dynamique pour surveiller la RAM, le CPU et la santé des container.

## Pour l'installation
1. `git clone https://github.com/antorou/Infrastructure-BI.git`
2. `docker-compose up -d`
3. Accès : `http://localhost` (Web) et `http://localhost/monitoring/` (Grafana).
