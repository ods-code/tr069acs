# TR069 ACS — Auto Configuration Server

[Turkce](README.md)

---

## About

TR069 ACS is a Windows application that allows you to remotely manage modem via the TR-069 (CWMP) protocol. You can read and write modem parameters and remotely configure devices.

TR-069 is a standard protocol used by Internet Service Providers (ISPs) to centrally manage customer modems. This application uses this protocol to let you connect to and manage modems from a single computer.

---

## What Does It Do?

The application turns your computer into an ACS (Auto Configuration Server). When you connect your modem to your computer via an Ethernet cable, the application automatically sets up the necessary network infrastructure and establishes communication with the modem.

**DHCP Server** — Automatically assigns an IP address to the modem. When the modem connects, the DHCP server activates and assigns the address 10.116.13.101 to the modem, enabling network communication between the modem and your computer.

**PPPoE Server** — Some modems need to initiate a PPPoE session to establish an internet connection. This server handles the modem's PPPoE requests and allows it to open a session.

**VLAN Mirroring** — Modems may send traffic with different VLAN tags. This feature automatically detects the VLAN tags used by the modem and mirrors them, ensuring uninterrupted communication.

**DNS Redirect** — DNS redirect intercepts all DNS requests and directs the modem to connect to your computer instead.

**TR-069 / CWMP Engine** — Once the modem establishes a connection, communication begins via the TR-069 protocol. The modem sends an Inform message to identify itself. You can then query the parameters the modem supports with GetParameterNames, read their current values with GetParameterValues, and change values with SetParameterValues.

**Real-time Monitoring** — All of these operations are tracked in real time through the web interface. You receive instant notifications when a modem connects, when parameters are queried, or when an error occurs.

---

## How Does It Work?

1. Start the application. The web interface will automatically open in your browser.

2. Select the network adapter (Ethernet port) that your modem is connected to from the left panel.

3. Enable the DHCP server. The modem will automatically receive an IP address.

4. Enable DNS redirect. When the modem tries to find the ACS server, requests will be redirected to your computer.

5. Restart your modem or trigger the ACS connection from the modem's settings. The modem will send an Inform message to your server via the TR-069 protocol.

6. You will see the connected modem on the Dashboard screen. From here, you can perform parameter reading, writing, and device management operations.

---

## Network Configuration

The application automatically creates the following network configuration:

- Computer IP address: 10.116.13.100
- Modem IP address: 10.116.13.101 (assigned via DHCP)
- Web interface: port 80
- ACS server ports: 7547, 8000, 8010, 8015

Multiple ACS ports provide flexibility for different modems connecting on different ports.

---

## System Requirements

- Windows 10 or Windows 11
- Direct Ethernet connection to the modem
- Administrator privileges (for port 80 and raw socket access)
- The installation of the npcap application is mandatory.  If the npcap application is not installed, it will not work or open.
---

Powered by **OnDiso**
https://ondiso.net
