# Intro
- many ways to transfer a file between 2 hosts on the same network
- SMB: Server Message Block
  - Provides shared access to files, printers, and serial ports between endpoints on a network
  - Mostly on Windows machine
  - 445/TCP open on the target reserved for the SMB protocol
  - Runs at the application or presentation layers of the OSI model
  - Relies on lower-level protocols for transport
  - Relies on lower-level protocols for transport
  - Transport layer protocol that SMB uses is with NetBIOS over TCP/IP (NBT)
  - Most likeley will see both protocols with open ports running on the target
- SMB protocol
  - application can access files at a remote server along with other resources such as printers
  - client can read, create, and update files on the remote server
  - Can communicate with any server program that is set up to receive an SMB client request
  - needs auth mechanism
  - SMB clients are required to provide a username/password combo to interact with contents of the SMB share
- sometimes admins can accidentaly allow logins without any valid credentials
  - using guest accounts or anonymous log-ons
- Can use smbclient to connect to remote host
- smbclient -L {ip address}
  - lists different types of shares
  - Then can use
    - smbclient \\\\{ip address}\\{share name}
    - to try an connect to different ones
    - can try no password
    - worked for one due to misconfiguration
