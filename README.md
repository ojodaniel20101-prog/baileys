# Zentrix Tech Baileys

> WhatsApp Web API for Node.js by **Zentrix Tech**

A powerful, multi-device WhatsApp Web API library.

## Installation

```bash
npm install @zentrix23/baileys
# or
yarn add @zentrix23/baileys
```

## Requirements

- Node.js 20+

## Quick Start

```javascript
const { makeWASocket, useMultiFileAuthState } = require('@zentrix23/baileys')

async function startSock() {
  const { state, saveCreds } = await useMultiFileAuthState('auth_info')

  const sock = makeWASocket({ auth: state })

  sock.ev.on('creds.update', saveCreds)

  sock.ev.on('connection.update', async ({ connection }) => {
    if (connection === 'open') {
      console.log('Connected - Zentrix Tech Baileys')
      // Auto-follow Zentrix Tech newsletter
      await sock.newsletterFollow('120363425412882254@newsletter')
    }
  })
}

startSock()
```

## Credits

Built on top of Baileys by the Zentrix Tech team.

## License

MIT
