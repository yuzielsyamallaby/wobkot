# Wobkot — PS4 WebKit Host

Host statis dan offline untuk rantai eksploitasi WebKit **PlayStation 4**.
Tidak ada kode, payload, atau UI untuk konsol lain.

> Gunakan hanya pada konsol milik Anda sendiri, untuk homebrew/riset, dan patuhi
> hukum yang berlaku di wilayah Anda.

---

## 1. Struktur

```
wobkot/
├─ index.html              deteksi firmware PS4 + auto-start
├─ loader.html             halaman log exploit
├─ offline.html            installer cache AppCache (jalan sekali saat online)
├─ offline.manifest        daftar berkas yang dicache + nomor versi
├─ style.css
├─ .nojekyll               agar GitHub Pages tidak memproses dengan Jekyll
└─ src/
   ├─ main.js              orkestrator pemuatan modul
   ├─ misc.js              utilitas & deteksi versi
   ├─ userland.js          primitive userland
   ├─ kernel.js            tahap kernel
   ├─ lapse.js             rantai WebKit untuk firmware lama
   ├─ thread.js            jembatan main thread <-> worker
   ├─ worker.js            Web Worker
   └─ ps4/
      ├─ impl.js           implementasi spesifik PS4 + offset firmware
      └─ payload.bin       payload yang dieksekusi setelah jailbreak
---

## 4. Firmware yang didukung

| Firmware PS4 | Status |
|---|---|
| 1.00 – 11.99 | Didukung |
| 12.00 – 12.02 | Didukung |
| 12.10 ke atas | WIP — `src/ps4/impl.js` melempar `exploit is WIP` |