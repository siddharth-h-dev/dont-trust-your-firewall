# The Philosophy behind DTyF

DTyF is basically a specific application of the broader **Zero Trust** philosophy. The aim is **ZERO TRUST in your firewall**.

## Your Firewall WILL BE BREACHED
> "Anything that can go wrong, will go wrong."
>
> — *Murphy's Law*

**No firewall is fully secure.** Firewalls can be compromised due to:-
- Bad Configurations
- Zero-Day Exploits
- Evasion Techniques
- the list goes on...

Most people only try to secure their firewall as much as possible, but *never prepare for the day when their firewall is compromised*.

## Do you trust your firewall too much?

There are two ways you can deploy your firewall:-
1. **As the master of your network** - Most small networks have their firewall do edge routing *and* local traffic routing. If such a firewall is compromised, you full network is too.
2. **As an edge-gateway** - The firewall only does edge routing while local network routing is handed off further down the network stack (for example, to a Layer-3 Managed Switch). Most of the time the L3 switch is not prepared to handle a firewall compromise so it still does not change the above scenario.

In both configurations, **The firewall is still trusted too much**. It's not about *only* switching to the 2nd method of deploying a firewall, it's about **not trusting your firewall entirely**.

## How to *not* trust your firewall.

- It seems weird to not trust the firewall because it is one of the core components of your network.
- What I'm trying to say here is you should **Protect your network in a situation where the firewall is compromised**.
- It's an odd task isn't it? *Protection against your own infrastructure* sounds weird right?
- But **This is how you can survive a network breach**. If you follow DTyF, your network will be safe in this situation.
- Read [The Rules of DTyF](rules.md) if you want to know how to do so.
