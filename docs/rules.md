# Rules of DTyF
There are many things to follow, condensed into three basic rules.
## 1. The Firewall must only handle Edge-Routing.
- **Your internet-facing firewall SHOULD NOT manage your local network**. Hand that duty down further down the network stack (such as an L3-Managed switch or another router OS in a VM).
- This ensures that **A compromised firewall won't have control of your entire network**.
## 2. The Firewall must be isolated from your network.
- Only the *local network master* (L3-Managed switch or router OS) should be connect to your firewall. Isolate your firewall from the rest of your network. Treat it like an Untrusted Entity.
- This ensures that **A compromised firewall won't have access to anything on your network except for the *local network master***
## 3. The Network must be Prepared to resist attacks from a compromised firewall.
- **The *local network master* must be able to defend against a compromised firewall.**
- **Employ prevention measures** (such as denying packets from the firewall itself by default, having some default-deny rules for stuff like SSH, etc.).
To know how to implement DTyF in your own network, see "How to Implement".
