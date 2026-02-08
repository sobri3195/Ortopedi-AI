# Ortopedi — PJI-Sentinel: AI Foto Luka + CRP untuk Deteksi Dini Infeksi Prostetik

## Ringkasan Konsep
**PJI-Sentinel** adalah sistem early warning untuk mendeteksi kemungkinan *periprosthetic joint infection* (PJI) pada pasien 0–90 hari pasca total hip arthroplasty (THA) atau total knee arthroplasty (TKA), dengan menggabungkan:
- Foto luka serial via smartphone,
- Tren biomarker inflamasi (CRP/ESR),
- Gejala harian (suhu tubuh, nyeri, keluarnya cairan luka, kemerahan),
- Data klinis dasar.

Sistem menghasilkan **skor risiko harian** dan **alert bertingkat** agar tim klinis dapat melakukan evaluasi lebih dini sebelum infeksi berkembang.

## PICO
### Population (P)
Pasien pasca THA/TKA dalam 0–90 hari pertama setelah operasi.

### Intervention (I)
Pemantauan multimodal berbasis AI:
- Analisis citra luka serial dari smartphone,
- Integrasi tren CRP/ESR,
- Integrasi suhu/nyeri dan gejala klinis harian,
- Dashboard risiko dan notifikasi dini untuk tim ortopedi.

### Comparison (C)
Follow-up standar:
- Kontrol klinis rutin,
- Pemeriksaan laboratorium/imaging ketika sudah ada kecurigaan klinis.

### Outcomes (O)
Utama:
- Waktu ke diagnosis PJI.

Sekunder:
- Proporsi pasien yang memerlukan DAIR atau reoperasi,
- *Length of stay* (LOS),
- Biaya perawatan,
- Outcome fungsional pasien.

## Tujuan Klinis
1. Menurunkan keterlambatan diagnosis PJI.
2. Meningkatkan peluang intervensi dini (mis. DAIR sebelum infeksi kronik).
3. Menurunkan beban biaya dan rawat inap ulang.
4. Mempertahankan hasil fungsional prostesis jangka menengah.

## Rancangan Implementasi (Pragmatic Clinical Workflow)
1. **Baseline sebelum pulang**
   - Foto luka standar,
   - CRP/ESR awal,
   - Edukasi pasien penggunaan aplikasi dan cara foto terstandar.
2. **Monitoring rumah (hari 1–90)**
   - Pasien unggah foto luka (mis. harian minggu 1–2, lalu 2–3x/minggu),
   - Input suhu/nyeri/gejala cepat via aplikasi,
   - Integrasi hasil CRP/ESR saat kontrol/lab terjadwal.
3. **Risk engine**
   - Model multimodal menghasilkan skor risiko (hijau-kuning-merah),
   - Alert merah memicu telekonsultasi/kunjungan dipercepat/lab lanjutan.
4. **Clinical adjudication**
   - Keputusan final tetap oleh dokter berdasarkan kriteria diagnostik PJI dan evaluasi klinis penuh.

## Definisi Outcome Operasional
- **Time-to-diagnosis PJI**: interval hari dari tanggal operasi hingga tanggal diagnosis PJI terkonfirmasi.
- **DAIR/reoperasi**: prosedur terkait infeksi dalam periode follow-up yang didefinisikan.
- **LOS**: total hari rawat inap terkait episode infeksi.
- **Biaya**: biaya langsung medis (kunjungan, lab, imaging, antibiotik, prosedur, rawat inap).
- **Outcome fungsional**: skor fungsi standar (mis. WOMAC/OKS/HHS) pada titik waktu yang disepakati.

## Metrik Evaluasi AI
- Sensitivitas, spesifisitas, PPV, NPV untuk deteksi dini PJI,
- AUROC/AUPRC dan kalibrasi,
- *Lead time gain* (berapa hari lebih cepat dibanding care standar),
- *False-alert burden* per 100 pasien,
- Dampak klinis bersih (*decision-curve analysis*).

## Kebutuhan Data Minimum
- Metadata pasien dan faktor risiko dasar,
- Foto luka serial berkualitas terstandar,
- Nilai CRP/ESR bertanggal,
- Catatan suhu/nyeri/gejala,
- Label outcome klinis teradjudikasi (PJI vs non-PJI) dan tanggal kejadian.

## Pertimbangan Etik dan Operasional
- Persetujuan pasien dan privasi data foto,
- Protokol keamanan data (enkripsi saat transit dan penyimpanan),
- Strategi mitigasi bias (warna kulit, variasi kamera/pencahayaan),
- Mekanisme *human-in-the-loop* agar AI sebagai pendukung keputusan, bukan pengganti klinisi.

## Hipotesis
Dibandingkan follow-up standar, penggunaan PJI-Sentinel akan mempercepat diagnosis PJI, menurunkan reoperasi mayor/LOS/biaya, dan memperbaiki outcome fungsional melalui intervensi lebih dini.
