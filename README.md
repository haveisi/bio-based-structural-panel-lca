# Plantd vs. OSB: Screening LCA & Product Carbon Methodology

**Bio-based building materials | Structural panels | Screening LCA | Excel | Python | openLCA-ready workflow**

## Overview

This project develops a transparent and reproducible **screening-level life cycle assessment workflow** for comparing a perennial-grass structural panel, using Plantd as a public case-study reference, with conventional oriented strand board (OSB).

The project was originally developed for **teaching, methodological exploration, and LCA workflow development**. It is not a commissioned Plantd study, and it does not represent verified Plantd environmental performance.

The purpose is to demonstrate how incomplete public sustainability and technical information can be structured into an LCA framework, how data gaps should be handled explicitly, and what primary information would be required to move toward a decision-grade product LCA or Environmental Product Declaration (EPD).

---

## Core Question

**How should a perennial-grass structural panel be compared with conventional OSB on a functionally equivalent and methodologically defensible basis?**

The project focuses less on producing a definitive carbon number and more on building the analytical structure needed to answer that question rigorously.

---

## Functional Unit

**1 m² of structural panel used for wall or roof sheathing**, assuming equivalent functional performance.

A full comparative LCA would require confirmation that the compared products provide equivalent structural performance, thickness, service function, and application.

---

## System Boundary

**Cradle-to-gate screening boundary**

The model is structured around:

* biomass production
* biomass transportation
* binder or resin inputs
* manufacturing electricity
* thermal energy / drying / pressing
* production yield and process losses
* packaging
* finished structural panel

The current screening model does not represent a complete product life cycle.

---

## Methodological Framework

The project follows the general logic of:

* ISO 14040: Life Cycle Assessment principles and framework
* ISO 14044: LCA requirements and guidance
* ISO 14025: Type III environmental declarations
* ISO 21930: Environmental declarations for building products

These standards are used as methodological references only. This project has not undergone third-party review or verification.

---

## Data Sources

The screening workflow draws from:

* publicly available Plantd technical and product information
* published LCA literature on bio-based structural panels
* conventional wood-panel and OSB studies
* public construction-material environmental data
* illustrative assumptions used to demonstrate the modeling workflow

### Important Data Classification

Inputs are separated conceptually into:

**Primary / company-specific data**
Data directly supplied by a manufacturer.

**Secondary data**
Published literature, EPDs, databases, or other external sources.

**Illustrative assumptions**
Values introduced only to demonstrate the model structure when required information is unavailable.

The current model relies substantially on secondary information and illustrative assumptions because a complete Plantd life-cycle inventory is not publicly available.

---

## Analytical Workflow

### 1. Data Extraction

Technical information and literature inputs are compiled into a structured Excel dataset.

### 2. Data Cleaning and Structuring

`src/02_clean_openlca_inputs.py`

The workflow:

* standardizes variable names
* separates input categories
* flags assumptions and missing data
* prepares modeling inputs
* exports a cleaned dataset

### 3. Screening Model Development

`src/03_build_screening_model.py`

The script:

* establishes illustrative OSB benchmark scenarios
* creates illustrative perennial-grass panel scenarios
* calculates comparative screening outputs
* supports sensitivity analysis

### 4. Visualization

`src/04_make_chart.py`

Creates comparative figures for interpreting screening scenarios.

### 5. Foreground LCA Structure

`src/05_build_lca_structure.py`

The workflow translates the extracted information into simplified LCA-style process flows that can support later implementation in professional LCA software.

---

## Illustrative Screening Scenarios

**The values below are hypothetical scenario values used to demonstrate the analytical workflow. They are not Plantd primary-data results and should not be interpreted as estimates or claims regarding Plantd's actual environmental performance.**

| Illustrative Scenario        | GWP (kg CO₂e/m²) |
| ---------------------------- | ---------------: |
| OSB - Low                    |               20 |
| OSB - Mid                    |               25 |
| OSB - High                   |               30 |
| Perennial-grass panel - Low  |               10 |
| Perennial-grass panel - Mid  |               14 |
| Perennial-grass panel - High |               18 |

These values are retained only to demonstrate scenario comparison, sensitivity analysis, and model functionality.

No comparative environmental claim should be drawn from these values.

---

## What the Screening Exercise Actually Shows

The most important result of this project is not a single carbon number.

The exercise identifies the **primary data required to determine the environmental performance of a perennial-grass structural panel rigorously**.

Key data gaps include:

### Agricultural Inputs

* biomass yield per acre or hectare
* establishment period
* fertilizer and soil amendment inputs
* field fuel consumption
* irrigation, where applicable
* harvesting operations
* soil-carbon assumptions
* moisture content
* biomass losses

### Materials

* panel mass per functional unit
* biomass content
* binder or resin type
* binder proportion
* additives
* packaging materials

### Manufacturing

* electricity consumption
* electricity source or grid mix
* thermal-energy requirements
* drying energy
* pressing energy
* production yield
* process waste
* recycled or reused process material

### Logistics

* farm-to-factory distance
* transportation mode
* inbound material logistics
* packaging and outbound assumptions

### Carbon Accounting

