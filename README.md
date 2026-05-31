# Deep Learning-Based Hydroclimate Zoning (AE pipeline)

Code and reproducibility materials for the manuscript:
"Deep Learning-Based Hydroclimate Zoning Informed by Evapotranspiration Patterns and Compared with Köppen Classification"
For full reproducibility instructions, see `docs/reproducibility.md`.

## How to run (Google Colab)
1. Open `notebooks/autoencoder_pipeline.ipynb` in Colab.
2. Upload a `.csv` file when prompted.
3. Choose `latent_dim` when asked.
4. Outputs will be written to `outputs_YYYYMMDD-HHMMSS/`.

## Input data format
- Rows: samples/pixels
- Columns: features (e.g., years or variables)
- Missing values: allowed; imputed with column mean

## Outputs
- `latent_features.csv`
- `training_history.csv`
- `metrics_summary.json`
- Figures: training curve, latent visualizations, reconstructions
- Models: `models/autoencoder.keras`, `models/encoder.keras`

## License

This project is licensed under the MIT License. See `LICENSE`.

