# Methodology — openLCA extension

## Functional unit
1 m² of structural panel for wall/roof sheathing.

## Boundary
Cradle-to-gate screening: perennial-grass production → road transport → panel manufacturing.

## openLCA implementation
- openLCA 2.6
- BAFU 2026 v1.1 background inventory
- IPCC 2021 GWP100
- Reference output: 1 m² structural panel

## Base foreground assumptions
See `outputs/openlca_base_case_inventory.csv`.

## Base result
4.38938 kg CO₂e/m² (IPCC 2021 GWP100).

## Contribution structure
- Generic phenolic-resin proxy: 70.87%
- U.S. grid electricity: 19.24%
- Grass production + transport: 9.89%

## Sensitivity
Resin proxy loading:
- 0.4 kg/m² → 2.83394 kg CO₂e/m²
- 0.8 kg/m² → 4.38938 kg CO₂e/m²
- 1.2 kg/m² → 5.94483 kg CO₂e/m²

## Interpretation constraint
The resin process is an impact proxy only and is not intended to represent Plantd's disclosed formaldehyde-free resin chemistry. The current model is a methodological screening case, not a verified Plantd product footprint or comparative assertion against OSB.
