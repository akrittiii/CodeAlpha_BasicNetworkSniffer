## Activate the Vitual environment First
    env\Scripts\activate

## 
![alt text](<Flow Chart.jpg>)

##
![alt text](<program run.png>)

## Code Explanation

1. Imports and Setup
    •    Modules imported:
    •    logging: Suppresses unnecessary Scapy messages.
    •    datetime: Records timestamps for packets.
    •    subprocess: Executes system commands (e.g., setting promiscuous mode).
    •    scapy.all: Provides packet sniffing functionality.
    •    Error Handling: Ensures the Scapy library is installed; exits if missing.

2. Initial Setup
    •    Prompts the user to:
    •    Select a network interface.
    •    Choose the number of packets, sniffing duration, and a protocol filter.
    •    Specify the name of a log file to save captured data.
    •    Promiscuous Mode:
    •    Activates promiscuous mode on the selected interface to capture all traffic, not just the packets meant for the system.
    •    Error Handling: Prints an error if the operation fails.

3. Packet Logging Function
    •    packet_log(packet): Logs packet details (source MAC, destination MAC, protocol) along with a timestamp into the specified file.
    •    Supports all protocols (proto_sniff = 0) or specific ones (arp, bootp, icmp).

4. Packet Sniffing
    •    Uses Scapy’s sniff() function:
    •    Captures packets based on user-defined criteria:
    •    Interface: Specified interface (e.g., enp0s8).
    •    Count: Number of packets to capture (0 = infinite).
    •    Timeout: Duration in seconds.
    •    Filter: Specific protocols (ARP, BOOTP, ICMP).
    •    Calls the packet_log() function for each captured packet.

5. Final Steps
    •    Logs captured data to the file.
    •    Prints the file name for user reference.
    •    Closes the log file gracefully.
