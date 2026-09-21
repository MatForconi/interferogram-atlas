# Specifics


| quantity | value | 
|---|---|
| band edges ν<sub>lo</sub>, ν<sub>hi</sub> | 50 GHz – 2 THz = 1.668 – 66.713 cm⁻¹ |
| channel count | 130 in band |
|  dν | 0.500 cm⁻¹ = 15.0 GHz | 
| maximum OPD δ<sub>max</sub> | 1.0 cm | 
| OPD sample spacing dδ | 0.005 cm | 
| Nyquist ν<sub>Nyq</sub> = 1/2dδ | 100.0 cm⁻¹ = 3.00 THz |
| samples per scan N = 2δ<sub>max</sub>/dδ + 1 | 401 | 
| band-edge taper shape | C<sup>∞</sup> compactly supported step | 


The window transmits up to 74.62 cm⁻¹ = 2.24 THz,
against ν<sub>Nyq</sub> = 100.0 cm⁻¹ — a factor of 1.34, so no aliasing.

---

## The window

A smooth passband W(ν) ∈ [0,1]. The
flat top is joined to zero by a C<sup>∞</sup> transition. Window chosen just to show the qualitative behaviour.

$$
t(u)=\frac{1}{1+e^{\left(\frac{1}{u}-\frac{1}{1-u}\right)}}
$$
with $0<u<1$, $t(0)=0$ and $t(1)=1$




## Noise

Assumed white noise of σ<sub>ν</sub>= 1.0 Jy sr⁻¹ which translates to σ<sub>δ</sub> = 7.0622 


## Fiducial amplitudes

| quantity | value | source |
|---|---|---|
| T<sub>CMB</sub> | 2.72548 K | 
| ΔT/T | 10⁻⁵ | 
| μ | 2.0×10⁻⁸ | 
| y (reionisation) | 1.77×10⁻⁶ | 
| ICM optical depth Δτ | 3.93×10⁻⁴ | 
| ICM electron temperature T<sub>e</sub> | 1300 eV |
| ICM bulk velocity β | 1/300 | 
| θ<sub>e</sub> = T<sub>e</sub>/m<sub>e</sub>c² | 2.5440×10⁻³ | 
| y<sub>tSZ</sub> = Δτ·θ<sub>e</sub> | 9.9981×10⁻⁷ | 

---

## Foreground fiducials


| component | parameter | value | meaning |
|---|---|---|---|
| **thermal dust** | `sd_A_d` | 1.49×10⁶ Jy/sr | amplitude at the 545 GHz pivot |
| | `T_effd` | 19.6 K | effective dust temperature |
| | `beta_d` | 1.5 | emissivity index |
| **CIB** | `sd_A_C` | 4.10×10⁵ Jy/sr | amplitude at the 545 GHz pivot |
| | `T_d` | 9.6 K | effective temperature |
| | `beta_c` | 2.2 | emissivity index |
| **synchrotron** | `sd_A_sync` | 288.0 Jy/sr | amplitude at the 100 GHz pivot |
| | `sd_alpha_sync` | 0.82 | power-law index |
| | `sd_omega_sync` | 0.2 | curvature of the power law |
| **free-free** | `sd_T_e_ff` | 7000.0 K | electron temperature |
| | `sd_EM` | 15.0 | emission measure  |
| **spinning dust** | `sd_A_spin` | 1485.33 Jy/sr | amplitude at 22.8 GHz, the template's reference frequency |
| | `sd_nu_p_spin` | 19.0 GHz | peak frequency the template is shifted to |
| **CO (integrated)** | `sd_A_CO` | 1.0 | dimensionless scaling on the template |

Pivots and template reference frequencies: dust and CIB use ν<sub>ref</sub>  =
545 GHz, synchrotron uses ν<sub>ref</sub>  = 100 GHz, and the spinning-dust
template has its own peak at 31.0 GHz and reference at 22.8 GHz, from which it
is shifted to `sd_nu_p_spin`.

Thermal dust and the CIB are modified blackbodies; synchrotron is a power law
with curvature; free-free is computed from the optical depth; spinning dust and CO are read from the external templates
listed below.

---

## External templates

CRR, spinning dust and CO are read rather than computed. 

| template | file |
|---|---|
| CRR Taylor coefficients | `table_Taylor_coeff_{1,2,3}.dat` |
| spinning dust | `SpinningDustTemplate.dat` |
| CO (integrated) | `COintegratedTemplate.dat` |

---

## Assumptions


- **Ideal observation** No beam, no pointing, no scan strategy, no anisotropy. 
- **Ideal symmetric double-sided interferogram**, sampling exactly at δ = 0.
- **Perfect instrument apart from the band.** Beam-splitter efficiency, detector response, throughput and calibration all folded into one real W(ν) ∈ [0,1]. 
- **Assumed window.** 
- **Simple white noise.** σ<sub>ν</sub> = 1 Jy sr⁻¹ per channel
- **No apodisation, no phase correction.** 

---
