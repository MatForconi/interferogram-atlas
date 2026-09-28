# CO isotopologues and the channel grid

Can the channel spacing be chosen so that CO drops out of the spectrum, and how
much do the CO isotopologues "mess" it up?

---

## Model

In the model used here, the <sup>12</sup>CO rotational lines form an exactly
evenly spaced ladder, ν<sub>J</sub> = J × 115.27 GHz.

If the channel spacing is dν = 115.27/8 = 14.41 GHz, every <sup>12</sup>CO line lands on a channel centre that can be masked. In this case we have not used a window.

The isotopologue ladders are spaced by their own emission, so they **do not** land on that grid, and they leak into every channel.

---

## Assumptions

Every one of these is a deliberate simplification.

1. **Rigid rotor.** Lines at ν<sub>J</sub> = 2BJ. 
2. **Lines are delta functions.**
3. **Local Thermodynamic Equilibrium (LTE) at a single excitation temperature** T<sub>ex</sub> for every level of every species.
4. **One velocity profile for all lines**, flat-topped (a box) of width Δv.
5. **Same column, same line width and same dipole moment for all species.** The
   isotopologues differ from <sup>12</sup>CO only through B and a fixed
   abundance X. 

---

## The numbers

### Physical parameters

| quantity | symbol | value |
|---|---|---|
| <sup>12</sup>CO(1→0) integrated intensity | W<sub>CO</sub> | 1 K km/s |
| <sup>12</sup>CO(1→0) optical depth | τ<sub>0</sub> | 3 (diffuse / translucent gas) |
| excitation temperature | T<sub>ex</sub> | 7 K |
| isotope ratios | <sup>12</sup>C/<sup>13</sup>C, <sup>16</sup>O/<sup>18</sup>O, <sup>18</sup>O/<sup>17</sup>O | 68, 557, 3.6 |

### Species

B from laboratory spectroscopy (CDMS). X = abundance relative to
<sup>12</sup>C<sup>16</sup>O. Q = partition function at 7 K. **X and Q values to be double checked.**

| species | B [MHz] | X | ν(1→0) [GHz] | Q |
|---|---|---|---|---|
| <sup>12</sup>C<sup>16</sup>O | 57635.968 | 1 | 115.2719 | 2.893 |
| <sup>13</sup>C<sup>16</sup>O | 55101.011 | 1/68 | 110.2020 | 3.008 |
| <sup>12</sup>C<sup>18</sup>O | 54891.420 | 1/557 | 109.7828 | 3.018 |
| <sup>12</sup>C<sup>17</sup>O | 56179.990 | 1/(557 × 3.6) = 1/2005 | 112.3600 | 2.957 |
| <sup>13</sup>C<sup>18</sup>O | 52356.001 | 1/(68 × 557) = 1/37876 | 104.7120 | 3.145 |
| <sup>13</sup>C<sup>17</sup>O | 53644.791 | 1/(68 × 557 × 3.6) = 1/136354 | 107.2896 | 3.079 |

---

## The equations

**(1) Line positions.** For the line from upper level J to J − 1 of a rigid rotor,

$$\nu_J = 2BJ, \qquad E_J = hB\,J(J+1).$$


**(2) Spectrum.** A sum of delta functions with the integrated flux F<sub>J</sub>,

$$S(\nu)=\sum_J F_J\,\delta_D(\nu-\nu_J)\qquad[\mathrm{Jy\,sr^{-1}}].$$

**(3) Interferogram.** The FTS measurement equation gives

$$I(\delta)=\int_0^\infty S(\nu)\cos(2\pi\nu\delta)\,d\nu=\sum_J F_J\cos(2\pi\nu_J\delta).$$

**(4) Recovered spectrum.** Trapezoid-weighted cosine transform of the samples:

$$\tilde S(\nu)=2\,d\delta\sum_{n=-M}^{M}w_n\,I(\delta_n)\cos(2\pi\nu\delta_n),
\qquad w_{\pm M}=\tfrac12,\ w_n=1\ \text{otherwise}.$$



---

## The J = 1→0 lines on the channel grid

![CO isotopologues — J=1→0 lines on the channel grid](co_response.png)

Each curve is normalised to its own peak. The dots are the same function at the
in-band channel centres ν<sub>k</sub> (faint dotted verticals), i.e. the only
numbers the instrument delivers. The area coloured is the instrumental band.

* **Top row, 115.27/8 grid** (dν = 14.409 GHz, dδ = 0.00500 cm,
  δ<sub>max</sub> = 1.0403 cm). <sup>12</sup>CO sits on channel 8. Its dot there is 1 and every other dot is exactly 0.
* **Bottom row, slightly different grid** (dν = 14.990 GHz, dδ = 0.00500 cm,
  δ<sub>max</sub> = 1.0000 cm). Now <sup>12</sup>CO is off the grid too and leaks like the others.

<sup>13</sup>CO and C<sup>18</sup>O almost overlap, because their B differ by
only 0.4%.

---

## Lines in the interferogram space


![12CO — four lines in frequency and interferogram space](co_four_lines.png)

**(a)** The four <sup>12</sup>CO as fractions f<sub>J</sub> = F<sub>J</sub>/ΣF of the whole ladder. **(b)** Each line becomes one cosine f<sub>J</sub> cos(2πJν<sub>1→0</sub>δ), with period 1/(Jν<sub>1→0</sub>). The black curve is their sum.


![CO isotopologues — interferogram space](co_interf.png)

**(a)** I(δ)/I(0)  summed over every line below 2 THz: J = 1…10 for <sup>12</sup>CO and J = 1…9 for <sup>13</sup>CO. It is evaluated continuously on a fine OPD grid, not at the instrument samples.  **(b)** The end of the stroke.

---

## What lands in the channels, after masking the <sup>12</sup>CO channels

### In frequency space

![CO isotopologues — channel values after masking](co_masked.png)

The grey bars are the six masked <sup>12</sup>CO channels (J = 1…6):

The dashed line is σ<sub>ν</sub>.

* **(a) Off grid.** <sup>12</sup>CO is off the grid.
* **(b) 115.27/8 grid.** Every <sup>12</sup>CO line is exactly on a channel, so
  masking those six channels removes it completely. The only
  <sup>12</sup>CO point left is the J = 7→6 line at 806.9 GHz. It is on the
  grid but, at F/dν = 0.38 Jy/sr, fainter than σ<sub>ν</sub>, so it is not
  masked. The isotopologues are unchanged: <sup>13</sup>CO at 10²–3×10³ Jy/sr
  below 350 GHz, C<sup>18</sup>O and C<sup>17</sup>O at 10–300. Above ~700 GHz
  everything is at or below σ<sub>ν</sub>.

### In interferogram space

![CO isotopologues — channel values after masking, in interferogram space](co_masked_interf.png)

The unmasked in-band channel values of the figure above, transformed back to the
OPD samples the instrument records.

* **(a) Off grid.** An off-grid <sup>12</sup>CO line differs from its
  nearest channel's cosine by a phase that drifts linearly.
* **(b) 115.27/8 grid.** Each on-grid line matches its channel's cosine along
  the whole stroke, so masking removes it.

---

[← back to the atlas README](../../README.md) · [MODEL.md](../../MODEL.md)
