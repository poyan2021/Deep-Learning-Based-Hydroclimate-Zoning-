# Deep Learning-Based Hydroclimate Zoning (AE + SOM Pipeline)

This repository provides a complete, reproducible framework for hydroclimate zoning built around actual evapotranspiration (ETa) dynamics. The architecture combines:

- Deep Autoencoder for nonlinear feature extraction
- Self-Organizing Map (SOM) for preserving spatial topology
- K-Means clustering for optimal zone delineation
- Köppen-Geiger classification for result validation
- GIS-based spatial analysis and mismatch detection

This code supports the following manuscript:

> *"Functional Hydroclimate Regionalization from Long-Term Evapotranspiration Records Using a Reproducible Autoencoder–SOM Framework"*

---

## What's different about this approach?

The framework is fully data-driven and moves away from the constraints of traditional zoning methods. In short:

- Long-term ETa time series are compressed into a compact latent space via deep autoencoder, letting the model learn hidden nonlinear relationships in the data
- Spatial topology is preserved through SOM, so geographic neighborhoods are reflected in the final clustering
- Hydroclimate zones are optimized directly in latent space
- A quantitative spatial comparison against Köppen-Geiger classes is performed
- Spatial mismatches are analyzed with uncertainty-aware diagnostics

---

## Processing Pipeline

Raw ETa data (monthly, 1980–2023)
        ↓
Quality control (ET-QCA: physical, statistical & temporal filters)
        ↓
Normalization (Min-Max scaling)
        ↓
Deep Autoencoder (528 → 256 → 64 → 3 latent features)
        ↓
Latent feature space extraction
        ↓
Self-Organizing Map (20×20 Gaussian SOM)
        ↓
Codebook clustering (K-Means with optimal k selection)
        ↓
Hydroclimate zone delineation
        ↓
Validation against Köppen-Geiger climate classes
        ↓
GIS mapping & spatial mismatch analysis
