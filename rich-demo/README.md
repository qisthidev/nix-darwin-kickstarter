# Nix Darwin Kickstarter - Rich Demo

 Demo lengkap dengan banyak konfigurasi yang dapat dijadikan referensi untuk pengaturan Anda. Namun, berhati-hatilah karena mungkin **MENIMPA** konfigurasi sistem Anda. **JANGAN** terapkan langsung ke sistem Anda.


## Cara Menggunakan

1. Mulai perjalanan nix-darwin Anda dengan mengikuti konfigurasi [minimal](../minimal).
2. Baca semua file dalam repositori ini, dan pahami apa fungsinya.
   1. Jika Anda kesulitan memahami, [ryan4yin/nixos-and-flakes-book](https://github.com/ryan4yin/nixos-and-flakes-book) adalah sumber yang baik untuk mempelajari nix dan flakes.
3. Salin dan SESUAIKAN konfigurasi yang Anda butuhkan dari demo ini ke konfigurasi Anda sendiri.
4. Jalankan `just darwin` di root konfigurasi nix Anda untuk menerapkan konfigurasi Anda.

Perintah Just lainnya:

```bash
# Lihat semua perintah yang tersedia
just

# Bersihkan nix store
just clean
just gc
```

## Struktur Konfigurasi

Struktur konfigurasi nix-darwin Anda saat ini seharusnya sebagai berikut:

```bash
› tree
.
├── flake.lock  # file lock yang dihasilkan oleh nix, Anda dapat mengabaikannya untuk saat ini
├── flake.nix   # titik masuk konfigurasi nix Anda, Anda perlu menambahkan hostname Anda di sini
├── home        # folder konfigurasi home-manager, membantu Anda mengelola dotfiles & aplikasi tingkat pengguna.
│   ├── shell.nix     # kustomisasi dotfiles zsh
│   ├── core.nix     # aplikasi tingkat pengguna dari nixpkgs (repositori paket resmi nix)
│   ├── default.nix  # titik masuk home-manager, Anda perlu mengimpor semua file nix lainnya di folder home di sini.
│   ├── git.nix      # kustomisasi dotfiles git
│   └── starship.nix  # kustomisasi dotfiles starship
├── Justfile    # Justfile untuk menyederhanakan alur kerja nix-darwin Anda.
├── README.md
├── modules     # folder yang berisi semua file konfigurasi nix-darwin Anda
│   ├── apps.nix        # berisi semua aplikasi homebrew & nix Anda (baik GUI & CLI)
│   ├── host-users.nix  # mendefinisikan hostname & semua pengguna sistem Anda
│   ├── nix-core.nix    # konfigurasi inti nix, Anda dapat mengabaikannya untuk saat ini
│   └── system.nix      # mendefinisikan konfigurasi sistem macOS Anda (seperti dock, trackpad, keyboard, finder, loginwindow, dll.)
└── scripts
    └── darwin_set_proxy.py  # skrip untuk mengatur proxy http untuk nix & homebrew.
```

## Catatan tentang Proxy Jaringan

Jika Anda berada di lingkungan jaringan yang memerlukan proxy (seperti China), Anda mungkin perlu mengatur proxy untuk nix dan homebrew.

File terkait:

- [rich-demo/scripts/darwin_set_proxy.py](/rich-demo/scripts/darwin_set_proxy.py)
- [rich-demo/Justfile](/rich-demo/Justfile)
- [rich-demo - pengaturan mirror homebrew](/rich-demo/modules/homebrew-mirror.nix)

