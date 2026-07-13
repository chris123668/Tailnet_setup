# Tailnet Setup

## Overview

Tailscale is a zero-config VPN service built on the WireGuard protocol. It creates a private, encrypted mesh network that connects all your devices—laptops, phones, servers, and home media hubs—as if they were sitting on the same physical desk, without requiring you to open complex router ports or configure firewall rules

## Goals

The goal of this project is to allow a private and safe way to reach my homelab from outside my local network

I'll be installing tailscale on my Iphone and my Docker Nextcloud container, so I can access my private cloud outside my network. You can repeat these steps for any set of devices for exmaple your laptop and a proxmox cluster.

## Technologies

- Proxmox
- Ubuntu
- Docker
- tailnet
- Bash


## Installation

  - Step 1. go to the Tailscale download website <https://tailscale.com/download>, copy and paste the command into the container terminal.
  ![Alt Text]().
  - Step 2. Wait for Tailscale to download, then type tailscale up It will display a login URL. I'm going to check if tailscale is up and running with tailscale status 
  - Step 3.Open the URL in your browser and authenticate. 
  ![Alt Text]() 
  I'll be signing in with my GitHub account but It doesn't matter which one you pick(but be mindful witch ever login method you choose, you will have to do the same on every device)
  - Step 4. Now head to your app store and download the Tailscale app on your phone. Once it's install login and now you should have 2 devices on your tailnet![Admin page]()
  - Step 5. Now that our Tailnet is up and running, we should be able to access the service from our phone without having to be on local wifi. if your advertising a service that is open on a certain port make sure to add the port number on the end of the Tailscale MagicDNS (ex 100.80.64.60:8080).
  

## Configuration

Nextcloud is different because if you want to access your Nextcloud from a different domain, you have to change the trusted domain in the config.php file. So if you're deciding to add your Nextcloud to your tailnet, make sure to add the tailnet magicdns to the trusted domain sections. 

## Challenges

Some problems I encountered were trying to actually access my services from my iPhone when I was not on my local network. Because of the fact that my Nextcloud is running on my proxmox cluster I made the mistake of advertising my subnet route on my actually proxmox machine instead of on the LXC container. You should not enable subnet routing in a way that changes how Proxmox cluster traffic is routed. Corosync is very sensitive to network changes, latency, and interface selection. I spent a couple of hours trying to understand what was the problem on why my cluster was not acting right.



