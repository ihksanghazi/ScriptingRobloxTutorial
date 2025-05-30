# 🧪 Meeting 8: Ujian Mini – Proyek Mini dengan RemoteEvent

## 🎯 Tujuan

- Menguji pemahaman kamu tentang **RemoteEvent**.
- Membuat **proyek mini mandiri** yang pakai tombol dan efek.
- Menunjukkan kreativitasmu sendiri! 🎨

---

## 🧠 Recap Singkat

Sampai sekarang, kamu sudah belajar:

- Cara pakai RemoteEvent untuk kirim pesan Client ⇄ Server.
- Buat tombol GUI pakai `TextButton`.
- Membuat Part dan Efek dari Script di Server.

---

## 🏗️ Tugas Proyek Mini

Buat **satu fitur game kecil** yang punya:

1. Tombol GUI (di layar).
2. LocalScript yang kirim `RemoteEvent` ke server.
3. Script server yang munculkan sesuatu (Part, Efek, atau suara).

---

## 📌 Contoh Ide Proyek Mini

💥 **Jurusan Api**

> Klik tombol → server spawn bola api di depan karakter!

🌟 **Cahaya Kekuatan**

> Klik tombol → karakter disinari cahaya kuning cerah selama 2 detik.

⚡ **Summon Batu Besar**

> Klik tombol → server spawn batu besar di posisi tertentu.

💡 **Kreasi Bebas**

> Boleh campur Part, efek suara, warna, dan posisi! Asal pakai `RemoteEvent`.

---

## 🛠️ Langkah Bimbingan (Kalau Perlu)

### 1. Siapkan RemoteEvent

- Buat `RemoteEvent` di `ReplicatedStorage`, contoh: `JurusEvent`

### 2. Buat Tombol

- Masukkan `TextButton` ke `StarterGui > ScreenGui`
- Tulis teks: `Gunakan Jurus!`

### 3. LocalScript

```lua
local tombol = script.Parent
local remote = game.ReplicatedStorage:WaitForChild("JurusEvent")

tombol.MouseButton1Click:Connect(function()
	remote:FireServer()
end)
```

### 4. Script Server

```lua
local remote = game.ReplicatedStorage:WaitForChild("JurusEvent")

remote.OnServerEvent:Connect(function(player)
	local part = Instance.new("Part")
	part.Size = Vector3.new(5,1,5)
	part.Position = player.Character.HumanoidRootPart.Position + Vector3.new(0,5,0)
	part.BrickColor = BrickColor.new("Bright red")
	part.Anchored = true
	part.Parent = workspace
end)
```

---

## ✅ Checklist Proyek Mini

| Fitur                       | Sudah? ✅ |
| --------------------------- | --------- |
| Ada tombol GUI              |           |
| Tombol pakai LocalScript    |           |
| Ada RemoteEvent di tengah   |           |
| Script Server respon tombol |           |
| Efek atau part muncul       |           |

---

## 🎁 Bonus Challenge

🔊 Tambahkan suara saat tombol diklik!
🌈 Munculkan part dengan warna acak setiap klik!
🌀 Tambahkan animasi atau particle effect (nanti kita bahas partikel ya 😉)

---

## 🏁 Penutup

Selamat! Kamu baru saja menyelesaikan:

- 8 Pertemuan Scripting Dasar
- Dan membuat proyek pertamamu! 🎉

🧠 Jangan takut eksplorasi ya. Coding itu tempat bermain ide dan imajinasi 💡

➡️ Lanjut ke [Pertemuan 9 - Menyimpan data buah pemain (ServerScriptService)](https://github.com/ihksanghazi/ScriptingRobloxTutorial/tree/Pertemuan_9)
