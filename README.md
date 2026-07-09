# 🚀 PPOB Addon - API Gateway untuk Software PPOB

> **Solusi integrasi API modern untuk software PPOB yang sudah berjalan**

[![Version](https://img.shields.io/badge/version-4.3.0-blue)](https://github.com/ndiing/ppob_addon)
[![License](https://img.shields.io/badge/license-Proprietary-red)](https://github.com/ndiing/ppob_addon)
[![Node](https://img.shields.io/badge/node-v24.11.1-green)](https://nodejs.org/)

---

## 📖 Apa Itu PPOB Addon?

**PPOB Addon** adalah **API Gateway** yang memperluas kemampuan software PPOB Anda dengan menyediakan akses ke API modern dari berbagai provider.

### 💡 **Cara Kerja:**

```
Software PPOB (OttoMax, Tiga Putri, dll)
         ↓
  [ PPOB ADDON ]
         ↓
XL SIDOMPUL | INDOSAT | TELKOMSEL | DLL
```

### 🎯 **Untuk Siapa?**

- **Pengguna** software PPOB yang ingin tambahan fitur
- **Pengusaha** yang butuh integrasi API modern
- **Developer** yang ingin extend software existing

---

## 🔥 Fitur Unggulan

| Fitur | Keterangan |
|-------|------------|
| 🔌 **API Gateway** | Integrasi ke XL SIDOMPUL, Indosat Ooredoo, Telkomsel |
| 🔐 **License System** | Per-feature licensing (WhatsApp, Telegram, dll) |
| 🔄 **Auto Update** | Zero-downtime update |
| 🛡️ **Security** | Hardware fingerprint + JWT + IP Whitelist |
| 📊 **Monitoring** | Health check + Crash report |
| 💰 **Billing** | Payment system (VA, QRIS, Manual) |
| 🔌 **RPC** | Real-time WebSocket communication |

---

## 🛠️ Kompatibilitas

PPOB Addon dirancang untuk **melengkapi** (bukan menggantikan) software PPOB yang sudah Anda gunakan:

| Software | Support | Keterangan |
|----------|---------|------------|
| **OttoMax** | ✅ | Tambahan API gateway |
| **Tiga Putri** | ✅ | Integrasi 3rd party |
| **IRS** | ✅ | Auto-update system |
| **Flash Maching** | ✅ | License management |
| **Software Lain** | ✅ | Custom integration |

---

## 📋 Prasyarat

### 1. **Node.js v24.11.1**
```bash
node --version
# Harus: v24.11.1
```
📥 Download: [https://nodejs.org/dist/v24.11.1/](https://nodejs.org/dist/v24.11.1/)

### 2. **PM2** (Auto-install)
```bash
npm install -g pm2
```

### 3. **Redis / Memurai**
**Windows:**
```bash
# Download Memurai: https://www.memurai.com/get-memurai
net start Memurai
```

**Linux/Mac:**
```bash
sudo apt-get install redis-server  # Ubuntu
brew install redis                   # Mac
```

**Atau pake Docker:**
```bash
docker run -d --name redis -p 6379:6379 redis
```

---

## 🚀 Cara Installasi

### **Hanya 1 Command!**

```bash
npx create-ppob-addon
```

Atau kalo pake server custom:
```bash
npx create-ppob-addon --server=https://server-anda.com
```

### **Apa yang Terjadi:**

```
🚀 PPOB_ADDON Installer
📡 Server URL: http://localhost:3000

🔍 Checking prerequisites...
✅ Node.js v24.11.1
✅ PM2 7.0.1
✅ Redis is running

📝 Generating configuration files...
✅ Created .env
✅ Created ecosystem.config.js

⬇️ Downloading latest version...
✅ Download complete: ppob_addon-4.3.0.zip

📦 Extracting...
✅ Extraction complete

🎉 Installation complete!
```

---

## 📂 Struktur Folder

```
ppob_addon/
├── current/              # ✅ Symlink ke versi terbaru
├── releases/             # 📦 Semua versi
├── .env                  # ⚙️ Konfigurasi
├── ecosystem.config.js   # 🔄 PM2 config
├── keys/
│   ├── license.key       # 🔑 License JWT
│   └── public.key        # 🔐 Public key
└── logs/                 # 📝 Log aplikasi
```

---

## 🛠️ Setelah Install

```bash
# Start aplikasi
npm run pm2:start

# Cek status
npm run pm2:status

# Lihat logs
npm run pm2:logs

# Restart
npm run pm2:restart

# Reload (zero downtime)
npm run pm2:reload
```

---

## 🔗 Supported Integrations

### **XL SIDOMPUL**
```http
POST /api/sidompul/topup
{
  "sessionId": "OTTOMAX-001",
  "product": "pulsa_10k",
  "phone": "08123456789"
}
```

### **Indosat Ooredoo**
```http
POST /api/indosat/topup
{
  "sessionId": "OTTOMAX-001",
  "product": "pulsa_20k",
  "phone": "08123456789"
}
```

### **Telkomsel API**
```http
POST /api/telkomsel/topup
{
  "sessionId": "OTTOMAX-001",
  "product": "pulsa_50k",
  "phone": "08123456789"
}
```

---

## 🔐 License Management

### **Cek License Status**
```http
GET /api/license/status
```

### **Response**
```json
{
  "success": true,
  "data": {
    "fingerprint": "10d7ea396dca...",
    "features": {
      "whatsapp": 1785261617,
      "telegram": 1785261617
    }
  }
}
```

---

## 🐛 Troubleshooting

### ❌ Node.js version mismatch
**Solusi:** Download Node.js v24.11.1 dari website resmi.

### ❌ Redis not found
**Solusi:** Install Redis atau pake Docker:
```bash
docker run -d --name redis -p 6379:6379 redis
```

### ❌ License expired
**Solusi:** Perpanjang license via admin.

### ❌ IP not allowed
**Solusi:** Tambah IP di `.env`:
```env
ALLOWED_IPS=127.0.0.1,192.168.1.100
```

---

## 📞 Dukungan

- **Email**: ndiing.inc@gmail.com
- **WhatsApp**: +62 812-3456-7890
- **Telegram**: @ndiing

---

## 💰 Harga

| Package | Price | Durasi |
|---------|-------|--------|
| **XL SIDOMPUL** | Rp 500.000 | /bulan |
| **Indosat Ooredoo** | Rp 500.000 | /bulan |
| **Telkomsel API** | Rp 500.000 | /bulan |
| **Bundle All** | Rp 1.200.000 | /bulan |
| **Support SLA** | Rp 200.000 | /bulan |

💳 **Custom quote** untuk enterprise.

---

## 🛡️ Keamanan

- ✅ Hardware Fingerprint - License terikat hardware
- ✅ JWT PS512 - Asymmetric encryption
- ✅ IP Whitelist - Kontrol akses
- ✅ On-Premise - Data tetap di server Anda
- ✅ Audit Log - Aktivitas tercatat

---

## 🔧 Tech Stack

| Layer | Technology |
|-------|------------|
| **Runtime** | Node.js v24.11.1 |
| **Framework** | Express.js 5 |
| **Database** | SQLite (better-sqlite3) |
| **Cache** | Redis (ioredis) |
| **Process** | PM2 Cluster |
| **Security** | JWT, Fingerprint, IP Whitelist |
| **Real-time** | WebSocket (ws) |

---

## 📄 Lisensi

**Proprietary License** - All rights reserved.

---

## 👨‍💻 Kontak

- **Email**: ndiing.inc@gmail.com
- **WhatsApp**: +62 812-3456-7890
- **Telegram**: @ndiing

---

**Made with ❤️ by [ndiing](https://github.com/ndiing)**  
*Powered by ☕ Caffeine*
