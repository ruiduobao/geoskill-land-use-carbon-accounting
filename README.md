# geoskill-land-use-carbon-accounting

> Compute carbon stock changes, emissions/removals, and uncertainty from multi-temporal land cover data using IPCC Tier 1/2 carbon factors. Use when analyzing land use change carbon budgets, estimating CO2e emissions from deforestation, or generating carbon accounting reports.

See [SKILL.md](SKILL.md) for full usage, inputs and outputs.

## Quick start

```bash
# Synthetic demo mode (no input files needed)
python scripts/land_use_carbon_accounting.py --output-dir ./luca-output

# With input GeoTIFF land cover rasters
python scripts/land_use_carbon_accounting.py \
  --before-landcover ./data/before.tif \
  --after-landcover ./data/after.tif \
  --eco-zone subtropical \
  --pools BAG BBG SOC \
  --output-dir ./luca-output

# With custom carbon factors and Monte Carlo settings
python scripts/land_use_carbon_accounting.py \
  --before-landcover ./data/before.tif \
  --after-landcover ./data/after.tif \
  --eco-zone temperate \
  --pools BAG BBG DW LT SOC \
  --mc-iterations 5000 \
  --mc-seed 42 \
  --confidence 0.95 \
  --output-dir ./luca-output

# With bounding box for area computation
python scripts/land_use_carbon_accounting.py \
  --before-landcover ./data/before.tif \
  --after-landcover ./data/after.tif \
  --bbox 116.0 39.5 116.5 40.0 \
  --output-dir ./luca-output
```

## License

MIT
