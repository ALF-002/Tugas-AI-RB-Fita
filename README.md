# Studi Ablasi RNN, LSTM, GRU vs ANN untuk Prediksi Trafik Seluler Milan

Tugas Workshop Deep Learning — Teknik Telekomunikasi ITERA.

<!-- Ganti seluruh isian bertanda [ ... ] di bawah. Hapus komentar ini. -->

## Kelompok

| Peran | Nama | NIM |
|---|---|---|
| Ketua | Alfita Eryani Nugroho | 124400002 |
| Anggota | Octavia Sesilia Malau | 124400038 |
| Anggota | Fitria Oktavianti | 124400058 |

- **Kelas:** RB
- **Lokasi kelompok:** 2 — Università Bocconi
- **Laporan:** `laporan-latex/main.pdf`

## Cara Menjalankan

**Prasyarat:** Python 3.12+, [Git](https://git-scm.com/), dan [uv](https://docs.astral.sh/uv/).

```bash
git clone https://github.com/mctosima/dl-workshop.git
cd Tugas-AI-RB-Fita
uv sync
uv run jupyter lab
```

Buka `tugas_ablasi.ipynb`, lalu:

1. Pastikan `LOKASI_KELOMPOK = 2` (Universita Bocconi) di sel pertama.
2. Pastikan `CEPAT = False` untuk hasil akhir (`CEPAT = True` hanya untuk uji coba kode).
3. Jalankan semua sel dari atas ke bawah (**Kernel → Restart Kernel and Run All Cells**).

> **Windows:** jika `uv` tidak dikenali, jalankan dengan awalan `python -m uv` (contoh: `python -m uv sync`).

Perangkat yang kami pakai: Laptop CPU Intel i3, Jupyter Notebook Lab, total waktu training: 182.3 menit.

## Ringkasan Hasil


## Struktur

```
tugas_ablasi.ipynb      notebook eksperimen (di-commit beserta output)
data/                   data trafik per jam (Duomo + 10 lokasi tugas)
hasil/                  CSV seluruh run, tabel, dan grafik
laporan-latex/          sumber laporan + PDF
```

## Data

Telecom Italia Big Data Challenge (Barlacchi dkk., 2015, *Scientific Data*, lisensi ODbL), versi per jam dari Zhang dkk. (INFOCOM 2021). Disiapkan oleh pengajar di repo [mctosima/dl-workshop](https://github.com/mctosima/dl-workshop).
