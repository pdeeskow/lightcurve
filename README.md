# Variable Star Lightcurve Analysis Pipeline

A comprehensive Python-based pipeline for processing and analyzing photometric observations of variable stars, from raw AAVSO data to publication-ready BAV reports.

## 🌟 Project Overview

This modular analysis pipeline transforms amateur astronomical observations into scientifically rigorous results suitable for professional databases and publications. The system supports multiple types of variable stars and implements state-of-the-art statistical methods for parameter estimation and uncertainty quantification.

### Key Features

- **Automated Data Processing**: AAVSO report parsing with metadata extraction
- **Astrometric Integration**: SIMBAD coordinate queries and constellation determination
- **Precision Time Corrections**: Heliocentric corrections and airmass calculations
- **Bayesian Parameter Estimation**: Advanced MCMC sampling for robust uncertainties
- **Multi-Variable Support**: Specialized analysis for different variable star types
- **BAV Compliance**: Standardized output formats for international databases
- **Publication Quality**: High-resolution plots and comprehensive documentation

## 📊 Supported Variable Star Types

### 🪐 Exoplanets & Transiting Systems
- **Notebook**: `exoplanet_fit.ipynb`
- **Method**: Bayesian transit modeling with PyMC and Exoplanet
- **Parameters**: Planet radius, orbital period, transit timing, impact parameter
- **Output**: Precise transit centers with MCMC-derived uncertainties

### 🔄 Pulsating Variables (RR Lyrae, HADS)
- **Notebook**: `rr_monte_carlo.ipynb`
- **Method**: Fourier series fitting with Monte Carlo error propagation
- **Parameters**: Pulsation period, amplitude, phase relationships
- **Output**: Maximum/minimum timing with statistical uncertainties

### 🌟 Future Extensions
- **Eclipsing Binaries**: Detached, semi-detached, and contact systems
- **Cepheid Variables**: Classical and Type II Cepheids
- **Cataclysmic Variables**: Dwarf novae and classical novae
- **Long-Period Variables**: Mira stars and semi-regular variables

## 🔧 Pipeline Architecture

### Core Workflow (`BAV_lightcurve.ipynb`)
1. **Data Import**: Parse AAVSO report files with complete metadata
2. **Coordinate Processing**: Query SIMBAD for precise J2000 coordinates
3. **Time Corrections**: Apply heliocentric light-travel-time corrections
4. **Airmass Calculation**: Compute observational conditions throughout night
5. **Quality Assessment**: Generate diagnostic plots for data validation
6. **Format Standardization**: Export to common CSV format for analysis
7. **Results Integration**: Combine with theoretical models
8. **BAV Export**: Generate compliant MiniMax and Report formats
9. **Publication Plots**: Create final documentation with metadata tables

### Specialized Analysis Modules

#### Exoplanet Transit Analysis (`exoplanet_fit.ipynb`)
- **Physics-Based Modeling**: Full Keplerian orbital mechanics
- **Advanced Sampling**: Hamiltonian Monte Carlo with automatic tuning
- **Parameter Constraints**: Stellar density, limb darkening, impact parameter
- **Uncertainty Quantification**: Posterior distributions with HDI intervals
- **Model Validation**: Posterior predictive checking and residual analysis

#### RR Lyrae/HADS Analysis (`rr_monte_carlo.ipynb`)
- **Period Determination**: Lomb-Scargle periodogram analysis
- **Fourier Decomposition**: Multi-harmonic series with optimized coefficients
- **Monte Carlo Sampling**: Error propagation through nonlinear transformations
- **Phase Analysis**: Precise maximum/minimum timing determination
- **Statistical Validation**: Bootstrap resampling and confidence intervals

## 🚀 Quick Start

### Prerequisites
```bash
conda install numpy pandas matplotlib scipy astropy
conda install -c conda-forge pymc pytensor exoplanet astroquery arviz
```

