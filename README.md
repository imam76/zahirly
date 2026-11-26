# zahirly

Program yang menyerahkan tugas dari daftar tugas Zahirly ke AI (Claude Code) di komputermu.

Setelah dipasang, ia hidup sebagai layanan dan menyala sendiri saat komputer hidup. Ia mengambil tugas yang kamu serahkan ke AI dari aplikasi, mengerjakannya di folder yang kamu izinkan, lalu menulis hasilnya kembali ke tugas itu.

## Pasang

```bash
curl -fsSL https://github.com/imam76/zahirly/releases/latest/download/install.sh | bash
zahirly
```

Perintah pertama mengunduh satu berkas ke `~/.local/bin/zahirly`. Perintah kedua menanyakan slug perusahaan dan folder yang boleh dikerjakan AI, lalu menghidupkan layanannya. Di akhir ia menampilkan kunci runner: tempel kunci itu di halaman AI aplikasi.

| Sistem | Keadaan |
|---|---|
| Linux x64 | Tersedia |
| Windows | Lewat WSL2 dengan perintah yang sama (belum diuji) |
| macOS | Belum tersedia |

## Yang dibutuhkan

- Claude Code yang sudah login: `curl -fsSL https://claude.ai/install.sh | bash`, lalu jalankan `claude` sekali.
- `git`, untuk tugas di repo git.
- Di Linux, `bubblewrap` dan `socat`: `sudo apt-get install -y bubblewrap socat`.

`zahirly` memeriksa semuanya dan menyebut yang belum ada.

## Perintah

| Perintah | Gunanya |
|---|---|
| `zahirly` | Menyiapkan runner (kalau belum) dan menghidupkan layanannya |
| `zahirly status` | Keadaan layanan |
| `zahirly logs -f` | Catatan layanan |
| `zahirly stop`, `start`, `restart` | Menghentikan dan menghidupkan layanan |
| `zahirly setup` | Mengubah konfigurasi |
| `zahirly uninstall` | Melepas layanan |

## Memperbarui

Jalankan lagi perintah pasang, lalu `zahirly restart`.

## Melepas

Jalankan `zahirly uninstall`, lalu hapus `~/.local/bin/zahirly`. Konfigurasi ada di `~/.config/zahir-starter-runner/`, dan hasil job di `~/.local/share/zahir-starter-runner/`.
