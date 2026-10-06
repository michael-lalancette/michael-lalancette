# 👨‍💻 Michaël Lalancette | Analyste en Cybersécurité


[![LinkedIn](https://img.shields.io/badge/LinkedIn-Profil-blue)](https://www.linkedin.com/in/michael-lalancette/)
[![Email](https://img.shields.io/badge/Email-Contact-red)](mailto:Michael.Lalancette@proton.me)

> ⚠️ Projet Microsoft Sentinel & Defender XDR à venir prochainement!



---

## 🎯 Objectif Professionnel

Diplômé d'une AEC en cybersécurité, je me spécialise présentement en surveillance, triage d'alertes et réponse aux incidents avec **Microsoft Sentinel** et **Defender XDR**  dans mes propres laboratoires SOC.    

> Je cherche un premier poste d'**analyste SOC** où mettre en pratique la détection, l'investigation et la réponse aux incidents au quotidien. 


---

## 📜 Formations & Certifications

* **AEC Cybersécurité : Protection et Défense** | *Collège Montmorency* | *2023-2024*
* **SC-900 : Microsoft Security, Compliance, and Identity Fundamentals** | *Microsoft* | *Septembre 2026*
* **TryHackMe : SOC Level 1** | *[TryHackMe](https://tryhackme.com/)* | *Octobre 2025*

**En cours :**
- **SC-200 : Microsoft Security Operations Analyst Associate** | *Microsoft* | *Octobre 2026*




## 💼 Compétences

### **Détection & surveillance**
- SIEM : Microsoft Sentinel (Log Analytics, data connectors, AMA, DCR) et Splunk (Universal Forwarder, index)
- XDR et EDR : Defender XDR, Defender for Endpoint (EDR, règles ASR)
- Règles de détection en KQL (analytics rules scheduled et NRT, watchlists, custom detections) et en SPL
- UEBA, anomalies et threat intelligence (indicateurs STIX, TI map)
- Mapping MITRE ATT&CK et analyse de couverture
- Déploiement de honeypots et d'infrastructures de détection

### **Réponse aux incidents**
- Triage d'alertes et priorisation par criticité
- Investigation : attack story, entités, device timeline
- Réponse sur l'appareil : live response, investigation package, isolement
- Identités compromises : Entra ID Protection (confirmer le compromis, réinitialiser, révoquer les sessions)
- Rapports d'incident : chronologie, IOCs, MITRE ATT&CK et recommandations

### **Threat hunting & investigation**
- Threat hunting en KQL (advanced hunting, hunting queries, bookmarks)
- Analyse PCAP et reconstruction de sessions malveillantes (Wireshark)
- Investigation de phishing : en-têtes SMTP, SPF/DKIM/DMARC, liens, pièces jointes, sandbox
- Extraction et enrichissement d'IOCs

### **Gestion des vulnérabilités**
- Inventaire, priorisation des CVE (CVSS, exploit disponible, exposition), demande de remédiation et vérification avec Defender Vulnerability Management

### **Identité, accès & automatisation**
- Entra ID, Intune, RBAC (rôles Entra et Azure par profil SOC, selon le principe du moindre privilège)
- Playbooks Logic Apps (managed identity) et automation rules
- Scripting : Python, Bash, PowerShell

### **Infrastructure**
- Windows, Linux, Active Directory
- Azure : VM, NSG, Azure Policy, Cost Management
- Virtualisation et réseaux isolés (VMware), segmentation (pfSense), TCP/IP, DNS

---

## 💡 Outils

**SIEM, XDR & détection**  
Microsoft Sentinel • Defender XDR • Defender for Endpoint • Splunk • Suricata • MITRE ATT&CK

**Requêtes & scripts**  
KQL • SPL • Python • Bash • PowerShell

**Analyse & investigation**  
Wireshark • CyberChef • VirusTotal • AbuseIPDB • Shodan

**Identité, cloud & automatisation**  
Entra ID • Intune • Azure • Logic Apps

**Infrastructure & systèmes**  
Linux • Windows • Active Directory • VMware • Docker • pfSense

---

## 📂 Projets

#### **Laboratoire SC-200 · Microsoft Defender XDR et Sentinel** - *Octobre 2026 - à venir*
[![Statut](https://img.shields.io/badge/Statut-En%20cours-orange)]()  
👉 **[Documentation complète du projet](https://github.com/Michael-Lalancette/SOC-Sentinel-XDR)** - *en construction*

* Environnement SecOps complet, monté de zéro dans un seul tenant : Defender XDR, Defender for Endpoint, Microsoft Sentinel, Entra ID P2, Intune, VM Azure et VM locale.
   * Ingestion dans Sentinel via data connectors, AMA et DCR : Windows, Syslog, Entra ID, Azure Activity, threat intelligence
   * Analytics rules KQL (scheduled, NRT, watchlist) et custom detection Defender XDR, testées contre des attaques simulées
   * UEBA, anomalies en Flighting et threat intelligence (TI map)
   * Playbook Logic Apps et automation rules pour automatiser le triage
   * Investigation et réponse : attack story, device timeline, live response, isolement d'appareil, Identity Protection
   * Threat hunting en KQL (advanced hunting, hunting queries)
   * Gestion des vulnérabilités avec Defender Vulnerability Management
   * Rôles Entra et Sentinel attribués par profil SOC, selon le principe du moindre privilège
> Couverture des trois domaines de la SC-200 : gérer l'environnement SecOps, répondre aux incidents, faire du threat hunting.

---

#### **Analyse d'e-mails de phishing** - *Octobre 2025*
[![Statut](https://img.shields.io/badge/Statut-Terminé-green)]()  
👉 **[Documentation complète du projet](https://github.com/Michael-Lalancette/SOC-Phishing)**

* Investigation complète d'un e-mail de phishing menant à trois malwares (BitRAT, AsyncRAT, miner Monero) :
   * Analyse des en-têtes (sender IP, SPF/DKIM/DMARC, Received hops) : spoofing confirmé
   * Vérification de réputation des domaines et IP (VirusTotal, OTX, AbuseIPDB)
   * Décodage d'un loader PowerShell avec CyberChef (sleep anti-sandbox)
   * Analyse dynamique en sandbox et hashing des payloads (SHA256)
   * Cartographie MITRE ATT&CK (TTPs)
   * Rapport d'IOCs et recommandations, dont une politique DMARC `p=reject`

---

#### **Laboratoire SOC avec Splunk** - *Septembre 2025*
[![Statut](https://img.shields.io/badge/Statut-Terminé-green)]()  
👉 **[Documentation complète du projet](https://github.com/Michael-Lalancette/SOC-Splunk-Lab)**

* Conception et déploiement d'un mini-SOC de 4 VM dans un réseau isolé :
   * SIEM Splunk Enterprise et honeypot IIS avec leurres
   * Collecte et indexation des logs Windows et IIS via Universal Forwarder
   * Alerte SPL en temps réel (Triggered Alerts, e-mail via Mailtrap, CSV lookup)
   * Dashboard Splunk pour suivre les accès au honeypot
   * Simulation adversaire (reconnaissance → accès → exfiltration), timeline et mapping MITRE ATT&CK
> Validation du pipeline SOC complet (collecte → détection → alerte → triage → visualisation)

---

#### **Analyse de PCAPs avec Wireshark** - *Septembre 2025*
[![Statut](https://img.shields.io/badge/Statut-Terminé-green)]()  
👉 **[Documentation complète du projet](https://github.com/Michael-Lalancette/PCAP-Investigation)**

* Investigation de trois captures d'infections réelles (Qakbot, OriginLogger, faux Google Authenticator) avec une même méthode en cinq étapes :
   * Identification de l'hôte infecté et de l'utilisateur (NBNS, SMB, Kerberos)
   * Vecteur initial, malware (Export Objects, hashes) et trafic C2
   * Exfiltration SMTP en clair et lateral movement SMB vers le domain controller
   * Extraction des IOCs, mapping MITRE ATT&CK et rapports d'investigation

---

*Dernière mise à jour : octobre 2026*