### Basic Usage
1. Place AAVSO report file in `data/` directory
2. Run `BAV_lightcurve.ipynb` for data processing and visualization
3. Choose appropriate analysis notebook:
   - For exoplanets: Run `exoplanet_fit.ipynb`
   - For RR Lyrae/HADS: Run `rr_monte_carlo.ipynb`
4. Return to `BAV_lightcurve.ipynb` for final BAV format generation

### Example Workflow
```python
# 1. Process raw observations
# BAV_lightcurve.ipynb → data/lc_obs.csv

# 2. Specialized analysis (example: exoplanet)
# exoplanet_fit.ipynb → data/lc_synth.csv, data/uncertainties.csv

# 3. Generate final reports
# BAV_lightcurve.ipynb → BAV MiniMax/Report files + publication plots
```

## 📁 File Structure

```
lightcurve/
├── BAV_lightcurve.ipynb      # Main pipeline notebook
├── exoplanet_fit.ipynb       # Exoplanet transit analysis
├── rr_monte_carlo.ipynb      # RR Lyrae/HADS analysis
├── data/                     # Data directory
│   ├── *.txt                 # AAVSO report files
│   ├── lc_obs.csv           # Standardized observations
│   ├── lc_synth.csv         # Synthetic lightcurves
│   ├── uncertainties.csv     # Parameter uncertainties
│   ├── *_MiniMax.txt        # BAV MiniMax format
│   ├── *_BAVReport.txt      # BAV Report format
│   ├── *.png                # Publication plots (high-res)
│   └── *.pdf                # Publication plots (vector)
└── README.md                # This file
```

## 🎯 Scientific Applications

### Professional Integration
- **BAV Database**: Automatic format compliance for submission
- **AAVSO Integration**: VSX catalog cross-referencing
- **Literature Comparison**: Precision timing for period studies
- **Multi-Site Coordination**: Standardized timing systems

### Research Capabilities
- **Period Change Detection**: Long-term timing analysis
- **Stellar Astrophysics**: Fundamental parameter determination
- **Exoplanet Characterization**: Precise radius and timing measurements
- **Binary Evolution**: Orbital period decay studies

### Educational Value
- **Modern Methods**: Exposure to cutting-edge statistical techniques
- **Professional Standards**: Learn publication-quality data analysis
- **Modular Design**: Understand scientific software architecture
- **Reproducible Research**: Complete workflow documentation

## 🔬 Technical Highlights

### Statistical Methods
- **Bayesian Inference**: Full posterior distributions with proper uncertainties
- **MCMC Sampling**: Advanced Hamiltonian Monte Carlo implementation
- **Model Selection**: Posterior predictive checking and information criteria
- **Error Propagation**: Rigorous uncertainty quantification through all steps

### Astronomical Standards
- **Time Systems**: Proper heliocentric corrections and coordinate transformations
- **Astrometry**: SIMBAD integration for precise coordinates
- **Photometry**: Professional uncertainty handling and systematic corrections
- **Documentation**: Complete observational metadata preservation

### Software Engineering
- **Modular Architecture**: Extensible design for new variable types
- **Data Standards**: Consistent interfaces between analysis modules
- **Version Control**: Complete project history and collaboration support
- **Reproducibility**: Deterministic results with documented dependencies

## 🤝 Contributing

We welcome contributions for additional variable star types, improved algorithms, or enhanced visualization capabilities. Please see our contribution guidelines for details on development standards and testing procedures.

## 📄 License

This project is open source and available under the MIT License. Please cite appropriately in scientific publications.

## 🙏 Acknowledgments

This pipeline builds upon excellent open-source packages:
- **PyMC**: Bayesian modeling and MCMC sampling
- **Exoplanet**: Specialized astronomical modeling
- **Astropy**: Fundamental astronomy tools
- **AstroQuery**: Astronomical database access
- **ArviZ**: Bayesian analysis visualization

Special thanks to the BAV and AAVSO communities for establishing data standards and promoting amateur-professional collaboration in variable star research.
