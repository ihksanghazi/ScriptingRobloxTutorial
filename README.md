# 🍎 Meeting 9: Menyimpan Data Buah Pemain (ServerScriptService)

## 🎯 Tujuan

- Belajar cara **menyimpan data pemain** di server.
- Menyimpan **nama buah** yang dimiliki pemain.
- Data disimpan selama sesi game berlangsung.

---

## 🔍 Kenapa Perlu Menyimpan Data?

Kalau pemain ambil buah (misalnya: “Flame Fruit”), kita perlu simpan info itu. Jadi kalau pemain pakai jurus atau bertarung, server tahu buah apa yang dia punya.

---

## 🧱 Langkah A: Siapkan Tempat Menyimpan Data

Kita akan buat tabel (`table`) di server untuk menyimpan buah setiap pemain.

### 1. Buka `ServerScriptService`

Klik kanan → `Insert Object` → `Script`.

### 2. Tulis kodenya seperti ini:

```lua
local Players = game:GetService("Players")

-- Buat penyimpanan data buah
local buahPemain = {}

-- Saat pemain masuk game
Players.PlayerAdded:Connect(function(player)
	print(player.Name .. " telah masuk!")

	-- Simpan data awal buah
	buahPemain[player.UserId] = "Belum punya buah"

	-- Contoh: kasih buah awal (bisa kamu ganti)
	wait(3)
	buahPemain[player.UserId] = "Flame Fruit"
	print(player.Name .. " sekarang punya buah: " .. buahPemain[player.UserId])
end)

-- Saat pemain keluar
Players.PlayerRemoving:Connect(function(player)
	-- Hapus data dari memori
	buahPemain[player.UserId] = nil
end)
```

---

## 📦 Apa yang Terjadi?

| Bagian Kode                       | Artinya                                      |
| --------------------------------- | -------------------------------------------- |
| `PlayerAdded`                     | Saat pemain masuk ke game                    |
| `buahPemain[player.UserId] = ...` | Simpan nama buah berdasarkan ID pemain       |
| `PlayerRemoving`                  | Saat pemain keluar, data dihapus dari memori |

---

## 🧪 Coba Tes

1. Jalankan game di Roblox Studio (Play).
2. Lihat di **Output**:
   - Akan muncul nama pemain dan buah yang dimiliki.
3. Coba ganti `"Flame Fruit"` jadi buah lain, misalnya `"Ice Fruit"` atau `"Magma Fruit"`.

---

## 🧠 Pengetahuan Tambahan

- Data ini **belum tersimpan** permanen.
- Artinya: Kalau keluar game, datanya hilang.
- Nanti di pelajaran lanjutan, kita akan pakai **DataStore** untuk menyimpan data permanen.

---

## 💡 Bonus Latihan

1. Buat RemoteEvent untuk meminta nama buah pemain.
2. Tambahkan command di chat, misalnya: /buahku → tampilkan buah pemain.
   Contoh Kode

   ```lua
   game.Players.PlayerAdded:Connect(function(player)
   	player.Chatted:Connect(function(pesan)
   		if pesan == "/buahku" then
   			local buah = buahPemain[player.UserId]
   			if buah then
   				print("Buah kamu: " .. buah)
   			end
   		end
   	end)
   end)

   ```

---

## ✅ Kamu Sudah Bisa...

- Simpan info penting di server.
- Hubungkan data ke UserId pemain.
- Bikin sistem awal untuk data “buah”.

Mantap! Sekarang kamu bisa bikin sistem pemain yang punya item khusus seperti buah 🔥❄️🌪️

➡️ Lanjut ke [Pertemuan 10 - RemoteEvent untuk makan buah](https://github.com/ihksanghazi/ScriptingRobloxTutorial/tree/Pertemuan_10)
