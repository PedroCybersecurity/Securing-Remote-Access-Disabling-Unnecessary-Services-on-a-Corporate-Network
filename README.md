### Title:
**Securing Remote Access: Disabling Unnecessary Services on a Corporate Network**

### Description:
This project documents a comprehensive approach to enhancing network security by identifying and disabling unnecessary remote access services on a corporate network. Using Zenmap for network scanning and the Windows Services management tool, we focus on closing potential security vulnerabilities associated with open ports for Remote Desktop Services (port 3389) and VNC Server (port 5900). This guide serves as a detailed walkthrough for cybersecurity analysts tasked with auditing and securing network endpoints.

### README.md Content:

```markdown
# Securing Remote Access: Disabling Unnecessary Services on a Corporate Network

## Introduction
In the realm of network security, identifying and disabling unnecessary services is crucial to protect against unauthorized access and potential breaches. This project outlines a methodical approach to secure a corporate network by focusing on two commonly exploited remote access services: Remote Desktop Services and VNC Server. Through network scanning with Zenmap and service management on Windows, we aim to minimize the attack surface of our network.

## Objective
Our primary goal is to detect and disable Remote Desktop Services (port 3389) and VNC Server (port 5900) on networked machines that do not require these services for their daily operations. This practice helps in reducing the risk of remote exploits and ensuring that only essential services are operational, adhering to the principle of least privilege.

## Tools and Technologies
- **Zenmap**: A graphical interface for the Nmap Security Scanner, used for network exploration and auditing.
- **Windows Services Management Tool**: A component of Microsoft Windows allowing the starting, stopping, and configuring of services.

## Process Overview

### Scanning the Network with Zenmap

1. **Initiate Zenmap**:
   - Launch Zenmap from the Favorites bar and maximize the window for better visibility.

2. **Conducting Port Scans**:
   - To find machines with Remote Desktop Services running, input the command:
     ```
     nmap -p 3389 192.168.0.0/24
     ```
   - For detecting VNC Server instances, use:
     ```
     nmap -p 5900 192.168.0.0/24
     ```
   - Execute the scans to identify open ports across the network.

### Identifying Target Machines

- Analyze Zenmap's output to pinpoint the IP addresses with ports 3389 and 5900 open.
- Reference the network's IP allocation table to match IP addresses with their corresponding computer names.

### Disabling and Stopping Services on Windows

1. **Accessing Services**:
   - Navigate to the identified machine via the network overview.
   - Use the search field on the taskbar to open the Services management console.

2. **Modifying Service Settings**:
   - Locate Remote Desktop Services or VNC Server in the services list.
   - Double-click the service to open its properties window.
   - Set the Startup Type to `Disabled` and click `Stop` to halt the service immediately.
   - Confirm changes by clicking `OK`.

## Conclusion

By systematically scanning for and disabling unnecessary remote access services, we bolster our network's defense against potential intrusions. This guide underscores the importance of regular audits and the proactive management of services to maintain a secure IT environment.

## Future Recommendations

- Regularly update and patch all systems to protect against vulnerabilities.
- Implement network segmentation to limit the spread of potential attacks.
- Consider deploying a centralized management solution for monitoring and managing services across the network.

Happy Securing!
```
