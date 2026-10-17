# Michaël Lalancette

## Analyste en cybersécurité

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Profil-0A66C2?style=flat-square&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/michael-lalancette/)
[![Courriel](https://img.shields.io/badge/Courriel-Contact-6D4AFF?style=flat-square&logo=protonmail&logoColor=white)](mailto:Michael.Lalancette@proton.me)

---

## Profil

Diplômé d'une AEC en cybersécurité, je me spécialise en **gestion des identités et des accès (GIA/IAM)** dans l'écosystème Microsoft Entra : cycle de vie des comptes, authentification forte, accès conditionnel et gestion des accès privilégiés.

Ce choix découle de mes laboratoires en détection et en investigation d'incidents. Une constante revenait d'une analyse à l'autre : l'attaque finissait toujours par viser des comptes/identités (identifiants exfiltrés, mouvement latéral vers le contrôleur de domaine, faux Google Authenticator). Comprendre comment les attaquants compromettent les comptes, abusent des privilèges et maintiennent leur accès m'a naturellement mené vers la GIA.

Je cherche un premier poste d'**analyste GIA** dans la grande région de Montréal.

---

## Certifications et formation

| Certification/formation | Organisme | Date |
| --- | --- | --- |
| SC-300 : Microsoft Identity and Access Administrator | Microsoft | En cours (novembre 2026) |
| SC-900 : Microsoft Security, Compliance, and Identity Fundamentals | Microsoft | Septembre 2026 |
| SOC Level 1 | TryHackMe | Octobre 2025 |
| AEC Cybersécurité : Protection et Défense | Collège Montmorency | 2023-2024 |

---

## Compétences

### Identités et accès

- Microsoft Entra ID (P2) : utilisateurs, groupes, rôles et applications
- RBAC : attribution de rôles Entra et Azure par profil, selon le principe du moindre privilège
- Entra ID Protection : traitement des utilisateurs à risque (confirmer la compromission, réinitialiser le mot de passe, révoquer les sessions)
- Identités managées pour l'automatisation (Logic Apps)
- Active Directory : comptes, groupes et stratégies
- **En développement (laboratoire GIA) :** accès conditionnel, MFA, PIM, revues d'accès, Microsoft Graph, identité hybride AD → Entra ID

### Détection et investigation

- Requêtes KQL et SPL, SIEM Splunk (Universal Forwarder, index, alertes)
- Investigation de phishing : en-têtes SMTP, SPF/DKIM/DMARC, liens, pièces jointes, sandbox
- Analyse PCAP et reconstruction de sessions malveillantes (Wireshark)
- Extraction et enrichissement d'IOC, cartographie MITRE ATT&CK
- Rapports d'incident : chronologie, IOC et recommandations

### Cloud et infrastructure

- Azure : VM, NSG, Azure Policy, Cost Management
- Windows, Linux
- Virtualisation et réseaux isolés (VMware), segmentation (pfSense), TCP/IP, DNS
- Scripting : PowerShell, Python, Bash

---

## Outils

**Identité et accès** · Microsoft Entra ID · Entra ID Protection · Intune · Active Directory  
**Cloud et automatisation** · Azure · Logic Apps  
**Requêtes et scripts** · KQL · SPL · PowerShell · Python · Bash  
**Analyse et investigation** · Splunk · Suricata · Wireshark · CyberChef · VirusTotal · AbuseIPDB · Shodan · MITRE ATT&CK  
**Infrastructure** · Windows · Linux · VMware · Docker · pfSense

---

## Projets

#### Laboratoire GIA · Microsoft Entra ID

![Statut : en cours](https://img.shields.io/badge/Statut-En%20cours-orange?style=flat-square)

**Documentation :** [IAM-Entra-Lab](https://github.com/Michael-Lalancette/IAM-Entra-Lab) *(en construction)*

Mise en place des processus de GIA d'une organisation fictive dans un tenant Microsoft Entra ID P2, en préparation à la SC-300.

- Cycle de vie : création, modification et désactivation de comptes à partir d'un fichier « RH » (CSV) avec PowerShell et Microsoft Graph
- Groupes dynamiques et attribution des accès par groupe
- Accès conditionnel : MFA obligatoire, blocage de l'authentification héritée, tests en mode rapport seul
- Authentification résistante à l'hameçonnage : clés d'accès (FIDO2) et Temporary Access Pass
- PIM : rôles d'administration juste-à-temps avec approbation
- Revues d'accès et packages d'accès
- Identité hybride : synchronisation d'un Active Directory local vers Entra ID
- Surveillance : requêtes KQL sur les journaux de connexion et d'audit d'Entra ID (ex. ajout à un rôle privilégié hors PIM)

---

#### SOC Lab · Microsoft Sentinel et Defender XDR · Octobre 2026

![Statut : terminé](https://img.shields.io/badge/Statut-Termin%C3%A9-green?style=flat-square)

**Documentation :** [SOC-Lab-Sentinel-Defender](https://github.com/michael-lalancette/soc-lab-sentinel-defender)

Montage complet d'un laboratoire SecOps Microsoft dans un seul tenant, de l'ingestion des journaux jusqu'à la détection, l'automatisation, l'investigation et threat hunting.

- Architecture de 3 VM (Windows 11 (VMware), Windows Server (AZ), Ubuntu 24.04 (AZ)) qui envoient leur télémétrie vers Sentinel et Defender XDR avec Azure Monitor Agent (AMA), des règles de collecte (DCR) et la Logs Ingestion API
- Intégration de Defender for Endpoint, Entra ID P2 (Identity Protection) et Intune, avec un modèle de comptes par rôle selon le moindre privilège
- 5 détections (scheduled, near-real time, liste de surveillance, personnalisée (*_CL*), TI/UEBA), chacune associée à une technique MITRE ATT&CK
- Flux de gestion des incidents : règles d'automatisation, playbook Logic Apps qui ajoute des commentaires structurés, tags, triage, classification et actions de réponse
- Requêtes KQL pour l'investigation et la hunt, et renseignement sur les menaces au format STIX

> **Leçon retenue :** Ce lab m'a montré, pas seulement en théorie mais en pratique, que l'identité est au centre de la sécurité : la plupart des incidents investigués remontaient à un compte, à ses privilèges ou à ses connexions. C'est ce qui m'a amené à vraiment m'intéresser à la gestion des identités et des accès (GIA/IAM) avec Entra ID.

---

#### Analyse d'e-mails de phishing · Octobre 2025

![Statut : terminé](https://img.shields.io/badge/Statut-Termin%C3%A9-green?style=flat-square)

**Documentation :** [SOC-Phishing](https://github.com/Michael-Lalancette/SOC-Phishing)

Investigation complète d'un e-mail de phishing menant à trois malwares (BitRAT, AsyncRAT, mineur Monero).

- Analyse des en-têtes (IP d'envoi, SPF/DKIM/DMARC, sauts Received) : usurpation confirmée
- Réputation des domaines et des IP (VirusTotal, OTX, AbuseIPDB)
- Décodage d'un loader PowerShell avec CyberChef (délai anti-sandbox)
- Analyse dynamique en sandbox et hachage des charges utiles (SHA256)
- Cartographie MITRE ATT&CK, rapport d'IOC et recommandations, dont une politique DMARC `p=reject`

> **Leçon retenue :** l'usurpation a réussi faute d'une politique DMARC stricte. Authentifier l'expéditeur relève aussi de la gestion des identités, au même titre qu'authentifier l'utilisateur.

---

#### Laboratoire SOC avec Splunk · Septembre 2025

![Statut : terminé](https://img.shields.io/badge/Statut-Termin%C3%A9-green?style=flat-square)

**Documentation :** [SOC-Splunk-Lab](https://github.com/Michael-Lalancette/SOC-Splunk-Lab)

Conception et déploiement d'un mini-SOC de 4 VM dans un réseau isolé.

- SIEM Splunk Enterprise et honeypot IIS avec leurres
- Collecte et indexation des journaux Windows et IIS via Universal Forwarder
- Alerte SPL en temps réel (Triggered Alerts, courriel via Mailtrap, CSV lookup)
- Tableau de bord Splunk pour suivre les accès au honeypot
- Simulation adverse (reconnaissance → accès → exfiltration), chronologie et cartographie MITRE ATT&CK

> **Leçon retenue :** une détection efficace dépend d'abord de la qualité des journaux collectés et d'une bonne compréhension du comportement normal de l'environnement.

---

#### Analyse de PCAPs avec Wireshark · Septembre 2025

![Statut : terminé](https://img.shields.io/badge/Statut-Termin%C3%A9-green?style=flat-square)

**Documentation :** [PCAP-Investigation](https://github.com/Michael-Lalancette/PCAP-Investigation)

Investigation de trois captures d'infections réelles (Qakbot, OriginLogger, faux Google Authenticator) selon une même méthode en cinq étapes.

- Identification de l'hôte infecté et de l'utilisateur (NBNS, SMB, Kerberos)
- Vecteur initial, malware (Export Objects, hachages) et trafic C2
- Exfiltration SMTP en clair et mouvement latéral SMB vers le contrôleur de domaine
- Extraction des IOC, cartographie MITRE ATT&CK et rapports d'investigation

> **Leçon retenue :** le trafic réseau permet souvent de reconstruire toute la chaîne d'attaque, du vecteur initial jusqu'aux comptes visés : identifiants volés, accès au contrôleur de domaine.

---

*Dernière mise à jour : octobre 2026*
