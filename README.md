# 🧠 Meeting 3: Variabel, Fungsi, dan Event Dasar di Lua

## 🎯 Tujuan

- Mengenal **variabel**: tempat menyimpan data.
- Mengenal **fungsi**: kumpulan perintah yang bisa dipanggil.
- Mengenal **event**: kode yang aktif saat sesuatu terjadi (seperti klik atau sentuh).

---

## 🧮 Bagian A: Apa Itu Variabel?

### Bayangkan:

Variabel itu seperti **kotak** yang menyimpan sesuatu. Kita kasih nama kotaknya, lalu isi dengan nilai.

### Contoh:

```lua
local namaBuah = "Fire Fruit"
print(namaBuah)  -- akan mencetak: Fire Fruit
```

### Latihan:

1. Buat variabel `playerName` dan isi dengan namamu.
2. Cetak ke output:

```lua
local playerName = "Raka"
print("Halo, " .. playerName)
```

📝 `..` digunakan untuk menyambung teks.

---

## 🛠️ Bagian B: Apa Itu Fungsi?

Fungsi adalah **kumpulan perintah** yang bisa dijalankan kapan saja.

### Contoh:

```lua
local function sapa()
	print("Selamat datang di dunia Roblox!")
end

sapa()  -- memanggil fungsi sapa
```

### Latihan:

Buat fungsi bernama `perkenalan` yang mencetak namamu dan usia.

```lua
local function perkenalan()
	print("Halo, aku Raka dan aku 13 tahun.")
end

perkenalan()
```

---

## 🎯 Bagian C: Apa Itu Event?

Event membuat kode jalan saat sesuatu terjadi.

### Contoh: Sentuh Part

1. Buat 1 Part di Workspace.
2. Tambahkan Script di dalam Part.
3. Tulis kode ini:

```lua
local part = script.Parent

local function disentuh(apaYangMenyentuh)
	print("Part disentuh oleh: ", apaYangMenyentuh.Name)
end

part.Touched:Connect(disentuh)
```

🔁 Penjelasan:

- `Touched` adalah event saat part disentuh.
- `Connect` menghubungkan event ke fungsi `disentuh`.

Coba:
Jalankan game dan sentuh part dengan karaktermu!

---

## 🧠 Latihan Mandiri

1. Buat variabel `buahFavorit` dan cetak ke Output.
2. Buat fungsi `serang()` yang mencetak `"Zzzap! Serangan petir!"`.
3. Buat Part yang saat disentuh mencetak `"Aduh! Kamu menyentuhnya!"`.

---

## 🧪 Tantangan Ekstra

Gabungkan semuanya:

- Saat menyentuh part, panggil fungsi `serang()`, dan tampilkan nama buah favoritmu di output!

---

## ✅ Kamu Sudah Bisa...

- Membuat variabel 🧺
- Membuat fungsi 🧩
- Menangkap event 🖱️
- Kamu sudah mulai jadi coder Roblox beneran! 🚀

➡️ Lanjut ke [Pertemuan 4 - Memahami LocalScript vs Script vs ModuleScript](https://github.com/ihksanghazi/ScriptingRobloxTutorial/tree/Pertemuan_4)
