# Michaël Lalancette

Cybersécurité Microsoft | Détection, Investigation & Gestion des identités

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Profil-0A66C2?style=flat-square&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/michael-lalancette/)
[![Courriel](https://img.shields.io/badge/Courriel-Contact-6D4AFF?style=flat-square&logo=protonmail&logoColor=white)](mailto:Michael.Lalancette@proton.me)

---

## Profil

Diplômé d'une AEC en cybersécurité, j'oriente actuellement mon développement professionnel vers la gestion des identités et des accès (IAM) dans l'écosystème Microsoft Entra.

Mes laboratoires en détection et en investigation d'incidents m'ont permis de constater qu'une grande partie des attaques visent ultimement les identités, leurs privilèges ou leurs accès. Comprendre comment les attaquants compromettent les comptes m'a naturellement amené à approfondir la gestion des identités et des accès.

Ouvert aux opportunités en GIA/IAM, en administration Entra ID et en sécurité Microsoft, dans la grande région de Montréal.

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

### Sécurité des identités

- Microsoft Entra ID (P2) : users, groups, roles, enterprise applications, administrative units et custom roles
- Identity Lifecycle : bulk operations (CSV), scripts Microsoft Graph PowerShell, dynamic groups et group-based licensing
- Hybrid identity : synchronisation AD DS vers Entra ID avec Entra Connect (PHS, PTA, Seamless SSO)
- Active Directory : users, groups et GPO
- RBAC : rôles Entra et Azure attribués par profil, selon le principe de least privilege

### Authentification et gouvernance

- MFA, passkeys (FIDO2), Temporary Access Pass et SSPR
- Conditional Access : baseline, risk-based CA, report-only et What If
- Entra ID Protection : risky users (confirm compromised, reset password, revoke sessions)
- PIM : rôles just-in-time avec approbation
- Access reviews, access packages et entitlement management

### Détection et investigation

- Microsoft Sentinel, Defender XDR, Defender for Endpoint, Splunk
- KQL et SPL : analytics rules, hunting queries, sign-in et audit logs
- Investigation de phishing : en-têtes SMTP, SPF/DKIM/DMARC, liens, pièces jointes, sandbox
- Analyse PCAP (Wireshark), extraction d'IOC et mapping MITRE ATT&CK
- Rapports d'incident : timeline, IOC et recommandations

### Automatisation et infrastructure

- PowerShell (Microsoft Graph), Python, Bash, Logic Apps et managed identities
- Azure : VM, NSG, Azure Policy, Log Analytics
- Intune, Windows LAPS, Windows 11, Windows Server, Linux
- VMware, pfSense, TCP/IP, DNS

---

## Outils

| Domaine | Outils |
| --- | --- |
| **Identités et accès** | Microsoft Entra ID · Entra ID Protection · Entra Connect · Cloud Sync · Active Directory · Intune · Windows LAPS · Windows Hello for Business |
| **SIEM et XDR** | Microsoft Sentinel · Microsoft Defender XDR · Defender for Endpoint · Splunk |
| **Collecte et automatisation** | Log Analytics · Azure Monitor Agent (AMA) · Data Collection Rules (DCR) · Logs Ingestion API · Splunk Universal Forwarder · Logic Apps |
| **Requêtes et scripts** | KQL · SPL · PowerShell (Microsoft Graph) · Python · Bash |
| **Analyse et threat intelligence** | Wireshark · CyberChef · VirusTotal · MITRE ATT&CK · STIX |
| **Infrastructure et systèmes** | Azure (VM, NSG, Azure Policy) · Microsoft 365 · VMware · Windows · Linux · Windows Server · IIS · Docker |

---

## Projets

#### Laboratoire GIA · Microsoft Entra ID

![Statut : en cours](https://img.shields.io/badge/Statut-En%20cours-orange?style=flat-square)

**Documentation :** [IAM-Entra-Lab](https://github.com/Michael-Lalancette/IAM-Entra-Lab) *(en cours)*

Mise en place des processus de GIA d'une organisation fictive *(nimbusID)* dans un tenant Microsoft Entra ID P2, en préparation à la SC-300.

**Réalisé**
- Delegated administration : custom role et administrative units ; une restricted management AU bloque même un Global Administrator, vérifié dans les audit logs
- Identity lifecycle : création de comptes en bloc (CSV) et par script Microsoft Graph PowerShell, dynamic groups et group-based licensing
- External identities : invitations B2B avec email one-time passcode et cross-tenant synchronization vers un tenant partenaire (*Cirrius Partner*)
- Hybrid identity : Entra Connect Sync (PHS, filtrage par OU, writeback), PTA, Seamless SSO, Cloud Sync et hybrid join
- Authentication : passkeys (FIDO2), TAP, Windows Hello for Business, CBA, SSPR avec writeback vers AD et Password Protection on-premises
- Conditional Access : baseline avec exclusion des emergency access, phishing-resistant MFA pour les admins, compliant device (Intune, Windows LAPS), named locations, report-only et What If, CAE et authentication context
- Troubleshooting dans les sign-in et audit logs : appareil non conforme (53000), session révoquée (50133), compte désactivé (50057)


**Prochaines étapes à documenter**
- Risk-based Conditional Access avec ID Protection
- Global Secure Access : accès à une app privée sans VPN
- Applications : SAML SSO, Application Proxy et managed identities
- Defender for Cloud Apps : session policy
- Gouvernance : access packages, access reviews et PIM avec approbation
- Monitoring : requêtes KQL et workbooks sur les sign-in et audit logs

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

*Dernière mise à jour : 28 octobre 2026*
