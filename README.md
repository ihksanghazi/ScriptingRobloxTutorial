# 🧠 Meeting 4: Memahami Script, LocalScript, dan ModuleScript

## 🎯 Tujuan

- Mengetahui perbedaan antara **Script**, **LocalScript**, dan **ModuleScript**.
- Belajar kapan harus memakai masing-masing jenis script.
- Mencoba contoh sederhana dari masing-masing script.

---

## 🧾 Kenalan Dulu Yuk!

| Jenis Script     | Jalan di         | Untuk Apa?                                                                         |
| ---------------- | ---------------- | ---------------------------------------------------------------------------------- |
| **Script**       | Server           | Untuk hal-hal yang semua pemain bisa lihat (misal: spawn musuh, kasih damage, dll) |
| **LocalScript**  | Client (Player)  | Untuk hal pribadi pemain seperti tombol, GUI, kamera                               |
| **ModuleScript** | Reusable (Semua) | Untuk menyimpan fungsi yang bisa dipakai berulang-ulang                            |

---

## 🛠️ Contoh A: Script (Server Side)

### Langkah:

1. Tambahkan **Part** ke Workspace.
2. Tambahkan `Script` ke dalam Part.
3. Tulis kode ini:

```lua
print("Halo dari Script Server!")
```

🧠 Script ini akan jalan untuk semua pemain.

---

## 🧰 Contoh B: LocalScript (Client Side)

### Langkah:

1. Tambahkan `StarterPlayer > StarterPlayerScripts`.
2. Klik kanan → `Insert Object > LocalScript`.
3. Tulis kode ini:

```lua
print("Halo dari LocalScript!")
```

🧠 LocalScript hanya akan jalan untuk pemain yang sedang main. Misalnya, kita bisa pakai untuk:

- Buka GUI
- Kontrol tombol keyboard
- Efek kamera

---

## 🔁 Contoh C: ModuleScript (Untuk Disimpan dan Dipanggil)

### Langkah:

1. Klik `ReplicatedStorage` → `Insert Object > ModuleScript`.
2. Ganti nama jadi `MathHelper`.
3. Isi kodenya:

```lua
local MathHelper = {}

function MathHelper.Tambah(a, b)
	return a + b
end

return MathHelper
```

4. Sekarang, dari Script atau LocalScript lain, kamu bisa panggil:

```lua
local mathLib = require(game.ReplicatedStorage.MathHelper)
print(mathLib.Tambah(5, 3))  -- Hasil: 8
```

🧠 ModuleScript seperti kotak alat berisi fungsi-fungsi yang bisa dipakai di mana saja.

---

## 🎯 Kapan Harus Pakai yang Mana?

| Mau ngapain?                       | Pakai apa?   |
| ---------------------------------- | ------------ |
| Kasih damage ke musuh              | Script       |
| Menampilkan tombol di layar        | LocalScript  |
| Simpan fungsi-fungsi hitung damage | ModuleScript |
| Membuat GUI khusus pemain          | LocalScript  |
| Munculkan musuh untuk semua pemain | Script       |

---

## 🧠 Latihan Mandiri

1. Buat LocalScript yang mencetak `“Halo dari LocalScript!”` saat game dimulai.
2. Buat ModuleScript bernama `Perkenalan` yang punya fungsi `sapa(nama)` dan cetak `"Halo, <nama>"`.
3. Buat Script yang memanggil fungsi dari ModuleScript `Perkenalan`.

---

## 🧪 Tantangan Bonus

Coba buat:

- ModuleScript dengan fungsi `serangan(seranganName)`, lalu dari Script panggil `serangan("Tendangan Api")`.
- LocalScript yang menampilkan GUI saat tombol ditekan (nanti kita pelajari lebih dalam ya!).

---

## Kamu Sudah Paham...

- Perbedaan Script, LocalScript, dan ModuleScript
- Cara pakainya
- Contoh sederhana masing-masing

Hebat banget! Sekarang kamu sudah tahu struktur penting dalam scripting Roblox 💻🧠

➡️ Lanjut ke [Pertemuan 5 - RemoteEvent: komunikasi Client-Server dasar](https://github.com/ihksanghazi/ScriptingRobloxTutorial/tree/Pertemuan_5)
