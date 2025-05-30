# 🔁 Meeting 5: RemoteEvent – Komunikasi Client-Server Dasar

## 🎯 Tujuan

- Mengerti cara kerja **Client** dan **Server** di Roblox.
- Belajar menggunakan **RemoteEvent** untuk mengirim pesan antar script.
- Membuat contoh tombol yang mengirim pesan dari pemain ke server.

---

## 🧾 Apa Itu Client dan Server?

> 🔹 **Client** = Pemain yang main game di komputernya sendiri.  
> 🔹 **Server** = Tempat utama yang mengatur semua hal di dalam game.

🧠 Client dan Server **tidak bisa langsung ngobrol**. Mereka butuh "alat komunikasi", yaitu:

### 🎤 RemoteEvent

RemoteEvent adalah "walkie-talkie" antara client dan server. Bisa kirim pesan 2 arah:

- Dari **Client ke Server**
- Dari **Server ke Client**

---

## 🛠️ Contoh: Pemain Tekan Tombol → Server Cetak Pesan

### Langkah 1: Buat RemoteEvent

1. Klik kanan `ReplicatedStorage` → `Insert Object` → pilih `RemoteEvent`.
2. Ganti nama jadi: `KirimPesan`.

---

### Langkah 2: Buat LocalScript (Client)

1. Masuk ke `StarterPlayer > StarterPlayerScripts`.
2. Tambahkan `LocalScript`.
3. Isi dengan:

```lua
local remote = game.ReplicatedStorage:WaitForChild("KirimPesan")

-- Kirim pesan ke server saat game dimulai
remote:FireServer("Halo dari Client!")
```

### Langkah 3: Buat Script (Server)

1. Tambahkan Script ke dalam ServerScriptService.
2. Isi dengan:

```lua
local remote = game.ReplicatedStorage:WaitForChild("KirimPesan")

remote.OnServerEvent:Connect(function(player, pesan)
	print(player.Name .. " mengirim pesan: " .. pesan)
end)
```

💬 Sekarang saat game dimulai, server akan menerima dan mencetak pesan dari client!

### 💡 Penjelasan

| Fungsi                    | Artinya                            |
| ------------------------- | ---------------------------------- |
| `FireServer(...)`         | Kirim pesan dari client ke server  |
| `OnServerEvent:Connect()` | Terima pesan di server dari client |
| `player`                  | Nama pemain yang mengirim pesan    |
| `pesan`                   | Isi pesan yang dikirim             |

---

## 🎮 Latihan Mandiri

1. Ubah isi pesan menjadi `"Aku siap bertarung!"`.
2. Coba kirim angka dari client, misalnya skor.
3. Tambahkan tombol GUI untuk mengirim RemoteEvent (nanti kita bahas GUI lebih dalam ya!).

---

## 🧪 Tantangan Seru

- Buat LocalScript yang mengirim `"Serangan Z diluncurkan!"` saat tombol Z ditekan.
- Di Script server, tampilkan pesan dari pemain yang menekan Z.

---

## ✅ Kamu Sudah Bisa...

- Bikin RemoteEvent untuk komunikasi Client ↔ Server
- Mengirim pesan dari LocalScript ke Script
- Menerima pesan dan mencetaknya di server

Keren banget! Ini dasar penting untuk bikin skill, misi, dan sistem pertarungan multiplayer 💥

➡️ Lanjut ke [Pertemuan 6 - Praktik: tombol klik spawn part dengan RemoteEvent](https://github.com/ihksanghazi/ScriptingRobloxTutorial/tree/Pertemuan_6)
