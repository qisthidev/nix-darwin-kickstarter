# Nix Darwin Kickstarter

Konfigurasi awal nix-darwin + home-manager + flakes yang ramah untuk pemula.

Tujuan utama dari repositori ini adalah untuk membantu pemula memahami pengaturan dasar nix-darwin, sehingga mereka dapat dengan cepat memulai konfigurasi nix-darwin mereka sendiri.

Dua versi template tersedia:

- [minimal](./minimal): Konfigurasi dasar yang berisi pengaturan penting untuk memulai nix-darwin. Dapat digunakan dengan aman pada sistem Anda.
- [rich-demo](./rich-demo): Demo lengkap dengan banyak konfigurasi yang dapat dijadikan referensi untuk pengaturan Anda. Namun, berhati-hatilah karena mungkin **MENIMPA** konfigurasi sistem Anda. **JANGAN** terapkan langsung ke sistem Anda.

## Mengapa nix-darwin

Nix-darwin memfasilitasi pengelolaan konfigurasi sistem macOS dan dotfiles Anda secara deklaratif.
Anda dapat dengan mudah kembali ke konfigurasi sebelumnya, menjadikannya alat yang kuat untuk kustomisasi sistem.
Berbagi konfigurasi menjadi mudah, dan mengelola beberapa host macOS sangat mudah dengan nix-darwin.

## Tampilan

Aktifkan TouchID untuk sudo hanya dengan satu baris:

![](./_img/nix-darwin-enable-touchid.webp)

Kustomisasi (Hampir) semua pengaturan macOS Anda melalui nix-darwin:

![](./_img/customize-your-macos.webp)

## Referensi

- [LnL7/nix-darwin](https://github.com/LnL7/nix-darwin)
- [macos-defaults](https://github.com/yannbertrand/macos-defaults)
- [ryan4yin/nix-config/modules/darwin](https://github.com/ryan4yin/nix-config/tree/main/modules/darwin)

