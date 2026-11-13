# DA2026_Dashboard_BuburDiaduk_Adeliya

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
