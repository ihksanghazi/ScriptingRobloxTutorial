# 💥 Meeting 7: Latihan – Buat Sistem Tombol untuk Spawn Efek

## 🎯 Tujuan

- Membuat **tombol GUI** seperti sebelumnya.
- Menghubungkannya ke **RemoteEvent**.
- Server akan membuat **efek keren** (seperti ledakan atau cahaya) saat tombol diklik.

---

## 🧠 Apa yang Akan Kita Buat?

Kita akan buat:

1. Tombol `Spawn Efek`.
2. Saat diklik → kirim pesan ke Server.
3. Server munculkan efek spesial, misalnya **ledakan api** atau **cahaya kilat**.

---

## 🛠️ Langkah A: RemoteEvent

1. Klik `ReplicatedStorage` → `Insert Object` → pilih `RemoteEvent`.
2. Ganti nama jadi: `SpawnEffectEvent`.

---

## 🎮 Langkah B: Buat Tombol GUI

1. Klik `StarterGui` → `Insert Object` → `ScreenGui`.
2. Di dalam `ScreenGui`, klik kanan → `Insert Object` → `TextButton`.
3. Atur properti tombol:
   - **Name**: `EffectButton`
   - **Text**: `Spawn Efek!`
   - **Size**: `UDim2.new(0, 200, 0, 50)`
   - **Position**: `UDim2.new(0.5, -100, 0.7, 0)` (tengah bawah layar)

---

## 💻 Langkah C: Tambahkan LocalScript ke Tombol

1. Klik kanan pada `EffectButton` → `Insert Object` → `LocalScript`.
2. Isi kodenya:

```lua
local tombol = script.Parent
local remote = game.ReplicatedStorage:WaitForChild("SpawnEffectEvent")

tombol.MouseButton1Click:Connect(function()
	remote:FireServer()
end)
```

---

## 🔥 Langkah D: Script untuk Membuat Efek

1. Klik `ServerScriptService` → `Insert Object` → `Script`.
2. Isi kodenya:

```lua
local remote = game.ReplicatedStorage:WaitForChild("SpawnEffectEvent")

remote.OnServerEvent:Connect(function(player)
	-- Posisi efek muncul: di atas kepala pemain
	local posisi = player.Character.HumanoidRootPart.Position + Vector3.new(0, 5, 0)

	-- Buat efek ledakan
	local ledakan = Instance.new("Explosion")
	ledakan.Position = posisi
	ledakan.BlastRadius = 5
	ledakan.BlastPressure = 50000
	ledakan.Parent = workspace
end)
```

✨ Efeknya: BOOM! Ledakan muncul di atas pemain yang klik tombol!

---

## 🧠 Variasi Efek Lain

### Cahaya Kilat:

```lua
local kilat = Instance.new("PointLight")
kilat.Color = Color3.new(1, 1, 0)  -- kuning
kilat.Range = 15
kilat.Brightness = 10

local part = Instance.new("Part")
part.Anchored = true
part.Size = Vector3.new(1,1,1)
part.Transparency = 1
part.CanCollide = false
part.Position = posisi
kilat.Parent = part
part.Parent = workspace

game.Debris:AddItem(part, 1)  -- hilang setelah 1 detik
```

🔁 Kamu bisa coba ganti efek ledakan dengan cahaya kilat ini, atau gabungkan dua-duanya!

---

## 🎯 Latihan Mandiri

1. Tambahkan tombol lain bernama `Spawn Kilat!` dan munculkan cahaya kilat.
2. Coba munculkan efek di posisi mouse (lanjutan nanti).
3. Ganti warna dan radius efek ledakan.

---

## ✅ Kamu Sudah Bisa...

- Buat tombol GUI interaktif
- Kirim pesan ke Server dengan RemoteEvent
- Spawn efek visual dari Server (Explosion atau cahaya)

Kamu makin jago! Efek ini bisa dipakai untuk jurus, serangan, atau respon dari game. 🔥⚡

➡️ Lanjut ke [Pertemuan 8 - Ujian mini: proyek mini dengan RemoteEvent](https://github.com/ihksanghazi/ScriptingRobloxTutorial/tree/Pertemuan_8)
