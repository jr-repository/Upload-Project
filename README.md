# 📤 Cara Upload Project ke GitHub Menggunakan VS Code & Terminal

Panduan singkat untuk mengunggah project lokal ke GitHub menggunakan **Visual Studio Code** dan **Git CLI**. Cocok untuk pemula!

---

## 🛠️ Persiapan Awal

- Pastikan kamu sudah:
  - Menginstall [Git](https://git-scm.com/)
  - Memiliki akun GitHub
  - Membuat repository kosong di GitHub (contoh: `templateartweb1`)
  - Menginstall [VS Code](https://code.visualstudio.com/)

---

## 🧩 Langkah-langkah

### 1. Buka VS Code dan Terminal

- Buka folder project kamu (`templateartweb1`) di VS Code.
- Buka terminal dengan:
  - Menekan `Ctrl + ~`  
  - Atau menu: `Terminal > New Terminal`

---

### 2. Inisialisasi Git (Jika Belum)

```bash
git init
```

---

### 3. Tambahkan Remote Repository

Hubungkan ke repository GitHub kamu:

```bash
git remote add origin https://github.com/jr-repository/templateartweb1.git
```

> 🔁 Jika sebelumnya sudah ada remote lama:

```bash
git remote remove origin
git remote add origin https://github.com/jr-repository/templateartweb1.git
```

---

### 4. Cek Status File

Lihat file yang belum dilacak Git:

```bash
git status
```

---

### 5. Tambahkan Semua File ke Staging Area

```bash
git add .
```

---

### 6. Commit Perubahan

Buat commit pertama dengan pesan:

```bash
git commit -m "Initial commit for templateartweb1"
```

---

### 7. Push ke GitHub

Kirim project kamu ke GitHub:

```bash
git branch -M main
git push -u origin main
```

> Jika diminta login:  
> - Masukkan **username GitHub**  
> - Masukkan **Personal Access Token (PAT)** sebagai pengganti password  
> [Buat token di sini](https://github.com/settings/tokens)

---

### 8. Cek di GitHub

Buka browser dan kunjungi:  
🔗 [https://github.com/jr-repository/templateartweb1](https://github.com/jr-repository/templateartweb1)  
Pastikan semua file sudah muncul!

---

## ✅ Selesai!

Project kamu sekarang sudah tersimpan di GitHub dan bisa dibagikan ke siapa saja!  
Kalau ada error atau kendala, jangan ragu untuk bertanya. 🚀

---

> Dibuat oleh: [jr-repository](https://github.com/jr-repository)
