# 🧪 Meeting 2: Membuat Script Pertama di Roblox Studio

## 🎯 Tujuan

- Menulis **kode pertama** di Roblox Studio.
- Mengenal **fungsi `print()`**.
- Belajar cara **mengubah warna dan ukuran Part** dengan script.

---

## 🎮 Yuk Mulai!

### 1. Buka Roblox Studio

1. Klik `New Project` > pilih **Baseplate**.
2. Sekarang kamu berada di dunia kosong, tapi siap untuk diberi “nyawa” lewat kode!

---

## ✍️ Bagian A: Cetak Teks dengan `print()`

### Apa itu `print()`?

`print()` adalah perintah untuk **menampilkan tulisan di jendela Output**, supaya kita tahu kode kita jalan atau tidak.

### Langkah-langkah:

1. Klik kanan `Workspace` → pilih `Insert Object` → pilih `Script`.
2. Di dalam Script, ganti kodenya jadi:

```lua
print("Halo, dunia Roblox!")
```

3. Tekan tombol **Play** (F5).
4. Klik menu `View` → pilih `Output`.
5. Lihat deh! Ada tulisan `"Halo, dunia Roblox!"` muncul 🎉

---

## 🟥 Bagian B: Ubah Warna Part dengan Script

### Langkah-langkah:

1. Tambahkan 1 **Part** ke Workspace (klik kanan → Insert Object → Part).
2. Klik kanan pada Part itu → pilih `Insert Object` → `Script`.
3. Ganti isi script-nya jadi:

```lua
script.Parent.BrickColor = BrickColor.Random()
```

4. Jalankan game (F5), dan lihat warna part akan berubah secara acak 🌈

---

## 📏 Bagian C: Ubah Ukuran Part dengan Script

### Langkah-langkah:

1. Tambahkan 1 **Part** ke Workspace (klik kanan → Insert Object → Part).
2. Klik kanan pada Part itu → pilih `Insert Object` → `Script`.
3. Ganti isi script-nya jadi:

```lua
script.Parent.Size = Vector3.new(10, 5, 10)
```

Artinya:

- Lebar = 10
- Tinggi = 5
- Panjang = 10

Sekarang Part kamu akan jadi lebih besar 💪

---

## 🧠 Latihan Mandiri

Coba lakukan hal-hal ini:

1. Buat 3 Part dengan warna berbeda menggunakan `BrickColor.Random()`.
2. Buat Part yang berubah ukuran dan warna saat game dimulai.
3. Tambahkan tulisan di Output seperti `"Part sudah berubah!"` setelah mengubah ukurannya.

Contoh:

```lua
script.Parent.Size = Vector3.new(8, 8, 8)
script.Parent.BrickColor = BrickColor.Red()
print("Part sudah berubah!")
```

---

## ✅ Siap Lanjut?

Kamu sudah bisa:

- Menulis script pertama
- Mencetak teks
- Mengubah warna dan ukuran part

Keren! 🎉

➡️ Lanjut ke [Pertemuan 3 - Variabel, fungsi, dan event dasar di Lua](https://github.com/ihksanghazi/ScriptingRobloxTutorial/tree/Pertemuan_3)
