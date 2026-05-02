# Nix Darwin Kickstarter

Konfigurasi awal nix-darwin + home-manager + flakes yang ramah untuk pemula.

Tujuan utama repositori ini adalah membantu pemula memahami dasar-dasar penyiapan nix-darwin, sehingga mereka dapat dengan cepat memulai konfigurasi nix-darwin mereka sendiri.

Two template versions are available:

- [minimal](./minimal): Konfigurasi dasar yang berisi pengaturan penting untuk memulai nix-darwin. Aman untuk diterapkan ke sistem Anda.
- [rich-demo](./rich-demo): Demo yang lebih lengkap dengan banyak konfigurasi yang bisa dijadikan referensi. Namun, harap berhati-hati karena dapat **MENIMPA** konfigurasi sistem Anda. **JANGAN** menerapkannya langsung ke sistem Anda.

## Mengapa nix-darwin

Nix-darwin memudahkan pengelolaan konfigurasi sistem macOS dan dotfiles Anda secara deklaratif.
Anda dapat dengan mudah kembali ke konfigurasi sebelumnya, sehingga ini menjadi alat yang kuat untuk kustomisasi sistem.
Berbagi konfigurasi menjadi lebih mudah, dan mengelola beberapa host macOS juga menjadi simpel dengan nix-darwin.

## Contoh

Aktifkan TouchID untuk sudo hanya dengan satu baris:

![](./_img/nix-darwin-enable-touchid.webp)

Kustomisasi (hampir) semua pengaturan macOS melalui nix-darwin:

![](./_img/customize-your-macos.webp)

## Referensi

- [LnL7/nix-darwin](https://github.com/LnL7/nix-darwin)
- [macos-defaults](https://github.com/yannbertrand/macos-defaults)
- [ryan4yin/nix-config/modules/darwin](https://github.com/ryan4yin/nix-config/tree/main/modules/darwin)
