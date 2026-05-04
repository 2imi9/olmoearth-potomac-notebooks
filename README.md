# OlmoEarth Potomac Sewage Spill (Jan 2026) Notebooks

Hands-on Jupyter notebooks for analyzing the January 19, 2026 Potomac Interceptor sewage spill event, using the [`OlmoEarth-v1-Potomac-Sewage-Spill-2026`](https://huggingface.co/datasets/BAIGroup/OlmoEarth-v1-Potomac-Sewage-Spill-2026) reference dataset on Hugging Face.

**Audience:** Civil & Environmental Engineering practitioners and researchers.

## Dataset

- **Source:** [`BAIGroup/OlmoEarth-v1-Potomac-Sewage-Spill-2026`](https://huggingface.co/datasets/BAIGroup/OlmoEarth-v1-Potomac-Sewage-Spill-2026)
- **Records:** 846 daily flow observations
- **Stations:** 8 USGS gauges along the Potomac corridor
- **Time:** 2025-12-01 → 2026-03-31
- **Variables:** discharge (cfs), station role, event phase, station metadata
- **Aux files:** 71-event operational log (DC Water + agencies), 4 AOI corridor polygons, monitoring station GeoJSON, spill-site metadata
- **License:** Apache-2.0

## Event Timeline (4 phases)

| Phase | Date Range | Description |
|---|---|---|
| `pre_spill_baseline` | 2025-12-01 → 2026-01-18 | Pre-spill reference window |
| `active_release` | 2026-01-19 → 2026-01-24 | Initial collapse, max untreated discharge |
| `bypass_period` | 2026-01-25 → 2026-03-14 | Bypass active, ongoing reduced impact |
| `post_recovery` | 2026-03-15 → 2026-03-31 | Repairs complete; recovery monitoring |

## Notebooks

| # | Notebook | Purpose |
|---|---|---|
| 01 | `01_demo.ipynb` | Flow timelines + event overlay + corridor map |
| 02 | `02_data_prep.ipynb` | End-to-end dataset reproduction from raw USGS + agency sources |
| 03 | `03_tutorial_embeddings.ipynb` | OlmoEarth embeddings on real Sentinel-1 RTC for per-AOI plume tracking |
| 04 | `04_analysis.ipynb` | Event-log + discharge-anomaly synthesis across the 4 phases |

## Quick Start

```bash
git clone https://github.com/2imi9/olmoearth-potomac-notebooks.git
cd olmoearth-potomac-notebooks
python -m venv .venv
source .venv/bin/activate    # Windows: .venv\Scripts\activate
pip install -r requirements.txt
jupyter notebook
```

Python 3.11 required.

## Citation

```bibtex
@dataset{qi2026potomac_spill,
  author    = {Qi, Ziming and BAI Group},
  title     = {OlmoEarth-v1-Potomac-Sewage-Spill-2026: Event Reference Dataset for Plume Tracking},
  year      = {2026},
  publisher = {Hugging Face},
  url       = {https://huggingface.co/datasets/2imi9/OlmoEarth-v1-Potomac-Sewage-Spill-2026}
}
```

## Source Data Attribution

All public domain or public reporting:

- **USGS NWIS** — [waterdata.usgs.gov](https://waterdata.usgs.gov/)
- **DC Water** — [Potomac Interceptor Collapse](https://www.dcwater.com/about-dc-water/media/potomac-interceptor-collapse)
- **Virginia Department of Health** — Potomac Sewage Spill News
- **Maryland DEP / MDE** — Potomac Interceptor Sewer Overflow
- **DC DOEE** — Potomac Interceptor Update and FAQs
- **Chesapeake Bay Program Data Hub** — [datahub.chesapeakebay.net](https://datahub.chesapeakebay.net/)

## Acknowledgments

This repository — notebooks, documentation, and scaffolding — was developed in collaboration with Claude Opus 4.7 (Anthropic).

## License

MIT for code in this repo · Apache-2.0 for the underlying dataset.
