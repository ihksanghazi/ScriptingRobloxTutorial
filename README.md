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

4. Jalankan game atau tekan tombol (`F5`).
5. Lihat hasilnya di **Output Window** (`View > Output`).

---

## 🧪 Eksperimen: Mengubah Warna Part Lewat Script

### Langkah:

1. Tambahkan **Part** di Workspace.
2. Klik kanan pada Part → `Insert Object > Script`.
3. Ganti isi script dengan kode berikut:

```lua
script.Parent.BrickColor = BrickColor.Random()
```

---

## 💡 Catatan

- Semua script yang ada di dalam `Workspace` atau `ServerScriptService` akan berjalan sebagai **Script server**.
- Jika kamu butuh interaksi dari pemain (seperti menekan tombol), gunakan `LocalScript` nanti.

---

## 🧠 Latihan Mandiri

1. Buat script yang mengubah ukuran part jadi lebih besar.
2. Buat 3 part berbeda dan setiap part punya script yang mengganti warnanya secara acak saat game dimulai.

---

## ✅ Evaluasi

- Apakah kamu bisa membuat dan menjalankan Script?
- Apakah kamu paham kapan harus menggunakan Script vs LocalScript?

Jika sudah, lanjut ke Meeting 2: Membuat script pertama: cetak teks, manipulasi part.

➡️ Lanjut ke [Pertemuan 2 - Membuat script pertama: cetak teks, manipulasi part](https://github.com/ihksanghazi/ScriptingRobloxTutorial/tree/Pertemuan_2)
