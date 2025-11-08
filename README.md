# AuthMeExploit - Remastered

## 📖 Important Notes
- 🟡 This project is made for only **EDUCATIONAL PURPOSES** only
- 🟡 This project aiming to show server owners how to protect their Minecraft servers from these Exploits.
- 🟢 Everyone can **download**, **try and test** this exploit for **EDUCATIONAL PURPOSES**

## 🛡️Technical: AuthMe and Proxy Bypass Vulnerabilities

- I. **The Intended Defense-in-Depth Architecture**

In modern, distributed server networks (e.g., Minecraft), a defense-in-depth strategy is employed to layer security controls.
BungeeCord (The Proxy Layer): This component functions as the single, mandatory entry point or "gatekeeper" for all network traffic. It is responsible for routing legitimate player connections to the correct backend server (Hub, Survival, etc.). Its primary security role is to abstract and obscure the backend network, preventing any direct external connections to individual servers.
AuthMe (The Authentication Plugin): This component enforces identity verification. It ensures that any player connecting through the proxy is who they claim to be by requiring a password or other credentials before granting access to server resources.
When correctly implemented, this architecture ensures that all network traffic is (1) proxied and (2) authenticated, providing a robust security posture.
- II. **The Vulnerability: Proxy & Authentication Bypass**

A "Proxy Bypass" is a critical vulnerability that emerges when an attacker can circumvent the proxy layer (BungeeCord) and establish a direct connection to a backend server.
This is almost exclusively achieved through:
Critical Network Misconfiguration: The individual backend servers (Hub, Survival, etc.) are improperly exposed to the public internet. Their ports are left open and are not firewalled to only accept connections from the proxy.
Port Scanning: An attacker systematically scans the host IP address to discover these exposed, non-proxied server ports.
When an attacker successfully bypasses the proxy, they often achieve an "Authentication Bypass" as a direct consequence. The backend server, which is incorrectly configured to be in online-mode: false (trusting the proxy to handle authentication), may fail to re-authenticate the direct connection. This allows the attacker to join the server with any username, including administrative accounts, without credentials.
- III. **Technical Impact and Risk**

The professional impact of this vulnerability is severe and immediate:
Unauthorized Access & Impersonation: Attackers can join servers without credentials, potentially impersonating administrators.
Service Disruption (DoS): Malicious actors can target the backend servers directly, bypassing proxy-level protections.
Loss of Data Integrity: Unauthorized access can lead to the theft or destruction of user data, in-game economies, and world files.
- IV. **Mitigation and Defensive**

Understanding the mitigation is essential for "server security" and preventing this methods:
Strict Firewall Rules (UFW/iptables): This is the most critical and effective mitigation. The firewalls on all backend servers must be configured to only accept incoming connections from the BungeeCord proxy's specific IP address. All other direct connection attempts from the public internet must be dropped. (The exploit relies entirely on this rule not being in place).
Enable bungeecord: true: In the spigot.yml configuration file for every backend server, this setting must be enabled. This instructs the server to only accept connections that have been properly forwarded by the BungeeCord proxy protocol.
Network Segmentation: Backend servers should ideally be placed on a separate internal network or VLAN, making them completely inaccessible from the public internet, reachable only by the proxy server.
By implementing these defensive measures, administrators can ensure their network architecture is secure and that the proxy and authentication layers function as intended.

<img width="1411" height="655" alt="graphic" src="https://github.com/user-attachments/assets/46bd4025-d76b-4a9f-8da0-65832a1dc97d" />


## 📩 Status
- 🔴 Update: **v1.0/6-10-2023** [Outdated]
- 🟢 Update: **v2.0/3-11-2025** [Working] [Notes](https://github.com/kheiron-1337/AuthMe/releases/tag/v2.0_03-11-2025)

## ⚠️ Requirements
- Target server must have **"AuthMe"** or **"AuthMeReloaded"** plugin.
- Target server must have several addresses, ports etc.
- You must download full of the packages from releases.

## ⚠️ Errors
- Check [Error List](https://github.com/kheiron-1337/AuthMe/blob/master/errors.md)

## 🚀 How to use?
- Start "launch.exe" file.
- Write your target server address.
- Wait for the localhost creation process
- After creation process, join to "localhost"
- It will send you random lobbies, ports or servers without logging in on target server.
- Done. You bypassed AuthMe!
<img width="992" height="557" alt="Ekran görüntüsü 2025-11-08 133740" src="https://github.com/user-attachments/assets/32d2a37c-0903-4c51-8d3d-f7b028848218" />

  

## 📥 Downloads
- Release v1.0/06-10-2023
- [Release v2.0/03-11-2025](https://github.com/kheiron-1337/AuthMe/releases/tag/v2.0_03-11-2025)
- [Download ZIP - Last Release](https://codeload.github.com/kheiron-1337/AuthMe/zip/refs/heads/master)
