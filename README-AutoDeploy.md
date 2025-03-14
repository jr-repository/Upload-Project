# 🚀 Auto Deploy Website ke GitHub Pages dengan GitHub Actions

Tutorial ini menjelaskan bagaimana cara mengatur **auto deploy** ke GitHub Pages menggunakan **GitHub Actions** setiap kali ada perubahan pada branch `main`.

---

## 🔗 Contoh Link Live

🖥️ https://jr-repository.github.io/templateartweb1/

---

## ✅ Langkah-langkah Auto Deploy

### 1. Pastikan Repository Sudah Dihubungkan ke GitHub

Jika belum, jalankan perintah berikut:

```bash
git init
git remote add origin https://github.com/jr-repository/templateartweb1.git
git pull origin main
```

---

### 2. Buat Branch `gh-pages`

```bash
git checkout -b gh-pages
```

> Branch ini digunakan sebagai tempat hasil deploy otomatis.

---

### 3. Buat Folder untuk Workflow

```bash
mkdir -p .github/workflows
```

---

### 4. Buat File Workflow untuk Auto Deploy

```bash
nano .github/workflows/deploy.yml
```

Isi dengan skrip berikut:

```yaml
name: Deploy ke GitHub Pages

on:
  push:
    branches:
      - main  # Menjalankan deploy setiap ada perubahan di branch main

jobs:
  deploy:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout Repository
        uses: actions/checkout@v3

      - name: Setup Node.js
        uses: actions/setup-node@v3
        with:
          node-version: '18'

      - name: Deploy ke GitHub Pages
        uses: JamesIves/github-pages-deploy-action@v4
        with:
          branch: gh-pages     # Branch tujuan untuk deploy
          folder: .            # Folder yang akan di-deploy (root folder)
```

> Tekan `CTRL + X`, lalu `Y`, lalu `Enter` untuk menyimpan.

---

### 5. Commit dan Push File Workflow

```bash
git add .github/workflows/deploy.yml
git commit -m "Menambahkan auto deploy ke GitHub Pages"
git push origin main
```

---

### 6. Aktifkan GitHub Pages

- Buka repository kamu di GitHub.
- Masuk ke menu: `Settings > Pages`.
- Pilih:
  - **Source**: `gh-pages`
  - **Folder**: `/ (root)`
- Klik **Save**.

---

### 7. Cek Deployment

Setiap kali kamu push ke `main`, GitHub Actions akan otomatis membangun dan mendistribusikan website kamu ke:

🌐 `https://jr-repository.github.io/templateartweb1/`

---

## 🎉 Selesai!

Sekarang setiap kali kamu melakukan commit ke branch `main`, websitemu akan **otomatis update** di GitHub Pages tanpa perlu upload manual lagi!

---

> Tips: Pastikan file utama kamu seperti `index.html` ada di root folder repo.
