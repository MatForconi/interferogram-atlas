# The sky in interferogram space

**v0.1 — 2026-09-21**

A collection of how the spectra looks like to a Fourier-transform spectrometer.

 **The figures live in [`figures/`](figures/)**, six directories each with its own description.

There is no code in this repository. See [MODEL.md](MODEL.md) for what went into the plots.

---

## The interferogram

Radiation from the sky is split into two arms, one is delayed by a path
difference δ, and the two beams are recombined onto a detector. A single
wavenumber ν arrives at the detector twice, the second copy lagging by 2πνδ in
phase. The detector is a square-law device, and different wavenumbers are
mutually incoherent, so their powers simply add. Dropping the δ-independent
term leaves the whole measurement equation of an FTS:

$$
I(\delta) = \int_0^\infty S(\nu)\,\cos(2\pi\nu\delta)\mathrm{d}\nu
$$

Three consequences are used over and over below:

* **At δ = 0 every wavenumber interferes constructively**, so I(0) = ∫S dν: the
  value at zero path difference (ZPD) is the band-integrated intensity. 

* **The interferogram has two scales.** If S is a bump centred at ν<sub>p</sub>
  with width Δν, then I oscillates with period ≈ 1/ν<sub>p</sub> inside an
  envelope of width ≈ 1/Δν. 

* **I is an intensity over wavenumber.** [I] = Jy sr⁻¹ × cm⁻¹. 

Everything is done in **wavenumber**, ν in cm⁻¹, not in GHz. Frequencies are converted for display only: 1 cm⁻¹ = 29.979 GHz.

## The figures

### Structure


| | directory | content |
|---|---|---|
| 1 | [`figures/00-overview/`](figures/00-overview/) | the whole distortion basis at once, in both spaces |
| 2 | [`figures/01-band/`](figures/01-band/) | the band-edge figure |
| 3 | [`figures/02-distortions/`](figures/02-distortions/) | blackbody, ΔT, μ, y, 2nd-order residual, CRR |
| 4 | [`figures/03-sz/`](figures/03-sz/) | the SZ family, and the SZ total |
| 5 | [`figures/04-foregrounds/`](figures/04-foregrounds/) | the six foregrounds, and the total foreground |
| 6 | [`figures/05-totals/`](figures/05-totals/) | the total sky |

---
After the band figure and the two overview figures, **every component gets the
same three figures, always in the same order**, so they can be compared across
sections.

* **solid** = through the band;
* **thin dashed** = the ideal, unbanded case;
* **thick black dashed** = the white-noise level (see below).

A component keeps **the same colour** from frequency space to interferogram
space. Vertical dotted lines at ±δ<sub>max</sub>
mark where the mirror stops.

### Noise

A **white-noise** is assumed: σ<sub>ν</sub> = 1 Jy sr⁻¹. White noise stays white under the cosine transform, so it is a
horizontal line in *both* spaces; only the level changes.

The two noises are related by:

$$
\sigma_\nu = \sqrt{2N}\mathrm{d}\delta\sigma_\delta
  \qquad\Longleftrightarrow\qquad
  \sigma_\delta = \frac{\sigma_\nu}{\mathrm{d}\delta\sqrt{2N}}
  $$

With dδ = 0.005 cm and N = 401 that turns 1 Jy sr⁻¹ per channel into
**σ<sub>δ</sub> = 7.06 per OPD sample**. Where a curve drops below the line,
that channel — or that single OPD sample — has stopped carrying information
about the component.

The line appears on the frequency-space and interferogram-space figures only,
not on the instrument-choices ones.

### The three figure types

**1. `<component>-frequency.png` — frequency space.**
(a) the shape normalised to its own peak, with the window drawn over it
in dashed grey and the band shaded, so it is possible to see what is kept; (b) the
magnitude, dashed = no band, solid = through the band, with σ<sub>ν</sub> as a
horizontal black dashed line.

