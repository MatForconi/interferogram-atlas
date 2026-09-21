# The distortions

The six components of the distortion basis, three figures each: the blackbody (as a check),
the temperature shift ΔT, the chemical potential μ, Compton-y, the second-order
temperature residual, and the cosmological recombination radiation. The horizontal dashed line represents the noise, as described in [white noise](../../MODEL.md#noise)

The two line conventions, and how to read each of the three figure types, are
in the [atlas README](../../README.md). The δ statistics quoted below are
collected in the [summary table](../../README.md#the-numbers).

---

## Simple check: the blackbody

Not a distortion, considered a test

![Blackbody — frequency space](blackbody-frequency.png)

The CMB blackbody B<sub>ν</sub> against frequency:
(a) normalised to its own peak with the instrument band over it, (b) absolute
magnitude in Jy/sr, dashed = no band, solid = through the band.

![Blackbody — interferogram space](blackbody-interferogram.png)

The blackbody interferogram: (a) near ZPD,
normalised to the unbanded peak, (b) magnitude out to ±1.5 cm with
±δ<sub>max</sub> marked.

![Blackbody — instrument choices](blackbody-instrument.png)

(a) the continuous interferogram with the samples
two dδ choices would take, (b) the round trip through each dδ, (c) cumulative
information against threshold δ<sub>0</sub>.

## Temperature shift, ΔT (the G spectrum)

$G(x) = x^4\frac{e^x}{(e^x-1)^2}$, 
the shape of a pure temperature shift, at ΔT/T = 10⁻⁵.

![Temperature shift — frequency space](temperature-shift-frequency.png)


![Temperature shift — interferogram space](temperature-shift-interferogram.png)

The G interferogram, unbanded (dashed) and through
the band (solid).

![Temperature shift — instrument choices](temperature-shift-instrument.png)

The three instrument panels for ΔT.

## Chemical potential, μ (the M spectrum)

M(x) = G(x)(α<sub>μ</sub> - 1/x), the chemical-
potential shape. $\mu=2\times 10^{8}$

![Chemical potential — frequency space](chemical-potential-frequency.png)


![Chemical potential — interferogram space](chemical-potential-interferogram.png)

The M interferogram, unbanded and banded.

![Chemical potential — instrument choices](chemical-potential-instrument.png)

The three instrument panels for μ.

## Compton-y (the Y spectrum)

$Y(x) = G(x)(x \coth(\frac{x}{2}) - 4)$ with $y = 1.77\times 10^{-6}$

![Compton-y — frequency space](compton-y-frequency.png)

![Compton-y — interferogram space](compton-y-interferogram.png)

![Compton-y — instrument choices](compton-y-instrument.png)

The three instrument panels for y.

## Second-order temperature residual

What is left of a temperature shift, $\frac{\Delta T}{T}^2(G + \frac{1}{2}Y)$, after the linear piece has
been absorbed into the calibration.

![Second-order residual — frequency space](second-order-residual-frequency.png)

Completely below the noise level

![Second-order residual — interferogram space](second-order-residual-interferogram.png)

The residual's interferogram, unbanded and banded.

![Second-order residual — instrument choices](second-order-residual-instrument.png)

The three instrument panels for the residual.

## Cosmological recombination radiation

The CRR line forest, from the Taylor tables.

![CRR — frequency space](crr-frequency.png)


![CRR — interferogram space](crr-interferogram.png)

![CRR — instrument choices](crr-instrument.png)

The three instrument panels for CRR.

---

[← back to the atlas README](../../README.md) · [MODEL.md](../../MODEL.md)
