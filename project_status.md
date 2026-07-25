# Status Proyek Remote Camera

## Fitur Saat Ini
- Koneksi WebRTC stabil (Target menelpon Viewer).
- Penyamaran YouTube di sisi Target dengan pop-up "LANJUT NONTON YA/NO".
- Support parameter URL `?v=ID_VIDEO` untuk mengganti video YouTube.
- Menggunakan server STUN Google untuk stabilitas.

## Fitur yang Akan Ditambahkan
1. **Perekaman Video**: Di sisi Viewer untuk menyimpan stream.
2. **Switch Camera**: Kontrol dari Viewer untuk mengganti kamera Target (depan/belakang).
3. **YouTube Link Cloner**: Input di Viewer untuk menentukan video penyamaran dengan mudah.

## Struktur File
- `viewer-enhanced.html`: Interface pengontrol (Viewer).
- `target-enhanced.html`: Interface kamera (Target).
- `README.md`: Dokumentasi penggunaan.
