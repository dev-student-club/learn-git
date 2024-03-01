# Git Workflow and Best Practices

This repository contains guidelines and best practices for working with Git. Whether you're new to Git or looking to improve your workflow, this guide will cover essential concepts and commands to help you effectively manage your projects.

## Table of Contents

- [Cara Pakai SourceTree](#cara-pakai-sourcetree)
- [Basic Git Commands](#basic-git-commands)
  - [Commit](#commit)
  - [Pull](#pull)
  - [Push](#push)
- [Stash](#stash)
- [Merge](#merge)
- [Rebase](#rebase)
- [Resolve Conflict](#resolve-conflict)
- [Git Branch](#git-branch)
- [Conventional Commit](#conventional-commit)
- [Share & Apply Patch](#share--apply-patch)
- [Cherry Pick](#cherry-pick)

## Cara Pakai SourceTree

SourceTree adalah salah satu aplikasi GUI untuk Git yang mempermudah penggunaan Git dengan antarmuka yang intuitif. Berikut adalah langkah-langkah dasar dalam menggunakan SourceTree:

1. Install SourceTree dari situs resminya.
2. Buka SourceTree dan login ke akun GitHub atau GitLab Anda.
3. Clone repository dari remote ke lokal menggunakan SourceTree.
4. Lakukan commit, pull, push, dan operasi Git lainnya menggunakan antarmuka SourceTree yang mudah dipahami.

## Basic Git Commands

### Commit

Commit digunakan untuk menyimpan perubahan yang telah Anda lakukan pada proyek Anda dalam Git.

```bash
git add <file>             # Menambahkan file ke area staging
git commit -m "Message"   # Melakukan commit perubahan dengan pesan deskriptif
```

### Pull

Pull digunakan untuk mengambil pembaruan terbaru dari repositori remote ke repositori lokal Anda.

```bash
git pull origin <branch>   # Mengambil pembaruan dari sebuah branch remote
```

### Push

Push digunakan untuk mengunggah perubahan lokal Anda ke repositori remote.

```bash
git push origin <branch>   # Mengunggah commit ke sebuah branch remote
```

## Stash

Stash digunakan untuk menyimpan perubahan sementara yang belum siap untuk di-commit.

```bash
git stash                   # Menyimpan perubahan yang belum di-commit
git stash apply             # Mengaplikasikan perubahan yang telah disimpan
```

## Merge

Merge digunakan untuk menggabungkan perubahan dari branch lain ke branch yang sedang aktif.

```bash
git merge <branch>          # Menggabungkan perubahan dari branch lain ke branch yang sedang aktif
```

## Rebase

Rebase digunakan untuk memindahkan atau menggabungkan serangkaian commit ke commit basis yang baru.

```bash
git rebase <base>           # Rebase branch saat ini ke branch atau commit basis lainnya
```

## Resolve Conflict

Conflict resolution terjadi ketika Git tidak dapat secara otomatis menggabungkan perubahan. Intervensi manual diperlukan untuk menyelesaikan konflik.

```bash
# Setelah menyelesaikan konflik:
git add <resolved-file(s)>  # Menambahkan file yang telah diselesaikan
git rebase --continue       # Melanjutkan proses rebase
```

## Git Branch

Branching memungkinkan Anda untuk bekerja pada fitur atau perbaikan tanpa mempengaruhi kode basis utama.

```bash
git branch <branch-name>    # Membuat branch baru
git checkout <branch>       # Pindah ke branch lain
git branch -d <branch>      # Menghapus sebuah branch
```

## Conventional Commit

Conventional commit adalah praktik menulis pesan commit dengan format tertentu untuk memberikan riwayat perubahan yang jelas dan terstruktur. Format ini membantu dalam otomatisasi proses seperti pembuatan catatan rilis dan pembangunan otomatis. Berikut adalah struktur umum dari sebuah conventional commit:

```
<type>: <description>

<optional body>

<optional footer>
```

### Type

Type menentukan jenis perubahan yang terjadi. Beberapa jenis umum termasuk:

- **feat**: Penambahan fitur baru
- **fix**: Perbaikan bug
- **docs**: Perubahan pada dokumentasi
- **style**: Perubahan pada format kode, tanpa perubahan fungsional (spasi, indentasi, dll)
- **refactor**: Refaktorisasi kode yang tidak memperbaiki bug atau menambah fitur baru
- **test**: Penambahan atau perubahan pada kode tes
- **chore**: Pekerjaan terkait build, konfigurasi, atau alat lain yang tidak terkait dengan kode yang berjalan (misalnya: mengubah `.gitignore`)

### Description

Deskripsi harus singkat dan jelas menjelaskan perubahan yang dilakukan.

### Body

Body merupakan bagian opsional yang menjelaskan detail perubahan. Ini dapat mencakup konteks tambahan, alasan untuk perubahan, atau cara mengujinya.

### Footer

Footer juga opsional dan digunakan untuk menautkan commit dengan isu tertentu. Biasanya digunakan dalam integrasi otomatis, seperti untuk menutup isu di GitHub.

### Contoh

```
feat: Add login functionality

- Added login form component
- Implemented authentication API integration
```

```
fix: Fix null pointer exception in user service

- Check for null user object before accessing properties
- Added unit test to cover the fix
```

```
docs: Update installation guide

- Added instructions for setting up environment variables
- Clarified installation steps for macOS
```

```
style: Format code according to style guide

- Fixed indentation issues
- Removed trailing whitespace
```

```
chore: Update dependencies

- Updated packages to latest versions
- Removed deprecated dependencies
```

Dengan menggunakan conventional commit, tim pengembangan dapat dengan mudah memahami perubahan apa yang terjadi di dalam repositori, membantu dalam pemeliharaan kode yang lebih baik dan memfasilitasi proses otomatisasi.

## Share & Apply Patch

Patch adalah cara untuk berbagi perubahan antara repositori.

```bash
git format-patch <commit>   # Membuat file patch untuk sebuah commit
git apply <patch-file>      # Mengaplikasikan file patch
```

## Cherry Pick

Cherry-picking memungkinkan Anda untuk menerapkan commit tertentu dari satu branch ke branch lainnya.

```bash
git cherry-pick <commit>    # Menerapkan commit tertentu ke branch saat ini
```

## Additional Resources

- [Git Documentation](https://git-scm.com/doc)
- [Atlassian Git Tutorial](https://www.atlassian.com/git/tutorials)
- [GitHub Git Handbook](https://guides.github.com/introduction/git-handbook/)
