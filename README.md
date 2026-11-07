# mybrolabs Voice Studio

**Voice cloning, TTS Bahasa Indonesia & dialog multi-speaker. Gratis, offline, jalan di PC lu sendiri (GPU NVIDIA).**
Nggak ada upload ke server mana pun, semua diproses di komputer lu.

Dibikin oleh **mybrolabs**. Follow IG **[@realtoonai](https://instagram.com/realtoonai)** buat tutorial dan tools AI lainnya.

> Repo ini cuma buat **halaman download, catatan rilis & dokumen**. File app-nya ada di
> [**Releases**](https://github.com/mybrolabs/voice-studio/releases/latest).

---

## Bisa ngapain aja?

- 🎙️ **Voice Conversion (VC)**: rekaman lu + suara target, hasilnya suara target ngucapin isi rekaman lu. Intonasi dan
  timing ngikut rekaman asli.
  - 🎵 **Pertahankan musik latar**: vokal dipisah dari musik, diganti suaranya, lalu digabung lagi.
- 🗣️ **Voice Clone TTS Bahasa Indonesia**: cukup referensi suara 6–10 detik + teks, jadi suara itu ngomong teks lu.
  Teks panjang otomatis dipecah + dapet subtitle SRT. English juga bisa.
- 🎬 **Dialog / short film**: 2–6 speaker, naskah format `NAMA: teks`. Hasilnya audio full, file per baris dan subtitle
  **SRT**. Satu baris jelek? Regen baris itu aja.
- 📖 **Kamus pengucapan**: atur cara baca kata yang sering salah (nama, istilah, singkatan). Angka, Rupiah, jam dan
  tanggal otomatis dibaca bener.
- ✨ **Cari bagian terbaik**: punya rekaman panjang? App nyariin potongan paling bagus buat dijadiin referensi.
- 🎯 **Multi-take**: render beberapa kali, otomatis dipilih yang paling mirip dan paling jelas.
- 🧹 **Bersihin referensi**: pisahin suara orang dari musik / suara latar di rekaman referensi.
- 🏷️ Tag non-verbal (`[laughter]`, `[sigh]`, …), jeda `<pause=0.5>` dan bahasa `<lang=en>` di dalam teks.
- 📋 **Nulis naskah pakai AI**: salin prompt siap pakai buat ChatGPT / Claude / Gemini langsung dari app.

## Syarat PC

| | Minimal | Disarankan |
|---|---|---|
| OS | Windows 10 / 11 64-bit | |
| GPU | **NVIDIA, VRAM 8 GB** | 12 GB ke atas |
| Driver NVIDIA | 528 | **570 ke atas** |
| Disk kosong | **±20 GB** (app + model AI ±9 GB + hasil) | SSD |
| Internet | Waktu install + download model (sekali aja) | |

**Nggak perlu** install Python, Git atau CUDA sendiri, semuanya dipasang di dalam folder app dan nggak ganggu program
lain. GPU AMD / Intel / Mac belum didukung.

## Download

👉 **[Download versi terbaru di Releases](https://github.com/mybrolabs/voice-studio/releases/latest)**
(file `mybrolabs-VoiceStudio-vX.Y.Z.zip`).

> ⚠️ **Download cuma dari mybrolabs.com atau repo ini.** File dari tempat lain (re-upload, mirror, grup) bisa udah
> diutak-atik dan nggak dijamin aman.

**Cek keaslian file (opsional tapi disarankan).** Buka Command Prompt di folder tempat zip-nya, jalanin:

```
certutil -hashfile mybrolabs-VoiceStudio-v0.9.2.zip SHA256
```

Hasilnya harus **sama persis** dengan isi file `.sha256` / angka SHA256 di halaman rilis. Beda? Jangan dipakai, download
ulang dari link resmi.

## Install (3 langkah)

1. **Extract** zip-nya (klik kanan → *Extract All*) ke folder dengan **path pendek**, mis. `D:\VoiceStudio`.
   Jangan dijalanin langsung dari dalam zip.
2. Buka folder `mybrolabs-VoiceStudio`, **double-click `install.bat`**.
   - Muncul *"Windows protected your PC"*? Klik **More info** → **Run anyway** (file .bat dari internet emang selalu
     ditanya kayak gini).
   - Installer ngecek GPU + driver, masang Python, PyTorch dan semua library di dalam folder app.
   - Di akhir ditanya **"Download model sekarang?"** (±9 GB). **Y** = disarankan. **N** = model didownload otomatis pas
     fiturnya pertama dipakai. Koneksi putus? Jalanin `install.bat` lagi, download lanjut dari terakhir.
3. **Double-click `run.bat`**. Browser kebuka sendiri ke `http://127.0.0.1:7860`. Tutup jendela hitam = app mati.

Total **±8–15 menit**, tergantung kecepatan internet.

Lebih gampang lihat videonya: [Cara install](https://www.youtube.com/watch?v=yyx6Ztqo06c)

## Update ke versi baru

Update cuma ganti kode app. Model, hasil render, library suara, setting dan kamus lu **tetap aman**, nggak perlu download
model lagi.

1. Download zip versi baru. **Jangan di-extract**, taruh di folder app (sebelahan `update.bat`) atau folder Downloads.
2. Tutup app dulu (tutup jendela hitam `run.bat`).
3. **Double-click `update.bat`** (atau drag-and-drop zip-nya ke `update.bat`). Biasanya selesai < 1 menit.
4. Jalanin `run.bat`, cek footer app udah versi baru.

Langkah lengkap + troubleshooting: **`CARA_UPDATE.txt`** (ada di zip dan di halaman rilis).

## Antivirus nge-block?

`install.bat` / `update.bat` cuma script teks biasa (bisa lu buka pakai Notepad) yang masang Python + library ke folder
app. Antivirus yang nilai dari **perilaku** (mis. Kaspersky System Watcher, nama deteksi kayak
`PDM:Trojan.Win32.Generic`) kadang curiga sama script yang download & ngopi banyak file. Itu **false positive**.
Script-nya sengaja dibikin "kalem" (tanpa PowerShell, nggak ngubah dirinya sendiri), tapi kalau masih kena:

1. **Pulihin file** dari karantina antivirus (Kaspersky: *Detections / Quarantine* → *Restore*;
   Windows Defender: *Windows Security* → *Virus & threat protection* → *Protection history* → *Allow* / *Restore*).
2. **Kasih pengecualian buat folder app** (mis. `D:\VoiceStudio\mybrolabs-VoiceStudio`):
   - **Kaspersky**: *Settings* (ikon gerigi di bawah) → *Security settings* → *Exclusions and actions on object
     detection* (versi lama: *Threats and exclusions*) → *Manage exclusions* → *Add* → *Browse* pilih folder app →
     biarin semua komponen proteksi tercentang → status *Active* → *Add*.
   - **Windows Defender**: *Windows Security* → *Virus & threat protection* → *Manage settings* → *Exclusions* →
     *Add or remove exclusions* → *Add an exclusion* → *Folder* → pilih folder app.
3. Jalanin lagi `install.bat` / `update.bat`.
4. **Bantu laporin false positive** biar user lain nggak kena:
   - Kaspersky: upload file-nya di [opentip.kaspersky.com](https://opentip.kaspersky.com/), kalau hasilnya merah klik
     *Submit to reanalyze*.
   - Microsoft Defender: [microsoft.com/wdsi/filesubmission](https://www.microsoft.com/en-us/wdsi/filesubmission),
     pilih *Home customer* → *Incorrectly detected as malware*.

Nama menu bisa beda dikit tergantung versi antivirus. Jangan matiin antivirus total, cukup pengecualian folder app.

## Lisensi (singkat)

- **App-nya gratis** buat keperluan pribadi maupun kerja. **Dilarang dijual, di-re-upload / mirror, atau dikemas ulang**
  tanpa izin tertulis dari mybrolabs. Mau bagiin? Bagiin link resminya aja. Detail: [`LICENSE.txt`](LICENSE.txt).
- **OmniVoice** (TTS & Dialog Bahasa Indonesia): bobot model **CC-BY-NC 4.0** → hasil TTS / Dialog **non-komersial**
  (belajar, eksperimen, konten pribadi yang nggak dimonetisasi).
- **Chatterbox** (Voice Conversion, TTS English): **MIT** → **Voice Conversion boleh komersial**. Buat job klien / iklan:
  rekam suara lu sendiri ngomongin naskahnya, terus ubah pakai tab Voice Conversion. **Suara target juga harus suara lu
  sendiri atau orang yang udah kasih izin.**
- Built with Higgs Materials licensed from Boson AI USA, Inc.
- **Pakai suara orang lain hanya dengan izin orangnya.** Jangan buat nipu, fitnah, scam atau konten yang menyesatkan.
- Lisensi lengkap semua model & library: [`NOTICE.txt`](NOTICE.txt).

## Video tutorial

- 📺 Cara install: https://www.youtube.com/watch?v=yyx6Ztqo06c
- 📺 Demo fitur & cara pakai: https://youtu.be/0Q9tXk08b-E
- ▶️ Playlist lengkap: https://www.youtube.com/playlist?list=PLFZ7AUSU9gAU

## Kontak & bantuan

Ada masalah? Kirim screenshot jendela hitam + file `logs\install.log` ke IG **[@realtoonai](https://instagram.com/realtoonai)**.

---

Riwayat versi: [`CHANGELOG.md`](CHANGELOG.md)
