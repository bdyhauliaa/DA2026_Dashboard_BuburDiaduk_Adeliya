# AirQualityHealth — DA Gelar Rasa 2026

Repository ini berisi proses **preprocessing** dan **EDA** untuk dashboard AirQualityHealth.

> Dataset bersifat sintetis. Analisis bersifat asosiatif, bukan kausal.

## Isi Repository

```text
notebooks/
├─ 01_preprocessing.ipynb
└─ 02_eda.ipynb
data/
├─ fact_air_quality.parquet
├─ fact_health.parquet
├─ dim_date.csv
├─ dim_time.csv
├─ dim_site.csv
├─ dim_sensor.csv
└─ dim_hospital.csv
requirements.txt
```

## Menjalankan

```powershell
pip install -r requirements.txt
jupyter lab
```

- `02_eda.ipynb` memakai data yang disertakan dan membuat `figures/` serta `data/eda_summary/` secara lokal.
- `01_preprocessing.ipynb` memerlukan data mentah dari panitia di `data/raw/`; data mentah tidak disertakan.

## Catatan

- Data sintetis; hasil bukan kondisi aktual Indonesia.
- Oktober 2026 hanya mencakup 1–14 Oktober.
- Angka kesehatan adalah volume kunjungan/rawat inap, bukan prevalensi.
