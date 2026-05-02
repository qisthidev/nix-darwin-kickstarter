# Nix Darwin Kickstarter - Minimal

 Konfigurasi dasar yang berisi pengaturan penting untuk memulai nix-darwin. Dapat digunakan dengan aman pada sistem Anda.

## Cara Menggunakan

1. Instal pengelola paket Nix melalui [Nix Official](https://nixos.org/download.html#nix-install-macos) atau [DeterminateSystems/nix-installer](https://github.com/DeterminateSystems/nix-installer).
2. Baca semua file dalam folder `minimal` ini, dan pahami apa fungsinya.
   1. Jika Anda kesulitan memahami, [ryan4yin/nixos-and-flakes-book](https://github.com/ryan4yin/nixos-and-flakes-book) adalah sumber yang baik untuk mempelajari nix dan flakes.
3. Instal Homebrew, lihat <https://brew.sh/>
   1. Homebrew diperlukan untuk menginstal sebagian besar aplikasi GUI, aplikasi App Store, dan beberapa aplikasi CLI yang tidak tersedia di repositori paket nix `nixpkgs`.
4. Cari `TODO` di folder `minimal` ini, dan selesaikan semua TODO.
5. Jalankan perintah berikut di root konfigurasi nix Anda untuk memulai perjalanan nix-darwin Anda (silakan ubah `hostname` menjadi hostname Anda):
   ```bash
	nix build .#darwinConfigurations.hostname.system \
		--extra-experimental-features 'nix-command flakes'

	sudo -E ./result/sw/bin/darwin-rebuild switch --flake .#hostname
   ```

Untuk menyederhanakan perintah, tambahkan konten berikut dengan membuat `Makefile` di root konfigurasi nix Anda:

```makefile
# silakan ubah 'hostname' menjadi hostname Anda
deploy:
	nix build .#darwinConfigurations.hostname.system \
	   --extra-experimental-features 'nix-command flakes'

	sudo -E ./result/sw/bin/darwin-rebuild switch --flake .#hostname
```

Kemudian Anda dapat menjalankan `make deploy` di root konfigurasi nix Anda untuk menerapkan konfigurasi Anda.

## Struktur Konfigurasi

Struktur konfigurasi nix-darwin Anda saat ini seharusnya sebagai berikut:

```bash
› tree
.
├── flake.lock  # file lock yang dihasilkan oleh nix, Anda dapat mengabaikannya untuk saat ini
├── flake.nix   # titik masuk konfigurasi nix Anda, Anda perlu menambahkan hostname Anda di sini
├── modules     # folder yang berisi semua file konfigurasi nix-darwin Anda
│   ├── apps.nix        # berisi semua aplikasi homebrew & nix Anda (baik GUI & CLI)
│   ├── host-users.nix  # mendefinisikan hostname & semua pengguna sistem Anda
│   ├── nix-core.nix    # konfigurasi inti nix, Anda dapat mengabaikannya untuk saat ini
│   └── system.nix      # mendefinisikan konfigurasi sistem macOS Anda (seperti dock, trackpad, keyboard, finder, loginwindow, dll.)
└── README.md
```


## Catatan tentang Proxy Jaringan

Jika Anda berada di lingkungan jaringan yang memerlukan proxy (seperti China), Anda mungkin perlu mengatur proxy untuk nix dan homebrew.

Silakan lihat folder `rich-demo` untuk detail lebih lanjut:

- [rich-demo/scripts/darwin_set_proxy.py](/rich-demo/scripts/darwin_set_proxy.py)
- [rich-demo/Makefile](/rich-demo/Makefile)
- [rich-demo - pengaturan mirror homebrew](/rich-demo/modules/homebrew-mirror.nix)