**2. `<component>-interferogram.png` — interferogram space.**
The same two curves transformed. Panel (a) is normalised to the *unbanded*
peak, so the drop from dashed to solid is the signal the band costs you. Panel (b) is absolute, with ±δ<sub>max</sub> marked and σ<sub>δ</sub> as a horizontal black dashed line.

**3. `<component>-instrument.png` — instrument choices.**
Three panels.

* **(a) what the sampler actually gets.** The black line is the continuous
  interferogram; the dots are the values at the OPD positions an instrument
  with that dδ would visit.

* **(b) the round trip.** Take the
  sampled record from (a), transform it back, and plot the spectrum that comes
  out. The thick grey line is the spectrum that went **in**; each coloured line
  is what comes **out** for one choice of dδ. The matched dotted vertical are represent ν<sub>Nyq</sub> = 1/2dδ.

* **(c) Cumulative information along the stroke.**  The y-axis represents the fraction of the total Σ<sub>j</sub> I(δ<sub>j</sub>)² contributed by all the samples with |δ<sub>j</sub>| ≤ δ<sub>0</sub>. The dot represents the *90% contribution within  ±δ<sub>0</sub>.* 

This is the **raw** information on one component in isolation. It ignores degeneracies.



## Summary

δ<sub>50</sub>, δ<sub>90</sub>, δ<sub>99</sub> are the optical path differences
inside which 50%, 90% and 99% of the cumulative information is collected, on the sample grid
dδ = 0.005 cm, δ<sub>max</sub> = 1 cm. Units are Jy sr⁻¹ × cm⁻¹ and
cm.

| component | I(0) banded | max\|I\| | max/I(0) | δ<sub>50</sub> | δ<sub>90</sub> | δ<sub>99</sub> |
|---|---|---|---|---|---|---|
| blackbody B<sub>ν</sub> | 3.2381e+09 | 3.2381e+09 | 1.000 | 0.010 | 0.075 | 0.130 |
| ΔT (G) | 1.3173e+05 | 1.3173e+05 | 1.000 | 0.010 | 0.060 | 0.085 |
| μ (M) | 5.0260e+01 | 5.0260e+01 | 1.000 | 0.035 | 0.060 | 0.175 |
| y (Y) | 2.3911e+04 | 2.6094e+04 | 1.091 | 0.030 | 0.080 | 0.110 |
| 2nd-order residual | 1.9928e+00 | 1.9928e+00 | 1.000 | 0.010 | 0.045 | 0.060 |
| CRR | 2.6378e+01 | 2.6378e+01 | 1.000 | 0.000 | 0.040 | 0.130 |
| tSZ (non-rel.) | 1.3506e+04 | 1.4739e+04 | 1.091 | 0.030 | 0.080 | 0.110 |
| tSZ (rel. correction) | 8.3530e+01 | 3.4712e+02 | 4.156 | 0.045 | 0.080 | 0.105 |
| kSZ | 3.6440e+01 | 3.6440e+01 | 1.000 | 0.025 | 0.045 | 0.095 |
| SZ total | 1.3626e+04 | 1.4664e+04 | 1.076 | 0.030 | 0.080 | 0.110 |
| spinning dust | 1.4166e+01 | 1.4166e+01 | 1.000 | 0.270 | 0.645 | 0.930 |
| CO (integrated) | 1.0559e+04 | 1.0559e+04 | 1.000 | 0.025 | 0.105 | 0.145 |
| thermal dust | 3.8524e+08 | 3.8524e+08 | 1.000 | 0.010 | 0.010 | 0.040 |
| CIB | 3.3679e+07 | 3.3679e+07 | 1.000 | 0.005 | 0.015 | 0.015 |
| synchrotron | 5.7497e+03 | 5.7497e+03 | 1.000 | 0.005 | 0.145 | 0.495 |
| free-free | 4.5287e+04 | 4.5287e+04 | 1.000 | 0.000 | 0.005 | 0.155 |
| total foreground | 4.1898e+08 | 4.1898e+08 | 1.000 | 0.010 | 0.010 | 0.040 |
| total sky | 4.1915e+08  | 4.1915e+08 | 1.000 | 0.010 | 0.010 | 0.040 |


