# Changelog — mybrolabs Voice Studio

Versi terbaru di atas. Download: [Releases](https://github.com/mybrolabs/voice-studio/releases/latest).

## v0.9.2 — 2026-11-01 · rilis publik pertama

**Fitur utama**
- 🎙️ **Voice Conversion**: ubah suara rekaman ke suara target, intonasi & timing ngikut sumber.
  🎵 **Pertahankan musik latar**: vokal dipisah, diganti, digabung lagi, dengan atur volume + ducking.
- 🗣️ **Voice Clone TTS Bahasa Indonesia** (+ English). Teks panjang otomatis dipecah dan dapet subtitle SRT.
- 🎬 **Dialog / short film** 2–6 speaker: audio full, file per baris, subtitle SRT, regen per baris, buka job lama, pilih
  take manual.
- 🎯 **Multi-take**: render beberapa kali, otomatis milih yang paling mirip & paling jelas. Ada perkiraan waktu render.

**Referensi suara**
- ✨ **Cari bagian terbaik** dari rekaman panjang.
- 🧹 **Bersihin referensi**: pisah suara orang dari musik / suara latar, plus download stem musiknya.
- 🎧 **Referensi yang dipakai**: player yang muter **potongan persis** yang dipakai model, langsung ikut berubah habis
  *Pakai potongan ini*, *Mulai dari detik*, atau ✨. Kandidat yang aktif ditandai **"✓ Dipakai"**. Rekaman asli tetap utuh.
- Badge kualitas referensi (durasi, noise, dll.) + saran kalau perlu dibersihin.
- *Mulai dari detik* buat milih bagian rekaman, library suara buat nyimpen referensi favorit.

**Teks & naskah**
- 📖 Kamus pengucapan (tab Kamus) + normalisasi angka, Rupiah, jam dan tanggal.
- Tag non-verbal (`[laughter]`, `[sigh]`, …), jeda `<pause=…>` dan bahasa `<lang=en>`.
- 📋 Tombol *Salin prompt untuk AI* + skill Claude buat nulis naskah dialog.

**Install, update & pemakaian**
- Installer sekali klik (`install.bat`): cek GPU + driver, pasang semua yang dibutuhin di dalam folder app, download
  model opsional (bisa dilanjut kalau putus). Dijalanin ulang = mode repair.
- `install.bat` & `update.bat` **tanpa PowerShell**, dan `update.bat` **nggak pernah nimpa dirinya sendiri** → jauh lebih
  jarang dicurigai antivirus. README punya bagian **"Antivirus nge-block?"**.
- `update.bat` buat update ke versi berikutnya tanpa download model ulang. Nolak jalan kalau app masih kebuka. Model,
  hasil render, library suara, setting dan kamus pengucapan nggak disentuh. Langkahnya di `CARA_UPDATE.txt` (ikut di zip).
- `run.bat` buka browser otomatis. Port 7860 kepake → otomatis pindah ke port lain.
- Tombol 🧹 Unload model buat ngosongin VRAM.
