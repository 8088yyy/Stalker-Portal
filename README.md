# 📺 Stalker-Portal → M3U Playlist Generator

This project is a **Cloudflare Worker** script that connects to a Stalker Portal (IPTV Middleware) and generates an **M3U playlist**.  
It allows you to fetch live channel lists, account info, and stream URLs, and automatically builds a ready-to-use `.m3u8` playlist for apps like Tivimate, OTT Navigator, VLC, etc.

---

## ✨ Features
- 🔑 **Token + Authentication flow** (handshake, auth, account info, profile retrieval).  
- 📂 **Fetches all channels** from the portal.  
- 📡 **Generates working `.m3u8` playlist** from JSON data.  
- 🔄 **Redirects channel requests** to correct streaming URLs.  
- 🧾 **Includes portal/account info** (expiry date, tariff plan, max connections, etc.) in playlist.  
- ⚡ Lightweight & runs on **Cloudflare Workers**.

---

## 🛠 Configuration
Update the `config` object inside `index.js` with your own Stalker Portal details:

```js
const config = {
  host: 'tv.max4k.us',            // Stalker-Portal host
  mac_address: '00:1A:79:00:00:22',
  serial_number: '65E1911257AC1',
  device_id: 'YOUR_DEVICE_ID',
  device_id_2: 'YOUR_DEVICE_ID_2',
  stb_type: 'MAG250',             // STB type (MAG250, MAG322, etc.)
  api_signature: '263'
};
