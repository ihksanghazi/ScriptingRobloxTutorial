# 🧪 Meeting 6: Praktik – Tombol Klik untuk Spawn Part (RemoteEvent)

## 🎯 Tujuan

- Membuat **tombol GUI** di layar.
- Mengirim perintah dari **Client** ke **Server** saat tombol diklik.
- Server akan **munculkan Part** di dunia!

---

## 🔁 Mengingat Kembali

> Kita akan pakai **RemoteEvent** untuk mengirim pesan dari tombol (Client) ke Script (Server).

---

## 🧱 Langkah A: Siapkan RemoteEvent

1. Klik `ReplicatedStorage` → klik kanan → `Insert Object` → `RemoteEvent`.
2. Ganti namanya jadi: `SpawnPartEvent`.

---

## 🎮 Langkah B: Buat Tombol GUI

1. Klik `StarterGui` → klik kanan → `Insert Object` → `ScreenGui`.
2. Klik `ScreenGui` → klik kanan → `Insert Object` → `TextButton`.
3. Atur properti tombol:
   - **Name**: `SpawnButton`
   - **Text**: `Spawn Part!`
   - **Size**: `UDim2.new(0, 200, 0, 50)`
   - **Position**: `UDim2.new(0.5, -100, 0.8, 0)` (tengah bawah)

---

## 💻 Langkah C: Tambahkan LocalScript ke Tombol

1. Klik kanan pada `SpawnButton` → `Insert Object` → `LocalScript`.
2. Isi dengan kode ini:

```lua
local tombol = script.Parent
local remote = game.ReplicatedStorage:WaitForChild("SpawnPartEvent")

tombol.MouseButton1Click:Connect(function()
	remote:FireServer()  -- kirim sinyal ke server
end)
```

---

## 🧠 Langkah D: Buat Script di Server untuk Spawn Part

1. Klik ServerScriptService → klik kanan → Insert Object → Script.
2. Isi dengan kode ini:

```lua
local remote = game.ReplicatedStorage:WaitForChild("SpawnPartEvent")

remote.OnServerEvent:Connect(function(player)
	local partBaru = Instance.new("Part")
	partBaru.Size = Vector3.new(4, 1, 4)
	partBaru.BrickColor = BrickColor.Random()
	partBaru.Anchored = true
	partBaru.Position = player.Character.HumanoidRootPart.Position + Vector3.new(0, 5, 0)
	partBaru.Parent = workspace
end)
```

🎉 Sekarang saat tombol diklik, server akan spawn 1 part di atas kepala pemain!

---

## 🔍 Penjelasan

| Bagian Kode                       | Artinya                                        |
| --------------------------------- | ---------------------------------------------- |
| `MouseButton1Click`               | Event saat tombol di-klik                      |
| `FireServer()`                    | Kirim sinyal ke server                         |
| `Instance.new("Part")`            | Buat Part baru                                 |
| `player.Character.Position + ...` | Menentukan posisi Part muncul (di atas pemain) |

---

## 🧠 Latihan Mandiri

1. Ubah warna Part jadi `BrickColor.new("Bright yellow")`.
2. Ganti ukuran Part jadi lebih besar.
3. Tambahkan efek suara atau partikel saat Part muncul (nanti kita bahas efek ya!).

---

## Kamu Sudah Bisa...

- Bikin GUI tombol di layar
- Kirim event dari Client ke Server saat tombol diklik
- Spawn Part dari Server

Keren! 🎉 Kamu barusan bikin fitur interaktif yang pakai RemoteEvent dan GUI! Ini bisa kamu pakai untuk spawn musuh, beri efek, atau panggil jurus spesial 💥

➡️ Lanjut ke [Pertemuan 7 - Latihan: buat sistem tombol untuk spawn efek](https://github.com/ihksanghazi/ScriptingRobloxTutorial/tree/Pertemuan_7)
