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

  - Step 1. go to the tailscale download website <https://tailscale.com/download>, copy and paste the command into the container terminal.
  ![Alt Text]().
  - Step 2. wait for the tailscale to download, Then type tailscale up It will display a login URL. I'm going to check if tailscale is up and running with tailscale status 
  - Step 3.Open the URL in your browser and authenticate. 
  ![Alt Text]() 
  I'll be signing in wiht my github account but It doesn't matter which one you pick(but mindful witch ever login method you choose you will have to do the same on every device)
  - Step 4. Now head to your app store and download the tailscale app on your phone. Once it's install login and now you should have 2 device on your tailnet ![Admin page]()
  - Step 5. Now that our tailnet is up and running we should be able to access the service you advertised. if your advertising a service that is open on a certain port make sure to add the port number on the end of the tailscale magicdns (ex 100.80.64.60:8080).
  

## Configuration

Important settings

## Challenges

Problems encountered

## Lessons Learned

What you learned

