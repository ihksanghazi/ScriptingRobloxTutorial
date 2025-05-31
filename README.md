# 💥 Meeting 12: Buat Efek Serangan Buah (Part dan Animasi Sederhana)

## 🎯 Tujuan

- Membuat **efek visual** saat jurus digunakan.
- Menggunakan **Part** dan **animasi sederhana**.
- Menambahkan sedikit **keajaiban visual** ke jurus!

---

## 📖 Cerita Game

Kamu sudah bisa pakai jurus dengan tombol Z (Meeting 11). Tapi... jurusnya cuma bola yang muncul. Sekarang kita bikin efeknya lebih keren!

Contoh: Saat pakai Flame Fruit, muncul bola api yang meluncur ke depan dengan cahaya menyala 🔥✨

---

## 🔥 Langkah 1: Script Jurus dengan Efek

Buka script yang ada di `ServerScriptService` dari Meeting 11. Kita ubah bagian `if tombol == "Z"` supaya jadi lebih menarik:

### ✨ Ganti dengan ini:

```lua
if tombol == "Z" and buah == "Flame Fruit" then
	local bolaApi = Instance.new("Part")
	bolaApi.Shape = Enum.PartType.Ball
	bolaApi.BrickColor = BrickColor.new("Bright orange")
	bolaApi.Material = Enum.Material.Neon
	bolaApi.Size = Vector3.new(2,2,2)
	bolaApi.Anchored = false
	bolaApi.CanCollide = false
	bolaApi.Position = player.Character.Head.Position + player.Character.Head.CFrame.LookVector * 3
	bolaApi.Parent = workspace

	-- Tambahkan cahaya
	local light = Instance.new("PointLight")
	light.Brightness = 3
	light.Range = 8
	light.Color = Color3.new(1, 0.4, 0)
	light.Parent = bolaApi

	-- Tambahkan gerakan
	local bodyVelocity = Instance.new("BodyVelocity")
	bodyVelocity.Velocity = player.Character.Head.CFrame.LookVector * 60
	bodyVelocity.Parent = bolaApi

	-- Hapus setelah 3 detik
	game.Debris:AddItem(bolaApi, 3)
end
```

---

## 🎬 Bonus: Efek Animasi Sederhana

Kita bisa buat bola api berputar biar makin keren.
Tambahkan ini di bawah `bolaApi.Parent = workspace`:

```lua
-- Putar bola terus-menerus
task.spawn(function()
	while bolaApi and bolaApi.Parent do
		bolaApi.Orientation += Vector3.new(0, 10, 0)
		wait(0.05)
	end
end)
```

---

## 💡 Mau Ganti Jadi Es?

Coba ubah warna dan nama buah:

```lua
if tombol == "Z" and buah == "Ice Fruit" then
	bolaApi.BrickColor = BrickColor.new("Toothpaste")
	light.Color = Color3.new(0.6, 0.9, 1)
end
```

---

## 🧪 Coba Tes!

1. Jalankan game.
2. Tekan tombol Z.
3. Bola api muncul, terang, dan terbang ke depan 🔥🌀
4. Ganti nama buah jadi `"Ice Fruit"` → efek jadi warna biru ❄️

---

## 🎁 Tantangan Kreatif

- Buat efek **petir** untuk "Lightning Fruit".
- Tambahkan **ledakan** kecil saat bola menyentuh sesuatu.
- Gunakan **SoundEffect** biar makin hidup.

---

## ✅ Hari Ini Kamu Sudah Bisa...

- Membuat **efek visual jurus**.
- Menambahkan **cahaya & animasi sederhana**.
- Membuat jurus yang terasa lebih “hidup”!

Keren banget! 🎉 Game kamu sekarang punya jurus yang benar-benar kelihatan **epik**!

➡️ Lanjut ke [Pertemuan 13 - Deteksi tabrakan serangan ke musuh](https://github.com/ihksanghazi/ScriptingRobloxTutorial/tree/Pertemuan_13)
