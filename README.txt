Tasbih Go — versi 21 (Penghitung dzikir real-time terhubung)

Yang diperbarui:
- Supabase Project URL dan Publishable key telah dimasukkan ke aplikasi.
- Indikator “X orang sedang berdzikir” menggunakan Supabase Realtime Presence.
- Sesi menjadi aktif setelah pengguna mengetuk tombol hitung atau menyentuh/ menggeser manik.
- Sesi dihitung aktif selama dua menit sejak aktivitas dzikir terakhir; setelah itu ditandai tidak aktif.
- Tidak mengirim nama, email, atau data identitas. Hanya status aplikasi, boolean aktivitas, dan timestamp aktivitas.
- Semua audio, logo, favicon, ikon aplikasi, dan font dari versi sebelumnya tetap disertakan.

PENTING:
- Nilai yang ditanamkan hanya Project URL dan Publishable key, yang memang ditujukan untuk koneksi browser. Jangan pernah menambahkan Secret key atau service_role key ke HTML publik.
- Karena ini file HTML statis, nilai NEXT_PUBLIC_ tidak perlu didefinisikan sebagai environment variable build; konfigurasi sudah langsung disetel pada script.
- Penghitung akan berfungsi jika Supabase Realtime aktif dan project dapat diakses.

Cara memakai:
1. Unggah seluruh isi folder/ZIP ini ke root proyek Vercel, menimpa versi lama.
2. Deploy/redeploy di Vercel.
3. Buka website pada dua browser atau perangkat berbeda.
4. Ketuk tombol dzikir pada masing-masing perangkat. Angka “X orang sedang berdzikir” akan tersinkron setelah koneksi Realtime tersambung.

Definisi hitungan:
- Angka menghitung sesi browser yang baru melakukan hitungan dzikir dalam dua menit terakhir, bukan memverifikasi bahwa seseorang benar-benar sedang mengucapkan dzikir.
- Setiap tab/perangkat dihitung sebagai sesi terpisah.
- Saat koneksi terputus atau tab ditutup, jumlah dapat memerlukan beberapa saat untuk menyinkronkan status leave.

Jika status menunjukkan koneksi tidak tersedia:
- Pastikan project Supabase dalam keadaan aktif.
- Pastikan Realtime tidak dinonaktifkan/dibatasi.
- Periksa Console browser untuk pesan jaringan atau konfigurasi.

Dokumentasi:
https://supabase.com/docs/guides/realtime/presence
https://supabase.com/docs/guides/realtime/limits
