# 🚀 PPOB Addon Installer

> **One-command installer for PPOB Addon Production**

[![npm version](https://badge.fury.io/js/create-ppob-addon.svg)](https://www.npmjs.com/package/create-ppob-addon)
[![Downloads](https://img.shields.io/npm/dt/create-ppob-addon.svg)](https://www.npmjs.com/package/create-ppob-addon)

---

## 📋 Prerequisites (Wajib!)

**Sebelum install, pastikan ini sudah terpasang:**

### 1. Node.js v24.11.1
```bash
node --version
# Harus: v24.11.1
```
📥 Download: [https://nodejs.org/dist/v24.11.1/](https://nodejs.org/dist/v24.11.1/)

### 2. Redis / Memurai (Recommended)
**Windows:**
```bash
# Install Memurai (Redis untuk Windows)
# Download: https://www.memurai.com/get-memurai
```
**Linux/Mac:**
```bash
sudo apt-get install redis-server  # Ubuntu/Debian
brew install redis                   # Mac
```
**Alternatif (Docker):**
```bash
docker run -d --name redis -p 6379:6379 redis
```

---

## 🚀 Cara Install (Cuma 1 Command!)

```bash
npx create-ppob-addon
```

Atau kalo mau pake server custom:
```bash
npx create-ppob-addon --server=https://server-anda.com
```

---

## 📦 Yang Akan Terjadi:

Installer otomatis akan:
1. ✅ Cek Node.js, PM2, Redis
2. ✅ Generate file `.env` dan `ecosystem.config.js`
3. ✅ Download latest version
4. ✅ Extract dan setup symlink

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

## 🛠️ Setelah Install

Masuk ke folder hasil install, lalu:

```bash
# Start aplikasi
npm run pm2:start

# Cek status
npm run pm2:status

# Lihat logs
npm run pm2:logs

# Restart
npm run pm2:restart
```

---

## 🔧 Troubleshooting

### ❌ Node.js version mismatch
**Solusi:** Download versi yang tepat:
```bash
# Windows: Download installer dari website
# Mac: brew install node@24
# Linux: nvm install v24.11.1
```

### ❌ Redis not found
**Solusi:** Install Redis atau Memurai, atau pake Docker:
```bash
docker run -d --name redis -p 6379:6379 redis
```

### ❌ Permission denied (Linux/Mac)
**Solusi:** Tambah `sudo` atau atur permission:
```bash
sudo chmod -R 755 ./folder_installasi
```

---

## 📁 Struktur Folder Setelah Install

```
folder_installasi/
├── current/              # ✅ Symlink ke versi terbaru
├── releases/             # 📦 Semua versi yang pernah diinstall
│   └── ppob_addon-4.3.0/
├── .env                  # ⚙️ Konfigurasi (edit sesuai kebutuhan)
├── ecosystem.config.js   # 🔄 PM2 config
├── keys/
│   └── public.key        # 🔑 Public key
└── logs/                 # 📝 Log file
```

---

## 🔄 Cara Update

Update ke versi terbaru? Jalankan lagi:
```bash
npx create-ppob-addon
```

Atau pake `--version` untuk versi tertentu:
```bash
npx create-ppob-addon --version=4.4.0
```

---

## 💡 Tips

- **Edit `.env`** setelah install untuk custom port, Redis, dll
- **PM2 will auto-restart** jika app crash
- **Logs** ada di `./logs/` folder
- **Zero-downtime** update dengan symlink

---

## 📞 Support

- **Email**: ndiing.inc@gmail.com
- **GitHub**: [https://github.com/ndiing/create-ppob-addon](https://github.com/ndiing/create-ppob-addon)

---

**Made with ❤️ by ndiing**