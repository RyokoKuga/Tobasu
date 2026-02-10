# Tobasu <img src="https://raw.githubusercontent.com/FortAwesome/Font-Awesome/6.x/svgs/solid/paper-plane.svg" width="32" height="32" style="vertical-align: middle;">

Tobasu is a minimal, elegant content-sharing tool. It allows you to **"throw" (jp: Tobasu)** URLs from one device to another instantly, as long as they are on the same Wi-Fi network.  

- **Receiver**: [https://ryokokuga.github.io/Tobasu/](https://ryokokuga.github.io/Tobasu/)
- **Sender**: [https://ryokokuga.github.io/Tobasu/send.html](https://ryokokuga.github.io/Tobasu/send.html)

> [!CAUTION]
> **Demo Version Disclaimer**
> The URLs provided at the top of this page are for **demo purposes** and utilize the **PeerJS free public server**. 
> - **Stability**: Since this is a shared public resource, connection speeds may vary, and service may be unstable during peak traffic.
> - **Privacy & Production Use**: For users who require higher security, privacy, or reliability for daily use, it is strongly recommended to **host your own PeerJS Server** rather than relying on the demo environment.

## ■ Features

- **Seamless Transfer**: Instantly send URLs to other devices without manual configuration.
- **Peer-to-Peer (P2P)**: Powered by PeerJS for direct device-to-device communication.
- **Auto-Detection**: Automatically detects the receiver on your network. No IP typing required.
- **Network Bound**: Designed to work exclusively between devices sharing the same public IP.

## ■ Components

The project consists of two simple interfaces:
- **Receiver**: A standby interface that prompts an approval dialog upon receiving content.
- **Sender**: A streamlined transmitter that auto-detects the active receiver on the same network.

## ■ Quick Start

### 1. Host the Files
Deploy the HTML files to any static hosting service or run them on a local server.

### 2. Launch Receiver
Open the **Receiver** on the target device (e.g., PC, Tablet, or TV).
- Status will show "● Ready on the same Wi-Fi".

### 3. Launch Sender
Open the **Sender** on your source device (e.g., Smartphone).
- Enter the URL you wish to share.
- Tap **"Send Content"**.

### 4. Approve and Open
An alert will appear on the Receiver. Click **"Open"** to navigate to the shared link.

## ■ Power User Tip: The "Tobasu!" Bookmarklet

For the most efficient experience, use the Bookmarklet to send the page you are currently viewing without any manual copying.

### Installation
1. Create a new bookmark in your browser's bookmark bar.
2. Set the Name to `Tobasu!`.
3. Paste the following code into the **URL** (or Location) field:

```javascript
javascript:(function(){
    const SENDER_PAGE_URL = "https://ryokokuga.github.io/Tobasu/send.html"; 
    const currentUrl = window.location.href;
    const finalUrl = SENDER_PAGE_URL + "?url=" + encodeURIComponent(currentUrl);
    window.open(finalUrl, '_blank');
})();
```

## ■ Tech Stack

- **Frontend**: HTML5, CSS3 (Custom Variables, Flexbox, Keyframes)
- **P2P Networking**: [PeerJS](https://peerjs.com/)
- Signaling Server:
  - Demo: PeerJS Public Cloud (0.peerjs.com)
  - Production: Self-hosted instance recommended.
- **Utility**: [ipify API](https://www.ipify.org/)

## ■ Usage Note
> **Note**: Both devices must be connected to the same Wi-Fi network (sharing the same public IP address) for the automatic discovery to function correctly.
