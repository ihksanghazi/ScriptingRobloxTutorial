# ⚔️ Meeting 11: Gunakan Skill dengan Tombol (InputBegan)

## 🎯 Tujuan

- Belajar cara mendeteksi **tombol keyboard ditekan**.
- Menjalankan **skill buah** saat pemain tekan tombol.
- Menghubungkan buah yang dimiliki pemain ke aksi tertentu.

---

## 💡 Cerita Game

Misalnya kamu sudah makan "Flame Fruit", lalu kamu tekan tombol **Z** → Boom! Bola api keluar! 🔥

Kita akan buat hal keren seperti itu hari ini!

---

## 📦 Yang Dibutuhkan

- RemoteEvent: `GunakanSkillEvent`
- Data buah pemain (dari meeting sebelumnya)
- LocalScript untuk cek tombol ditekan
- Script Server untuk keluarkan efek/jurus

---

## 🔁 Langkah 1: Siapkan RemoteEvent

1. Klik `ReplicatedStorage` → `Insert Object` → `RemoteEvent`
2. Ganti nama: `GunakanSkillEvent`

---

## 🖥️ Langkah 2: Buat LocalScript di `StarterPlayerScripts`

1. Klik `StarterPlayer > StarterPlayerScripts` → `Insert Object` → `LocalScript`
2. Tulis ini:

```lua
local UserInputService = game:GetService("UserInputService")
local remote = game.ReplicatedStorage:WaitForChild("GunakanSkillEvent")

UserInputService.InputBegan:Connect(function(input, isTyping)
	if isTyping then return end  -- Kalau sedang mengetik chat, abaikan

	if input.KeyCode == Enum.KeyCode.Z then
		print("Tombol Z ditekan!")
		remote:FireServer("Z")  -- Kirim ke server: Tombol apa yang ditekan
	end
end)
```

---

## 🛡️ Langkah 3: Script Server di `ServerScriptService`

1. Buat Script baru di `ServerScriptService`.
2. Isi:

```lua
local remote = game.ReplicatedStorage:WaitForChild("GunakanSkillEvent")
local buahPemain = {}  -- Buah yang dimiliki pemain

game.Players.PlayerAdded:Connect(function(player)
	buahPemain[player.UserId] = "Flame Fruit"  -- Contoh: buah awal
end)

game.Players.PlayerRemoving:Connect(function(player)
	buahPemain[player.UserId] = nil
end)

remote.OnServerEvent:Connect(function(player, tombol)
	local buah = buahPemain[player.UserId]
	print(player.Name .. " menekan " .. tombol .. " dengan buah " .. buah)

	if tombol == "Z" and buah == "Flame Fruit" then
		-- Keluarkan jurus api
		local bolaApi = Instance.new("Part")
		bolaApi.Shape = Enum.PartType.Ball
		bolaApi.BrickColor = BrickColor.new("Bright orange")
		bolaApi.Material = Enum.Material.Neon
		bolaApi.Size = Vector3.new(2,2,2)
		bolaApi.Anchored = false
		bolaApi.CanCollide = false
		bolaApi.Position = player.Character.Head.Position + player.Character.Head.CFrame.LookVector * 3
		bolaApi.Parent = workspace

		local bodyVelocity = Instance.new("BodyVelocity")
		bodyVelocity.Velocity = player.Character.Head.CFrame.LookVector * 50
		bodyVelocity.Parent = bolaApi

		game.Debris:AddItem(bolaApi, 3)  -- Hapus bola setelah 3 detik
	end
end)
```

---

## 🧪 Tes Yuk!

1. Jalankan game (`Play`).
2. Tekan tombol **Z** → Bola api muncul di depan karakter.
3. Coba ganti `buahPemain[...] = "Flame Fruit" jadi "Ice Fruit"` lalu buat jurus yang berbeda!

---

## 🧠 Tips Tambahan

- Kamu bisa buat tombol lain seperti:
  - X → Skill kedua
  - C → Skill ketiga
- Tambahkan efek suara, cahaya, atau animasi biar makin keren!

---

## ✅ Hari Ini Kamu Sudah Bisa...

- Deteksi tombol keyboard (InputBegan)
- Kirim info tombol ke server
- Jalankan jurus dari buah tertentu
- Simulasi skill seperti di game Blox Fruits!

🔥 Keren banget! Sekarang game kamu udah mulai punya jurus kayak ninja atau pahlawan!

➡️ Lanjut ke [Pertemuan 12 - Buat efek serangan buah (part, animasi sederhana)](https://github.com/ihksanghazi/ScriptingRobloxTutorial/tree/Pertemuan_12)