* biogenic carbon uptake
* carbon retained in the finished product
* treatment of temporary carbon storage
* coproduct allocation
* treatment of biomass residues
* potential biochar pathways

### Functional Equivalence

* panel dimensions
* density
* thickness
* structural performance
* service-life assumptions
* equivalent OSB reference product

These variables are likely to have significantly more influence on the reliability of the final comparison than the calculation code itself.

---

## Current Interpretation

The screening model demonstrates that a perennial-grass structural panel can be modeled using a conventional LCA framework and compared with OSB under a consistent functional basis.

However, **publicly available information is currently insufficient to support a defensible quantitative comparative environmental claim for Plantd products**.

A decision-grade assessment would require manufacturer-specific agricultural and manufacturing data, an appropriate OSB benchmark, recognized background datasets, defined biogenic-carbon treatment, and applicable PCR requirements.

---

## Path to a Decision-Grade Product LCA

A stronger assessment would proceed through the following stages.

### Phase 1: Primary Data Inventory

Develop a detailed foreground inventory covering:

* agricultural production
* biomass logistics
* panel material composition
* factory energy
* process yield
* packaging
* production residues

### Phase 2: Background LCA Modeling

Connect the foreground inventory with recognized background datasets for:

* electricity
* transportation
* fertilizers
* resins
* fuels
* packaging
* conventional OSB production

### Phase 3: LCIA

Apply recognized impact-assessment methods and report relevant indicators.

For construction-product applications, the final methodology should be selected according to the applicable PCR and EPD program requirements.

### Phase 4: Comparative Analysis

Compare Plantd-type panels against functionally equivalent OSB using:

* equivalent performance
* equivalent functional unit
* consistent boundaries
* consistent impact methods
* transparent data-quality assumptions

### Phase 5:ensitivity and Uncertainty

Test the variables most likely to control the result, including:

* biomass yield
* resin content
* electricity intensity
* logistics
* manufacturing efficiency
* carbon-storage assumptions
* allocation method

### Phase 6: EPD Readiness

Assess the model against the applicable:

* PCR
* ISO 14025 requirements
* ISO 21930 requirements
* program-operator rules
* third-party verification requirements

---

## Potential Extension: Integrated Panel + Biochar Carbon Model

Plantd's evolving biomass system also creates an important future LCA question around production residues and biochar.

A broader model could represent:

**Perennial grass cultivation**

→ harvesting
→ biomass transport
→ panel manufacturing

followed by two product pathways:

**Structural panel**

and

**Biochar / biomass coproduct**

This would require explicit treatment of:

* coproduct allocation
* biogenic carbon
* stable carbon storage
* production residues
* soil application
* avoided-product assumptions
* end-of-life pathways

This extension could connect agricultural LCA, product LCA, circularity, and carbon-removal accounting within one system.

---

## Outputs

Current project outputs include:

* `outputs/openlca_input_table_clean.csv`
* `outputs/screening_gwp_results.csv`
* `outputs/plantd_lca_structure.csv`
* `outputs/plantd_vs_osb_screening_chart.png`

These outputs support methodological demonstration and future model refinement.

---

## Project Structure

```text
plantd-osb-lca/
│
├── data/
│   └── Plantd_openLCA_extracted_dataset.xlsx
│
├── outputs/
│   ├── openlca_input_table_clean.csv
│   ├── screening_gwp_results.csv
│   ├── plantd_lca_structure.csv
│   └── plantd_vs_osb_screening_chart.png
│
├── src/
│   ├── 01_read_excel.py
│   ├── 02_clean_openlca_inputs.py
│   ├── 03_build_screening_model.py
│   ├── 04_make_chart.py
│   └── 05_build_lca_structure.py
│
├── docs/
│   └── methodology.md
│
├── README.md
├── requirements.txt
└── .gitignore
```

---

## What This Project Demonstrates

This case demonstrates the ability to:

* define an LCA goal, functional unit, and system boundary
* structure incomplete product data into an LCI framework
* distinguish primary data, secondary data, and assumptions
* avoid presenting unsupported estimates as environmental claims
* build reproducible Excel and Python workflows
* develop simplified foreground-process models
* identify LCA data-quality gaps
* design sensitivity and scenario analyses
* prepare data structures for openLCA or similar professional tools
* translate a screening model into a roadmap for a decision-grade product LCA
* connect product sustainability analysis with EPD readiness and commercial decision support

---

## Intended Use

This repository is intended for:

* LCA methodology learning
* product-sustainability analysis
* teaching
* portfolio demonstration
* scenario development
* exploration of data requirements for bio-based construction products

It is **not** intended for public comparative environmental claims, marketing claims, regulatory reporting, or verified EPD publication.

---

## Disclaimer

This is an **independent educational and analytical case study**.

It was not commissioned, sponsored, reviewed, or verified by Plantd Materials.

Plantd is referenced because publicly available information about its perennial-grass structural-panel system provides a useful real-world case for exploring product LCA methodology.

Illustrative scenario values in this repository are not Plantd operational data and do not represent Plantd's actual product carbon footprint.

Any commercial or comparative environmental claim would require appropriate primary data, methodological review, applicable PCR requirements, and independent verification where required.
