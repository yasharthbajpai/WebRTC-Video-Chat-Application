# WebRTC Video Chat Application

A real-time video chat application built with WebRTC, Express.js, and Socket.IO. This application enables peer-to-peer video communication between two users through a signaling server.

## Features

- Real-time video streaming between peers
- Secure HTTPS connection
- Signaling server for WebRTC connection establishment
- Simple authentication system
- Support for both local and remote connections

## Prerequisites

- Node.js (v14 or higher)
- npm (Node Package Manager)
- mkcert (for SSL certificate generation)

## Installation

1. Clone the repository:
```bash
git clone https://github.com/YOUR_USERNAME/webrtc-video-chat.git
cd webrtc-video-chat
```

2. Install dependencies:
```bash
npm install
```

3. Generate SSL certificates using mkcert:
```bash
mkcert create-ca
mkcert create-cert
```

This will create two files:
- `cert.key`: Private key (do not commit this file)
- `cert.crt`: SSL certificate (do not commit this file)

Note: The SSL certificates are automatically ignored by .gitignore for security reasons. Each developer needs to generate their own certificates.

## Usage

1. Start the server:
```bash
npm start
```

2. Access the application:
- Local: Open `https://localhost:8181` in your browser
- Remote: Open `https://<your-ip>:8181` in your browser (replace `<your-ip>` with your machine's IP address)

3. To test the video chat:
- Open the application in two different browsers or devices
- Each user will be assigned a random username
- Click the "Call" button on one device to initiate the call
- Accept the call on the other device

## Technical Details

### Architecture

- **Frontend**: HTML5, JavaScript (ES Modules)
- **Backend**: Express.js, Socket.IO
- **Protocol**: WebRTC for peer-to-peer communication
- **Security**: HTTPS with SSL/TLS

### Components

- `server.mjs`: Signaling server handling WebRTC connection establishment
- `scripts.mjs`: Client-side WebRTC implementation
- `index.html`: User interface

### WebRTC Configuration

The application uses Google's STUN servers for NAT traversal:
```javascript
iceServers: [
    {
        urls: [
            'stun:stun.l.google.com:19302',
            'stun:stun1.l.google.com:19302'
        ]
    }
]
```

## Security Notes

- The application uses a simple password authentication system
- All communication is encrypted using HTTPS
- WebRTC connections are peer-to-peer and encrypted

## Development

The project uses ES Modules for better code organization and modern JavaScript features. To modify the code:

1. Edit the relevant files
2. Restart the server to apply changes
3. Refresh the browser to load updated client-side code

## Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## Security Considerations

- Never commit SSL certificates or private keys
- The default password ("x") should be changed in production
- Consider implementing a more robust authentication system for production use
- Keep dependencies up to date to patch security vulnerabilities



## Author


Yasharth Bajpai
(Made with the help of StackOverFlow + GPT's)

