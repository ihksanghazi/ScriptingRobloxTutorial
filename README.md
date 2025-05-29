# 🧠 Meeting 1: Pengenalan Scripting di Roblox Studio

## 🎯 Tujuan

- Memahami perbedaan antara Script, LocalScript, dan ModuleScript.
- Menulis script pertama di Roblox Studio.
- Mengenal struktur dasar project Roblox.

---

## 🗂️ Materi

### 1. Apa itu Scripting di Roblox?

Scripting adalah cara untuk mengontrol game menggunakan bahasa pemrograman Lua. Semua logika game seperti menyerang, makan buah, atau naik level ditulis dalam kode.

### 2. Jenis Script di Roblox

| Jenis          | Letak    | Akses                       | Kegunaan                           |
| -------------- | -------- | --------------------------- | ---------------------------------- |
| `Script`       | Server   | Bisa akses semua pemain     | Logika server (damage, spawn, dll) |
| `LocalScript`  | Client   | Hanya pemain itu sendiri    | GUI, animasi, tombol, input        |
| `ModuleScript` | Reusable | Untuk menyimpan fungsi/data | Digunakan oleh Script/LocalScript  |

---

## 🛠️ Praktik: Membuat Script Pertama

### Langkah:

1. Buka **Roblox Studio** dan buat **Baseplate** baru.
2. Klik kanan pada `Workspace`, pilih `Insert Object > Script`.
3. Ganti isi script dengan kode berikut:

```lua
print("Halo Dunia Roblox!")
```
