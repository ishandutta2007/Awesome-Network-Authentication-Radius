# Awesome-Network-Authentication-Radius

## Top Network Authentication & RADIUS Tools Ecosystem

**Curated List of SaaS Products & Open-Source GitHub Projects**  
*Focused on 802.1X/EAP, NAC Policy Enforcement & Self-Hosted AAA*  
**Last updated: March 2026**

This repository tracks notable **SaaS platforms** and **open-source projects** for **Network Authentication & RADIUS**. These tools provide the AAA (Authentication, Authorization, Accounting) layer for wired and wireless networks — validating user and device credentials, enforcing access policies, and logging sessions — typically speaking the RADIUS protocol to switches, access points, and VPN gateways.

**Examples** include FreeRADIUS, ToughRADIUS, Radiator Policy Server, Cisco ISE, Aruba ClearPass, Portnox Cloud, JumpCloud Cloud RADIUS, and Foxpass (the category leaders).

**Open-source emphasis**: This section is heavily expanded with every major active project for self-hosting, 802.1X/EAP support, and transparent policy logic — ideal for network engineers who want AAA infrastructure they control rather than per-device SaaS licensing.

Contributions welcome! Open a PR to add/update entries. Keep descriptions factual and link to official sites.

## Table of Contents
- [SaaS/Hosted Platforms](#saas-hosted-platforms)
- [Open-Source GitHub Projects](#open-source-github-projects)
- [How to Contribute](#how-to-contribute)
- [Disclaimer](#disclaimer)

## SaaS/Hosted Platforms

- **Cisco Identity Services Engine (ISE)** — **The enterprise NAC standard** with RADIUS, TACACS+, device profiling, posture assessment, BYOD onboarding, and guest access [citation:2][citation:13]. **Supports EAP-MD5, LEAP, PEAPv0/v1, EAP-TLS, and EAP-FAST** with certificate-based mutual authentication [citation:13]. **Trade-offs**: **expensive licensing** and complex deployment; typically requires dedicated appliance or VM infrastructure. **Best for large enterprises** already standardized on Cisco networking.

- **Aruba ClearPass Policy Manager** — **Role- and device-based NAC** for multivendor wired, wireless, and VPN infrastructure [citation:3]. **Built-in context-based policy engine**, RADIUS, TACACS+, OnConnect enforcement, device profiling, posture, onboarding, and guest access [citation:3]. **Aruba Exchange Program** integrates with third-party security vendors for automated threat response [citation:3]. **Best for Aruba networking customers** and organizations needing granular role-based micro-segmentation.

- **Portnox Cloud** — **Cloud RADIUS with optional local proxy** for on-premises resilience. **Two Azure server farms** (US and Netherlands) with N+2 redundancy [citation:4]. **Local RADIUS servers** act as proxies to the cloud, with a **7-day outage cache** of successful authentications for internet disruptions [citation:4]. **Supports RadSec (RADIUS over TLS)** and mTLS validation [citation:15]. **Best for organizations wanting cloud-managed RADIUS** without maintaining physical servers, especially those needing local failover.

- **JumpCloud Cloud RADIUS** — **RADIUS-as-a-Service** with delegated authentication to established IdPs including Microsoft Entra ID [citation:5]. **Automatically generates shared secrets** for WAP-to-RADIUS authentication, supports **MFA for VPN/Wi-Fi login**, and **VLAN mapping** for access restriction [citation:5]. **Best for JumpCloud directory customers** wanting centralized Wi-Fi and VPN authentication.

- **Foxpass** — **Cloud RADIUS and LDAP since 2015**, with **RadSec (RADIUS over TLS)** supported while less-secure protocols (PAP, PEAP over RADIUS/UDP) require explicit enabling [citation:8]. **99.95% availability** since founding [citation:8]. Integrates with Google Workspace, Azure/Entra ID, Okta, OneLogin, Active Directory, and LDAP [citation:8]. **Best for security-conscious organizations** wanting RadSec by default.

- **SecureW2** — **Cloud RADIUS and PKI** for certificate-based Wi-Fi authentication. **Replaces on-premises RADIUS and certificate infrastructure** with cloud-native PKI, SCEP profile management, and integrations with Jamf, Kandji, Okta, and Splunk [citation:7]. **Best for organizations wanting certificate-based 802.1X** without managing internal PKI.

- **Microsoft NPS** — **Windows Server role implementing RADIUS** for wireless, VPN, RD Gateway, and switch authentication [citation:10]. **Integrates with Active Directory** for SSO, supports RADIUS proxying and accounting to SQL Server or log files [citation:10]. **Cannot be installed on Server Core** [citation:10]. **Best for Windows-centric organizations** already running AD DS.

## Open-Source GitHub Projects

- **[FreeRADIUS](https://github.com/FreeRADIUS/freeradius-server)**  
  **The most widely used RADIUS server in the world** — GPL-2.0 licensed. **Powers major ISPs and telcos**, is the technology behind **eduroam**, and is used by all cloud identity providers [citation:1]. **Authenticates one-third of all users on the Internet** [citation:1]. **Scales to tens of millions of users** — deployed in national ISPs with 15M+ users [citation:1]. **Multi-protocol policy server** implementing RADIUS, DHCP, BFD, and ARP, with a **BSD-licensed RADIUS client library**, PAM library, and Apache module [citation:1]. **Infinitely flexible policy language**, AD integration, and support for Vendor-Specific Attributes including USR non-standard ones [citation:1][citation:12]. **Runs on all Unix-like platforms** with full IPv6 support [citation:12]. **Commercial support available via InkBridge Networks** [citation:1]. **Best for any organization needing a proven, scalable, self-hosted RADIUS server** — the reference implementation the entire industry builds on.

- **[ToughRADIUS](https://github.com/talkincode/toughradius)**  
  **The modern Go-based RADIUS server for ISPs and enterprises** — **supports standard RADIUS, RadSec (TLS over TCP), and a full EAP/802.1X suite** including EAP-MD5, EAP-MSCHAPv2, EAP-TLS, PEAPv0/EAP-MSCHAPv2, and EAP-TTLS [citation:11]. **React Admin web interface** for user management, online session monitoring, and log auditing [citation:11]. **Multi-vendor VSA support** for Cisco, Mikrotik, Huawei, H3C [citation:11]. **PostgreSQL or SQLite** backends. **Built with Go for high concurrency** [citation:11]. **Compatibility note**: PEAP and EAP-MSCHAPv2 are compatibility-first methods — prefer EAP-TLS for new deployments [citation:11]. **Best for ISPs and enterprises wanting a modern, web-managed RADIUS server** with broad EAP support.

- **[Radiator Policy Server](https://github.com/radiatorsoftware/radiator-server)**  
  **The Rust-based next-generation standalone RADIUS server** — **achieves concurrency, high performance, and security** with a **monitoring and management dashboard** and **REST API** for upstream/downstream integration [citation:9]. **Up to latest standards** with a variety of integration options. **Docker image available** (29.2 MB) [citation:9]. **Best for teams wanting a modern, performant RADIUS server** with API-driven management.

### Additional Strong Open-Source Options

- **daloradius** — Web-based RADIUS management interface for FreeRADIUS. Provides user management, accounting reports, and billing integration for ISPs and hotspot operators.
- **RadiusDesk** — RADIUS management platform with a focus on hotspot and mesh networking deployments.
- **PacketFence** — Open-source NAC solution with RADIUS support, captive portal, and device registration.

**Frameworks for building custom systems**: Combine **FreeRADIUS** for the most battle-tested AAA engine with infinitely flexible policy language, **ToughRADIUS** for a modern web-managed server with broad EAP support, and **Radiator Policy Server** for API-driven management with Rust performance — to build a RADIUS infrastructure tailored to your scale, management preferences, and EAP requirements.

## How to Contribute

1. Fork the repo.
2. Add/edit entries in `README.md` (follow existing format).
3. Include: name, link, 1–2 sentence description, and whether it's SaaS or open-source.
4. Submit PR with a short explanation.

Star the repo if you find it useful!

## Disclaimer

- This is a **community-curated** list — not exhaustive and not an endorsement.
- Network authentication tools differ significantly in deployment model, EAP method support, and management interface. **FreeRADIUS authenticates one-third of all Internet users** and is the de facto open-source standard, but requires manual configuration and lacks a built-in UI [citation:1]. **ToughRADIUS adds a React Admin web interface and broad EAP support** including EAP-TLS, PEAP, and EAP-TTLS [citation:11]. **Radiator Policy Server brings Rust performance and REST API management** [citation:9]. **Cisco ISE and Aruba ClearPass are enterprise NAC platforms** with deep policy engines and vendor integrations, at significantly higher cost and complexity [citation:3][citation:13]. **Portnox and JumpCloud are cloud-managed RADIUS** — Portnox offers local proxy with outage cache [citation:4], JumpCloud offers delegated authentication to Entra ID [citation:5]. **Foxpass enforces RadSec by default** and requires explicit enabling of less-secure protocols [citation:8]. **PEAP and EAP-MSCHAPv2 carry NTLMv1-like attack surface** — prefer EAP-TLS where you control client certificates [citation:11].
- Self-hosted open-source solutions require proper certificate management for EAP-TLS, database backups for user credentials, and careful firewall rules for RADIUS ports (1812/1813) and RadSec (2083).

---

**Made for network engineers, sysadmins, and organizations building RADIUS and 802.1X authentication infrastructure they can own and control.**
Let's make network authentication more open, standards-compliant, and self-hostable.
