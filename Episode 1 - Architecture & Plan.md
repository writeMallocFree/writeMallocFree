# LAB Maison - Architecture & Plan

> **Contexte :** Bâtir un Security Operations Center (SOC)

## 1. Objectifs

> Collecter logs, flux réseau et télémétrie depuis VMs de test et lab personnels\
> Déployer un SIEM corrélé + SOAR\
> Enrichir les alertes via des plateformes open-source (MISP, OpenCTI)\
> Pouvoir déclencher Atomic Red Team / CALDERA afin de valider les détections\

## 2. Mise en place d'une infrastructure virtuelle

> **vCenter** : Version 8\
> **ESXi** : 5 Esxi V8 -> 3 sites (2*ESXI Site A, 2*ESXI Site B, 1*ESXI Site Witness)\
> **vSAN** : stretched cluster\
> **Capacité libre dédiée SOC** : 1To SSD NVME\
> **Réseau** : VLANs 10-Mgmt / 20-Prod / 30-Capture / 40-SOC\

# 3.SOC Stack

| Fonction | Composant | VM sizing | Stockage | Notes |
|----------|-----------|-----------|-----------------|-------|
| **SIEM / NDR** | *Security Onion 2.4* (Elastic, Fleet, Zeek, Suricata) |   |   |   |
| **Endpoint Security** | *Wazuh Mgr 4.12* |   |   |   |
| **SOAR** | Shuffle |   |   |   |
| **Case Management** | *TheHive 4* + *Cortex* |   |   |   |
| **CTI** | *OpenCTI 6* + *MISP* |   |   |   |
| **Vuln Mgmt** | *OpenVAS / GVM* |   |   |   |
| **Monitoring** | *Prometheus* + *Grafana* |   |   |   |
| **Attack Sim** | *CALDERA* + *Atomic Red Team* |   |   |   |
| **JumpBox** | Win Srv 2022 |   |   |   |
| **TOTAL** |   |   |   | < 1 TB |

> Après quelques recherches, je remplirai les cellules vides 

# 4. Roadmap de déploiement

> Pré-requis environnement de travaille virtuel : Mise en place de l'infrastructure vCenter/ESXI/vSAN/datastore/VLAN...\
> Security Onion : \
> Wazuh Mgr + agents : \
> CTI & Vuln : \
> SOAR & Case Mgmt : \
> Playbooks & Dashboards : \
> Purple Team : exécuter Atomic Red Team, valider détections, ajuster corrélation\

# 5. Références

> [Security Onion 2.4](https://docs.securityonion.net/en/2.4/ "Security Onion 2.4")\
> [Wazuh](https://documentation.wazuh.com/current/index.html "Wazuh")\
> [MISP](https://www.misp-project.org/ "MISP")\
> [OpenCTI](https://docs.opencti.io/latest/ "OpenCTI")\
> [GVM](https://github.com/greenbone/gvmd "GVM (Greenbone)")\
> [TheHive](https://github.com/TheHive-Project/TheHive "TheHive 4 (Le 5 est sous license)")\
> [Cortex](https://github.com/TheHive-Project/Cortex "Cortex")\
> [Shuffle](https://github.com/Shuffle/Shuffle "Shuffle")\
> [Sigma](https://github.com/SigmaHQ/sigma "Sigma (règles Sigma)")\
> [Prometheus](https://prometheus.io/ "Prometheus")\
> [Grafana](https://grafana.com/ "Grafana")\
> [Atomic Red Team](https://github.com/redcanaryco/atomic-red-team "Atomic Red Team")\


