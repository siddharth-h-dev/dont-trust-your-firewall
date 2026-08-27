# <img src="../assets/DTyF Logo.png" width="64" height="64" align="center"> How to implement DTyF
Made the decision to Implement DTyF? **GREAT!** Don't know *what* to do exactly? **YOU ARE AT THE RIGHT PLACE!**

## Separating the firewall from local network management:-
If you don't want to trust your firewall, **you should not let it have control of your entire network**.
So the first thing we'll do is **not let the firewall manage your network at all**.
From now, **the firewall's ONLY JOB is to manage EDGE routing**.

This includes:-
- NAT (Network Address Translation).
- Firewalling access to the internet (Different config for different VLANs also included).
- Edge Routing (Normal routing, routing traffic through Tor, routing trallic through VPN, etc.).
- DNS (except Local Network DNS). **NOTE: *Ad-blocking* DNS is not a problem.**
- etc.

and DOES NOT INCLUDE:-
- Inter-VLAN Routing.
- Local DNS (DNS to your media server, for example).
- DHCP for your network.
- etc.

There are two ways you can manage your local network:-
1. **Using a Layer-3 Managed Switch**: This is the most conventional way. Unlike Layer-2 Managed switches, Layer-3 Switches can do Inter-VLAN Routing, DHCP, etc. If you don't have one, you can do the other way.
2. **Using another router (Physical or virtualized)**: This is unconventional, but is better for people who don't have L3 switch or their network infrastructure is virtualized. You can use a router by disabling the WAN features (By plugging the firewall link into its LAN cable, for example). If you are virtualizing, use a lightweight routing OS (Like OpenWRT) and configure it as such.

The first way is recommended since L3 switches have specialized hardware whose benefits software cant replicate, but not everyone has L3 switch, so the 2nd way makes DTyF *more accessible*.

## Isolating your firewall from the rest of your network:-
To achieve this, you can take the below measures:-
- **Use VLANs** - VLANs keep devices on separate subnets.
- **Restrict Traffic** - Configure the L3 switch such that the firewall itself can't talk to any devices on your network.

## Being prepared for a firewall compromise:-
You can apply the following preventive measures:-
- **L3 switch also does some firewalling** - Your L3 switch will also be a firewall. 2 layers of defense!
- ***Kill Switch*** - This is just my idea. If you suspect your firewall is compromised, *sever the connection between firewall and L3 switch*.
There are other measures you can implement which I have not mentioned.


