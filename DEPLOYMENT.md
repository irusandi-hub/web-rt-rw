# Deployment & batas keamanan

## Vercel

Proyek ini adalah situs statis tanpa proses build atau dependensi npm. Hubungkan repository ke Vercel dengan Root Directory `./`; Framework Preset dapat menggunakan **Other**. Output dilayani dari root repository. File `vercel.json` memasang header keamanan dasar dan mencegah service worker tersimpan terlalu lama oleh cache HTTP.

Setiap perubahan di branch yang terhubung akan menghasilkan deployment Preview; perubahan pada branch Production yang dipilih di pengaturan Vercel akan menghasilkan deployment Production.

## Sebelum dipakai dengan data warga sungguhan

Versi saat ini hanya menyimpan data di localStorage browser. PIN panel bukan autentikasi server. Siapa pun yang memiliki akses ke perangkat/browser dapat memeriksa atau mengubah data lokal. Data tidak dibagikan atau disinkronkan ke perangkat lain.

Jangan menyimpan NIK, nomor KK, alamat lengkap, nomor telepon, atau catatan sensitif warga dalam deployment publik ini. Untuk penggunaan operasional bersama, bangun backend terpisah dengan:
- autentikasi individual dan otorisasi berbasis peran;
- database terpusat dengan kebijakan akses per RT/RW;
- validasi server-side dan audit log;
- backup terjadwal, retensi, dan prosedur pemulihan;
- persetujuan serta kebijakan privasi yang sesuai.

## PWA / cache

Service worker menggunakan nama cache berversi. Naikkan versi cache setiap kali mengubah aset inti agar perangkat pengguna mengambil versi aplikasi terbaru. Data localStorage tidak ikut dihapus saat cache aplikasi diperbarui.

## Kredit & lisensi

Pertahankan atribusi Maliki Saputra pada footer, header berkas, dan LICENSE sesuai syarat lisensi repository.
