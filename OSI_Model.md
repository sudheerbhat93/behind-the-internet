In this document, I've shared my understanding of the OSI Model. You'll find answers to what, why, and how of the OSI Model based on my learning journey.


❓ What is the OSI Model?
The OSI Model (Open Systems Interconnection) is a conceptual framework that describes how data moves through a network. 
It defines a set of protocols and rules that allow different computers and systems to communicate effectively over a network.


✅ Why is the OSI Model Important?
🧠 Simplifies the understanding of complex network operations.
🧱 Divides networking into 7 layers, making it easier for devices and systems to work together.
🔧 Helps in troubleshooting and managing network issues by breaking them down layer-by-layer.


⚙️ How Does the OSI Model Work?
The OSI Model is made up of 7 layers, each with a specific function:
7. Application Layer
6. Presentation Layer
5. Session Layer
4. Transport Layer
3. Network Layer
2. Data Link Layer
1. Physical Layer


Let's go through each one 👇

📱 Layer 7 - Application Layer
Closest to the end user.
The layer where requests start, like web browsing, sending emails, or file transfers.
Protocols: HTTP/HTTPS, FTP, SMTP, etc.


🖼️ Layer 6 - Presentation Layer
Data Translation: Converts user-readable data (text, images, etc.) into machine-readable binary.
Compression: Reduces data size for faster transfer.
Encryption: Protects data integrity and confidentiality (e.g., using SSL/TLS).


🧩 Layer 5 - Session Layer
Manages sessions or connections between two systems.
Responsible for:
Establishing the connection
Maintaining communication
Terminating the session when done
Protocols: NetBIOS, PPTP, etc.


🚚 Layer 4 - Transport Layer
Segmentation: Splits data into segments, adds port numbers & sequence info.
Flow Control: Regulates how much data can be sent (10 Mbps vs 1000 Mbps).
Error Control: If some data does not arrive at the destination, transport layer uses Automatic Repeat Request to send the missing data. 
Protocols: TCP, UDP


🗺️ Layer 3 - Network Layer
Adds logical addressing (IP addresses) to each segment to form packets.
Routing: Determines how data should be sent from source to destination.
Path Determination: Chooses the best route using routing protocols.
Protocols: IP, ICMP, OSPF, BGP


🧷 Layer 2 - Data Link Layer
Adds MAC addresses (physical addresses) to packets, forming frames.
Responsible for:
LLC (Logical Link Control): Error detection & flow control between adjacent nodes.
MAC (Media Access Control): Determines which device gets to send data when multiple devices share a medium.
Devices: Switches, Bridges


⚡ Layer 1 - Physical Layer
The actual hardware layer: transmits raw bits (0s and 1s) over physical media.
Includes cables, switches, hubs, radio signals, and fiber optics.



🎥 Reference Videos
These are the resources I referred to during my learning:
OSI Model Explained: TechTerms
OSI Model Simplified: Abhishek Veeramalla

