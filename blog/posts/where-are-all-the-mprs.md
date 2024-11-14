---
date:
    created: 2024-11-13
categories:
    - Opinion
authors:
    - fria
tags:
    - MPR
    - VPN
license: BY-SA
---
# Where are all the Multi-Party Relays?

Multi-Party Relays are a technology that aims to provide better privacy protections than VPNs do. They show a lot of promise, but it's been years and there's even fewer options than ever. What happened?<!-- more -->

VPNs were originally meant to be used to access a network privately when you’re not physically there, with encryption in between, so you can get to your files or manage network-related things from wherever you are. It extends the security you’d expect from being physically at your LAN.

Commercial VPNs like ProtonVPN allow you to connect to their network and then connect to your destination. This keeps sites and services you connect to from knowing your real IP address and using it as a metric to track you. But there’s a problem here; you now need to fully trust your VPN provider in the same way you need to trust your ISP with all your internet traffic. This “shifting trust” problem has haunted VPNs for as long as they’ve been marketed as a privacy product. It’s clear that a better solution is needed.

MixNets like Tor have solved this problem by decoupling the sender from the destination. No relay along the path has all the information: the guard relay knows who you are but not where you’re going, the middle relay knows the other two relays, and the exit relay knows the destination but not the sender. There’s also separate encryption between each relay.

Tor provides great privacy properties, but the relays are run by volunteers and as such it can be extremely slow and unreliable. Anyone who’s tried to download a file on it knows how painful it can be. Even normal browsing can be slow, with potentially minutes collectively wasted on loading times in any given browsing session. Tor is hands down the most private way to browse the web, and if your threat model calls for it there is no substitute. But for VPN users that want better privacy, a paid solution where you have access to fast and reliable servers like on a VPN but also separation between who you are and what you’re connecting to is the obvious next step.

Enter Multi-Party Relays. Services like iCloud Private Relay and INVISV Multi-Party Relay take inspiration from MixNets like Tor and separate the sender from the destination using two relays operated by different parties, as the name implies. There’s separate encryption between each relay as well. MPRs *do* require you to trust that the two parties don’t collaborate to correlate your traffic, so keep that in mind.

Typically, the first relay is controlled by the provider, so Apple in the case of Private Relay and INVISV in the case of their offering, and the second relay is controlled by another company such as Fastly or Cloudflare. These are big names so you won’t need to worry about reliability.

They also provide *speed*. Private Relay uses the QUIC protocol and as a result it’s lightning fast. You wouldn’t even know you were connecting to two servers in between your cat videos. The reliability is so good that I forget I even have it on. It even integrates with Safari and gives you a different IP address for different websites, similar to Tor’s stream isolation.

So why haven’t MPRs taken off? INVISV’s Pretty Good Phone Privacy service never seemed to [make it out of beta](https://invisv.com/pgpp/#pgpp-release-notes). [INVISV partnered with Vivaldi](https://invisv.com/articles/vivaldi-privacy-guard) but I can’t seem to find any mention of it in the Vivaldi settings or on their website outside of the original [announcement post](https://vivaldi.com/blog/desktop/privacy-guard-your-privacy-matters-vivaldi-browser-snapshot-3319-12/). INVISV [shutdown their service](https://invisv.com/articles/service_shutdown.html) back in June, I hope to see more from them in the future because they were providing something that currently isn’t possible to get anymore on Android.

That leaves [iCloud Private Relay](https://support.apple.com/en-us/102602) as the only offering that I’m aware of, but it’s limited to Apple devices only. Great for Apple users, but everyone else is left high and dry. As is Apple’s way, they didn’t want any extra inconvenience from using their service so they restrict you to your real country and timezone, so you don’t have the same freedom to choose a server wherever in the world you want like a VPN service would allow.

It really is a shame to see such a promising technology go so underutilized. Perhaps the VPN companies could make their own MPR product and fill the gap in the market, only time will tell.
