# Abstract

This document provides a guide on how to accelerate VPN connections to supported VPN providers. The guide is written in a simple and easy-to-follow format, and it is intended for users who are not familiar with VPN technology.

* * *

# Table of Contents

1. [Introduction](https://github.com/galpt/kissvpn#introduction)
   1. [Definition of VPN](https://github.com/galpt/kissvpn#definition-of-vpn)
   2. [History of VPNs](https://github.com/galpt/kissvpn#history-of-vpns)
   3. [Causes of Slow VPN Connections](https://github.com/galpt/kissvpn#causes-of-slow-vpn-connections)
2. [Overview](https://github.com/galpt/kissvpn#overview)
3. [Security and Privacy Considerations](https://github.com/galpt/kissvpn#security-and-privacy-considerations)
   1. [Security](https://github.com/galpt/kissvpn#security)
      1. [Encryption of VPNs](https://github.com/galpt/kissvpn#encryption-of-vpns)
      2. [Common Protocols](https://github.com/galpt/kissvpn#common-protocols)
         1. [OpenVPN](https://github.com/galpt/kissvpn#openvpn)
         2. [WireGuard](https://github.com/galpt/kissvpn#wireguard)
      3. [Endpoint](https://github.com/galpt/kissvpn#endpoint)
   2. [Privacy](https://github.com/galpt/kissvpn#privacy)
4. [Supported VPN Providers](https://github.com/galpt/kissvpn#supported-vpn-providers)
   1. [Cloudflare 1.1.1.1](https://github.com/galpt/kissvpn#cloudflare-1111)
   3. [Mullvad VPN](https://github.com/galpt/kissvpn#mullvad-vpn)
   4. [Proton VPN](https://github.com/galpt/kissvpn#proton-vpn)
5. [Contributing](https://github.com/galpt/kissvpn#contributing)
   1. [Translation](https://github.com/galpt/kissvpn#translation)
   2. [Donation](https://github.com/galpt/kissvpn#donation)
   3. [Other](https://github.com/galpt/kissvpn#other)
6. [Credits](https://github.com/galpt/kissvpn#credits)
7. [References](https://github.com/galpt/kissvpn#references)

* * *

# Introduction

VPNs can be very useful for protecting privacy and security. However, they can also slow down the user's Internet connection. This is because all of the user's traffic is being routed through the VPN server, which adds additional overhead.

This document provides explanation about the VPN technology and how to accelerate VPN connections to supported VPN providers.

## Definition of VPN

A virtual private network (VPN) is a mechanism for creating a secure connection between a computing device and a computer network, or between two networks, using an insecure communication medium such as the public Internet.

A VPN can extend a private network (one that disallows or restricts public access), in such a way that it enables users of that network to send and receive data across public networks as if the public networks' devices were directly connected to the private network. The benefits of a VPN include security, reduced costs for dedicated communication lines, and greater flexibility for remote workers. VPNs are also used to bypass internet censorship. Encryption is common, although not an inherent part of a VPN connection.

A VPN is created by establishing a virtual point-to-point connection through the use of tunneling protocols over existing networks. A VPN available from the public Internet can provide some of the benefits of a wide area network (WAN). From a user perspective, the resources available within the private network can be accessed remotely.

## History of VPNs

VPN technology was first used in 1996 when a Microsoft employee developed the PPTP. The protocol created a more secure private connection between a user device and the internet. In 1999, the specification was published.

In the early 2000s, VPNs were mostly associated with and used by businesses. The technology wasn't quite used by average online users. At this time, VPNs were being used by businesses to access private business networks. In this use case, organizations were able to access company data from anywhere while looking as if they were in the office. Secure file sharing between different offices became possible.

After this, encryption standards started to become more powerful, and new tunneling protocols were developed. As individuals started to learn about potential online threats and privacy issues, VPN use expanded to individual, at-home users. Privacy scandals, such as WikiLeaks or the separate security leaks by Edward Snowden, were injected into the modern zeitgeist. Around 2017, internet users in the United States learned that ISPs could collect and sell their browsing history, and net neutrality became a concept citizens had to fight for — and effectively lost. A bill was passed by the U.S. House of Representatives in 2019 to bring back net neutrality, but was ultimately blocked by the Senate. Since then, different states have enacted versions of net neutrality laws. With this knowledge, the use of VPNs became a more legitimate need for individuals.

## Causes of Slow VPN Connections

There are a number of factors that can contribute to slow VPN connections, including:
- Routing
- Network Setup
- VPN Protocol
- Server Location
- Encryption Strength
- Server Bandwidth
- CPU/RAM
- Overall Internet Speed

You could browse the Internet to get a better understanding of each one of them.
Before making the assumption on what has caused your VPN connection to be slow, you should consider some of those factors.

* * *

# Overview

This guide provides explanation on how to accelerate VPN connections to supported VPN providers, written in a simple and easy-to-follow format (a.k.a. *"Keep It Simple, Stupid."*), and is intended for users who are not familiar with VPN technology.

The implementation used in this guide was inspired by a term *Dynamic Content Acceleration* which is commonly known as something provided by CDN providers.

* * *

# Security and Privacy Considerations

It is important to note that the methods described in this guide can have some security and privacy implications. This section will explain some of them to not cause a confusion.

# Security

Modern VPNs use strong encryption algorithms so your data between you and your VPN provider will be encrypted and safe.

## Encryption of VPNs

Encryption is a technique used to transform information from its original form, called *plaintext*, into an encrypted form, known as *ciphertext*. It aims to protect the confidentiality and integrity of your online information. You might already heard of the term *[Advanced Encryption Standard (AES)](https://youtu.be/O4xNJsjtN6E)*, which is a widely trusted encryption algorithm by the United States government, military and other organizations.

Encryption ensures that only authorized individuals with the appropriate decryption key can decode the ciphertext and access the original plaintext. 

> :information_source: Note that an encryption/decryption key is a sequence of characters (usually numbers and letters) used to transform plaintext into ciphertext (encryption) and vice versa (decryption). In other words, it’s a code that enables data to be encrypted so that it can only be read by someone with the corresponding key to decrypt it.

## Common Protocols

There are some protocols commonly used by VPNs, including:
- SSL/TLS
- PPTP
- L2TP/IPsec
- OpenVPN
- WireGuard

This guide explains mostly about the WireGuard protocol because it is a modern protocol which is secure, really fast, and used by many VPN providers as of now.

### OpenVPN

[OpenVPN](https://openvpn.net/) is open-source, which means its codebase is publicly available for inspection. Researchers can test for vulnerabilities, substantiate security claims, and refine the product. It uses TLS protocols and the OpenSSL library in combination with a range of other tools to create a reliable and secure VPN connection. Custom OpenVPN applications are available from commercial VPN providers, but the primary source code is created and developed by the OpenVPN Project.

### WireGuard

[WireGuard](https://www.wireguard.com/) is a relatively new tunnelling protocol that seeks to offer better performance and faster speeds than OpenVPN.

The protocol is designed to resolve some of the negative issues commonly associated with IPsec and OpenVPN: frequent disconnections, complex setup for users looking to manually configure, extended reconnection times, and heavy codebases which can make it difficult for researchers to spot bugs. 

WireGuard aims to surpass traditional protocols by using more modern ciphers. It’s codebase is only 4000 lines – around 1% of OpenVPN’s and IPsec’s.

## Endpoint

`Endpoint` is used by the WireGuard configuration file to specify which server it is connecting to. Normally, the endpoint will be automatically set to the one used by your VPN provider. To achieve the goal of accelerating your VPN connection, this guide will instruct you to use an endpoint provided by us.

No matter what endpoint you are using, your data can only be decrypted by your VPN provider. The endpoint given in this guide will only be used to route your WireGuard-encrypted traffic through better network paths.

Encryption algorithms used by modern VPN protocols such as OpenVPN or WireGuard can't be cracked easily, even by using supercomputers that big companies have nowadays. This means you can safely assume that your data is safe when routed through our endpoint.

# Privacy

According to the last explanation from the [Endpoint](https://github.com/galpt/kissvpn#endpoint) section, your privacy will also be guaranteed as long as you trust your VPN provider.

* * *

# Supported VPN Providers

Until now, this guide has been tested only with a very limited number of VPN providers. This may change as the time goes and more people are contributing to improve this guide.

## Cloudflare 1.1.1.1

The [1.1.1.1](https://1.1.1.1/) VPN (a.k.a. WARP) is a service provided by Cloudflare that is by far the best you could get compared to other providers listed here. We measured the quality of the VPN by testing the speed for download/upload, browsing, streaming, and gaming activity.

### Requirements

Before continuing to the next step, you will need to download and/or install these programs:

- [WireGuard](https://www.wireguard.com/)
- [WGCF](https://github.com/ViRb3/wgcf)

### Preparations

- Download and install **WireGuard** client from the official website.
- Make a new folder and name it anything you'd like (e.g. `wgcf`).
- Download the latest **WGCF** from the repository's [Releases](https://github.com/ViRb3/wgcf/releases) to the `wgcf` folder, and extract it.

### How to Use

- Rename the `.exe` file to `wgcf.exe` to make it easier to use.
- Open a new Command Prompt terminal in that folder, and type:
```bash
wgcf.exe register
```
- After the `wgcf-account.toml` file has been generated, use the following command:
```bash
wgcf.exe generate
```
- Then, import the `wgcf-profile.conf` to your **WireGuard** client.
- Change the `DNS` and `Endpoint` as follows:
```yaml
[Interface]
...
DNS = 45.135.228.52

[Peer]
...
Endpoint = sg-r.0ms.dev:443
```
- Click `Save` to save the new edited config, and then click the `Active` button to connect to the server.

### Supported Regions

As of now, we only support acceleration for a limited number of regions.

1. Use `Endpoint = sg-r.0ms.dev:443` for Singapore.
2. Use `Endpoint = sg-r.0ms.dev:500` for Japan.
2. Use `Endpoint = sg-r.0ms.dev:501` for Germany.

> :information_source: **NOTES**
> 1. (Optional) If you already have a WARP+ license and want to use it, follow the instruction [here](https://github.com/ViRb3/wgcf#change-license-key).
> 2. Custom regions are possible only and if only people make requests for them, and we receive enough financial supports.
>    1. You can send your request to ask@0ms.dev and describe why you need it.
>    2. A request won't be processed if there aren't enough demands for it.
>    3. A request won't be processed if there aren't enough financial supports for it. See the [Donation](https://github.com/galpt/kissvpn#donation) section for the details.

## Mullvad VPN (Tested, No Guarantee to Always Work)

The [Mullvad](https://mullvad.net/en) VPN is another great alternative you could use after WARP.

From privacy perspective, Mullvad might give you more privacy compared to Cloudflare, and according to some sources (e.g. Reddit, etc.) you could use it for torrenting activity without worrying about your privacy — that is if you are into torrenting.

From performance perspective, Mullvad might be less performant than WARP since they have a small number of servers compared to Cloudflare, and their user base have to share the same servers and the same IP addresses. When their servers are getting too crowded, you might notice a performance degradation.

### How to Use

- Import the `.conf` file to your **WireGuard** client.
- Change the `DNS` and `Endpoint` as follows:
```yaml
[Interface]
...
DNS = 45.135.228.52

[Peer]
...
Endpoint = sg-r.0ms.dev:444
```
- Click `Save` to save the new edited config, and then click the `Active` button to connect to the server.

## Proton VPN (Tested, No Guarantee to Always Work)

The [Proton](https://protonvpn.com/) VPN is another great alternative you could use other than WARP and Mullvad.

From privacy perspective, Proton might give you more privacy compared to Cloudflare or even Mullvad since they are a Swiss-based company — which will guarantee your privacy even more. This means you could use it for torrenting activity without worrying about your privacy compared to when using Mullvad or Cloudflare.

From performance perspective, they have more servers compared to Mullvad, but lesser compared to Cloudflare, and for Asia users — we are limited to Japan-only servers if we are not getting their Premium plan.

When these servers are getting too crowded, a performance degradation is something you couldn't avoid.

### How to Use

- Import the `.conf` file to your **WireGuard** client.
- Change the `DNS` and `Endpoint` as follows:
```yaml
[Interface]
# Key for <your@email.com>
# Bouncing = 1
# NAT-PMP (Port Forwarding) = on
# VPN Accelerator = on
...
DNS = 45.135.228.52

[Peer]
# JP-FREE#117005
...
Endpoint = sg-r.0ms.dev:445
```
- Click `Save` to save the new edited config, and then click the `Active` button to connect to the server.

* * *

# Contributing

There are some ways you could contribute to this project, which are:

## Translation

You could help us improving this guide by translating it to your native language (a.k.a. *"mother tongue"*) so that more people from different part of the world could understand it.

## Donation

It costs us quite a lot to maintain all of our servers, and we use some of them for the purpose of writing this guide.
Until now, this guide works best for APAC users, especially Southeast Asia.

Donations make it possible to support more regions, especially the ones in Europe and the US. Donation of any amount will be greatly appreciated!

## Other

You could help us improving this guide by testing the implementation when you are playing online games, browsing, and more, and creating new [Issues](https://github.com/galpt/kissvpn/issues) to report your self-tests, and also other problems related to the implementation.

* * *

# Credits

Although we are writing this guide to let people know about our implementation, it was made possible by using other things provided by the developers and/or companies mentioned in this guide.

All credits and copyrights go to the respective owners.

* * *

# References

1. [Virtual private network](https://en.wikipedia.org/wiki/Virtual_private_network)
2. [History of VPNs](https://www.techtarget.com/searchnetworking/definition/virtual-private-network#:~:text=VPN%20technology%20was%20first%20used,with%20and%20used%20by%20businesses.)
3. [AES Explained (Advanced Encryption Standard) - Computerphile](https://youtu.be/O4xNJsjtN6E)
4. [VPN & Remote Working - Computerphile](https://youtu.be/1mtSNVdC7tM)
5. [Breaking RSA - Computerphile](https://youtu.be/-ShwJqAalOk)
6. [VPN (Virtual Private Network) Explained](https://youtu.be/R-JUOpCgTZc)
7. [7 Cryptography Concepts EVERY Developer Should Know](https://youtu.be/NuyzuNBFWxQ)
8. [8 Factors that Affect the VPN Speed: What Causes VPN to be Slow?](https://www.zenarmor.com/docs/network-security-tutorials/what-causes-vpn-to-be-slow)
9. [What is a content delivery network (CDN)? | How do CDNs work?](https://www.cloudflare.com/learning/cdn/what-is-a-cdn/)
9. [Argo Smart Routing](https://www.cloudflare.com/application-services/products/argo-smart-routing/)
10. [Cloudflare Spectrum](https://www.cloudflare.com/application-services/products/cloudflare-spectrum/)
