# 🍇 Meeting 10: RemoteEvent untuk Makan Buah Sekarang

## 🎯 Tujuan

- Membuat **tombol GUI** untuk “makan buah”.
- Kirim pesan ke Server pakai **RemoteEvent**.
- Server menyimpan buah yang dimakan oleh pemain.

---

## 🧠 Cerita Game

Bayangkan kamu nemu buah seperti:

- 🔥 Flame Fruit
- ❄️ Ice Fruit
- ⚡ Lightning Fruit

Lalu kamu klik tombol “Makan” → Server tahu kamu makan buah itu → dan menyimpannya. Gampang kan?

---

## 🛠️ Langkah A: RemoteEvent

1. Klik `ReplicatedStorage` → `Insert Object` → `RemoteEvent`.
2. Ganti nama: `MakanBuahEvent`.

---

## 🖱️ Langkah B: Buat GUI Makan Buah

1. Klik `StarterGui` → `Insert Object` → `ScreenGui`.
2. Di dalamnya, buat:
   - **TextButton** → nama: `MakanButton`
   - **TextLabel** → nama: `NamaBuahLabel`

Atur seperti ini:

- `TextButton.Text = "Makan Buah"`
- `TextLabel.Text = "Flame Fruit"` _(ini contoh buah yang mau dimakan)_

---

## 💻 Langkah C: LocalScript di Tombol

Klik kanan `MakanButton` → `Insert Object` → `LocalScript`. Lalu isi:

```lua
local tombol = script.Parent
local label = tombol.Parent:WaitForChild("NamaBuahLabel")
local remote = game.ReplicatedStorage:WaitForChild("MakanBuahEvent")

tombol.MouseButton1Click:Connect(function()
	local namaBuah = label.Text
	remote:FireServer(namaBuah)
end)
```

---

## 🔐 Langkah D: Script di Server

1. Klik `ServerScriptService` → `Insert Object` → `Script`.
2. Isi kodenya:

```lua
local remote = game.ReplicatedStorage:WaitForChild("MakanBuahEvent")
local buahPemain = {}  -- Data penyimpanan buah

remote.OnServerEvent:Connect(function(player, namaBuah)
	buahPemain[player.UserId] = namaBuah
	print(player.Name .. " makan buah: " .. namaBuah)
end)

-- Tambahkan juga saat pemain keluar
game.Players.PlayerRemoving:Connect(function(player)
	buahPemain[player.UserId] = nil
end)

```

---

## 🧪 Tes Yuk!

1. Jalankan game (`Play`).
2. Klik tombol **"Makan Buah"**.
3. Lihat di Output → muncul:

```csharp
[Nama Pemain] makan buah: Flame Fruit
```

4. Coba ganti tulisan di `NamaBuahLabel` jadi "Ice Fruit", klik lagi.

---

## 🎁 Latihan Tambahan

🔄 Buat beberapa tombol buah:

- Tombol "Flame"
- Tombol "Ice"
- Tombol "Lightning"

Setiap tombol ubah isi `NamaBuahLabel`, lalu klik "Makan".
👀 Tambahkan `TextLabel` untuk menunjukkan “Buah Kamu Sekarang: ...”

---

## ✅ Kamu Sudah Bisa...

- Kirim info dari Client ke Server pakai RemoteEvent
- Kirim **data penting** (seperti nama buah)
- Simpan buah yang dimakan pemain!

Keren! Ini bisa jadi awal untuk sistem skill atau jurus. 💥

➡️ Lanjut ke [Pertemuan 11 - Gunakan skill dengan tombol (InputBegan)](https://github.com/ihksanghazi/ScriptingRobloxTutorial/tree/Pertemuan_11)
