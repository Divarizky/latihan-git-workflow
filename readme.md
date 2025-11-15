# Latihan Git Workflow
Repositori ini dibuat untuk latihan memahami Git Workflow modern (main, develop, feature branch), menangani merge conflict, dan mensimulasikan alur kerja tim developer.

## Tujuan Latihan
1. Memahami struktur branch standar.
2. Membuat feature branch.
3. Menghasilkan merge conflict dan menyelesaikannya.
4. Membuat pull request (PR).
5. Simulasi code review dan merging.

## 📂 Struktur Repository

```
latihan-git-workflow/
│
├── readme.md
├── conflict.txt
├── fitur-login.txt
└── profile.txt (latihan pribadi)
```

## Langkah Latihan

### 1. Clone Repository
```
git clone <url-repo>
cd latihan-git-workflow
```

### 2. Buat Branch `develop`
```
git checkout -b develop
git push origin develop
```

### 3. Buat Feature Branch
Contoh pembuatan branch fitur login:

```
git checkout develop
git checkout -b feature/auth-login
```

Tambahkan file:

```
echo "Fitur login: sudah dibuat" >> fitur-login.txt
git add .
git commit -m "feat(auth): inisiasi fitur login"
git push origin feature/auth-login
```

### 4. Buat Konflik Merge
Pada branch feature:

```
echo "Ini dari feature/auth-login" >> conflict.txt
git add .
git commit -m "feat(auth): update conflict file"
git push
```

Pada branch develop:

```
git checkout develop
echo "Ini dari develop" >> conflict.txt
git add .
git commit -m "chore: update conflict file di develop"
git push
```

### 5. Merge dan Perbaiki Konflik
```
git checkout develop
git merge feature/auth-login
```

Perbaiki `conflict.txt` dengan menggabungkan kedua versi:

```
Ini dari branch develop
Ini dari branch feature/auth-login
```

Setelah itu:

```
git add conflict.txt
git commit
git push
```

### 6. Pull Request
- Lakukan PR (Pull Request) dari `develop` → `main`
- Tambahkan komentar sebagai simulasi code review
- Merge jika sudah sesuai

## 📄 Catatan
Latihan ini bertujuan agar pengembang memahami proses kolaborasi Git secara terstruktur dan dapat menangani konflik secara mandiri. Dengan menyelesaikan seluruh langkah, pengembang mendapatkan gambaran alur kerja Git dalam proyek nyata.
