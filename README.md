
<picture>
<source srcset="Logo/Stardust-Black.svg?raw=true&sanitize=true" media="(prefers-color-scheme: light)"/>
<source srcset="Logo/Stardust-White.svg?raw=true&sanitize=true" media="(prefers-color-scheme: dark)"/>
<img src="Logo/Stardust-Black.svg?raw=true&sanitize=true" alt="Stardust">
</picture>

** ⚠️ COLOUR VALUES ARE NOT CURRENTLY STABLE AND WILL CHANGE **

Stardust is a modern, general-purpose colour palette optimised for screen
use that follows similar design principles to [Ethan Schoonover's Solarized](https://ethanschoonover.com/solarized/),
and is intended to be useable, for some applications, as a drop-in replacement.

The palette consists of eight balanced hues, each in five shades (Midnight, Dark,
Medium, Vivid, and Pastel), along with five grey scales (Black, Dark grey,
Medium grey, Light grey, and White), and lightly-adapted versions of Solarized's
`base` tones.

The eight hues are evenly spaced around the colour wheel, and because there is
an even number of them, four of the hues are the direct complements of the
other four: Pumpkin, Gold, Lime, and Mint complement Sky, Bilberry, Lilac, and
Raspberry.

This preview version of Stardust was developed using the [J<sub>z</sub>a<sub>z</sub>b<sub>z</sub>](https://doi.org/10.1364/OE.25.015131)
colour appearance model, with a number of manual adjustments applied to specific
shades to ensure balance in practice.

Colour model conversions are performed using the [colorspacious](https://github.com/njsmith/colorspacious)
and [ColorAide](https://github.com/facelessuser/coloraide) Python modules.

<img src="overview.svg?raw=true&sanitize=true" width="100%" alt="Palette overview">

## Compatibility with Solarized

Stardust isn't based directly upon Solarized, but because it follows similar
design principles, the Stardust hues complement slightly-modified versions of
the Solarized base tones quite nicely.

The base shades as they appear in Stardust do not match the Solarized values;
this is because they've been re-specified in J'a'b' and matched with the rest
of the palette. Meanwhile, Stardust's hues are quite different to Solarized's:
if you're especially attached to Solarized's accent palette, Stardust may not
be for you.

In the distributed theme files, "Stardust Dark" and "Stardust Light" themes
use the Solarized base shades as default foreground and background colours, but
with the Stardust hues as accents. Where "Stardust Solar Day" and "Stardust
Solar Night" theme files are present, these seek to reproduce faithfully
the Solarized palette layouts, but using the Stardust colour values, and so
these are the nearest to a direct drop-in replacement for Solarized themes.

## Release versioning

Stardust uses an `x.y.z` versioning scheme, similar to but not entirely
matching [Semantic Versioning](https://semver.org):-

* Major versions (`x`) will be incremented when there is a change to one or more J<sub>z</sub>a<sub>z</sub>b<sub>z</sub> values, or the addition or removal of colours altogether
* Minor versions (`y`) will be incremented when there is a change to derived colour values
* Revisions (`z`) will be incremented when there's a change to anything else (e.g., adding or adjusting a theme)

Where this diverges from Semantic Versioning is that the addition of _new_
colours is considered a "backwards-incompatible" change (so that you only need
to look at the major version number to know which colours are available), but
adjustments to sRGB values (which are non-canonical) is not.

## ChangeLog

### Pre-release versions:

*All values are subject to change*

* 2024-06-03 - *Major change*: Switch from J'a'b' to J<sub>z</sub>a<sub>z</sub>b<sub>z</sub> as the source model; all shades have been re-specified and re-adjustted
* 2024-06-02 - Palettes: added Apple Color Picker `.clr` file
* 2024-06-02 - Values: added colour values as a [tab-delimited text file](Values/Stardust.txt)
* 2024-06-02 - iTerm2: adjusted _Stardust Solar_ themes to more closely match Solarized; added _Stardust High Contrast_ theme.
* 2024-06-01 - Initial preview _(all values subject to change)_

## History

Stardust is a carefully-chosen balanced subset of a colour palette developed
throughout 2023/24 that forms part of a much more comprehensive design system.
Shades were selected initially in sRGB, subsequently re-modelled in CIELab,
then, J'a'b', then subsequently J<sub>z</sub>a<sub>z</sub>b<sub>z</sub>.

## Using Stardust

If your application isn't listed here, you're welcome to use [the colour values](#colour-values);
pull requests containing samples are gratefully received and credit will naturally be given for
any contributions. Please do include a link to any documentation that explains the file format,
so that theme files can be generated rather than needing to be manually updated if values changed.

### Palettes

* [Apple Color Picker](https://github.com/nevali/Stardust/tree/main/macOS) (copy to `~/Library/Colors`)

### Terminal emulators

#### iTerm 2

There are several versions of Stardust [provided for iTerm 2](https://github.com/nevali/Stardust/tree/main/iTerm2):

* _Stardust_ uses the `base` tones (like Solarized), but map the eight Stardust hues to the 16 standard- and high-intensity ANSI colours as most applications expect
* _Stardust Solar_ is a direct port of the Solarized Dark & Light palettes: like with Solarized, these remap all but two of the high-intensity ANSI colours to `base` tones
* _Stardust Pro_ is a grey-on-black or grey-on-white theme with the eight Stardust hues mapped to the 16 ANSI colours; these are closest to "traditional" colour terminal themes
* _Stardust High Contrast_ is similar to _Stardust Pro_, but uses darker shades on a white background, and lighter shades on a dark background, in order to increase contrast. You may wish to experiment with iTerm 2's "Minimum contrast" profile setting, but 40% offers a good balance.

Note that the _Stardust Solar_ themes seek to reproduce faithfully the
Solarized palette arrangements (notwithstanding the accent colour hue
differences between Solarized and Stardust), which is *inconsistent* with
iTerm 2's bundled Solarized theme: the bundled theme uses the same 16 ANSI
colour assignments for both light and dark modes. _Stardust Solar_ follows
the light/dark logic as specified in the [Solarized Xresources file](https://github.com/altercation/solarized/blob/master/xresources/solarized),
which inverts _all_ of the "base" shades between modes (i.e., all `base0`
shades become `base` shades and vice versa; `base03` is swapped for `base3`
and so on).

### SVG, HTML and CSS

The Stardust palette is available as [a set of CSS Variables](CSS/Stardust.css?raw=true).

### Non-screen use

Stardust has not been designed with specific support for non-sRGB gamuts, nor
have its tones been matched to any dye/pigment combinations. However, that
doesn't mean that Stardust is entirely unsuitable for print use, particularly
with respect to the medium tones, whose shades ought to lie within the gamut
of most colour processes, and the CIELAB values should aid in achieving
consistent results.

A future version of Stardust may include specific support for non-screen use
of the palette, but there are no current plans to do so. Contributions are of
course welcome.

## Colour values

The J<sub>z</sub>a<sub>z</sub>b<sub>z</sub> values are canonical. D65 is used as
the reference white point where relevant. RGB values are sRGB unless otherwise
noted.

The following table is also available in [tab-delimited text format](Values/Stardust.txt?raw=true).

|        Name        |    Hex    |  R   |  G   |  B   |  L*  |  a*  |  b*  |   Jz   |   az    |   bz    |
| ------------------ | --------- | ---- | ---- | ---- | ---- | ---- | ---- | ------ | ------- | ------- |
|            Pumpkin | `#b42a13` |  180 |   42 |   19 |   40 |   53 |   46 |    0.1 |  0.0849 |  0.0849 |
|   Midnight pumpkin | `#340000` |   52 |    0 |    0 |    6 |   27 |   12 |  0.025 |  0.0424 |  0.0424 |
|       Dark pumpkin | `#600000` |   96 |    0 |    0 |   18 |   39 |   32 |   0.05 |  0.0636 |  0.0636 |
|       Deep pumpkin | `#9b0000` |  155 |    0 |    0 |   27 |   69 |   62 |  0.075 |  0.1061 |  0.1061 |
|      Vivid pumpkin | `#ff593d` |  255 |   89 |   61 |   65 |   70 |   56 | 0.1575 |  0.1008 |  0.1008 |
|      Light pumpkin | `#ff987e` |  255 |  152 |  126 |   75 |   43 |   33 |  0.175 |  0.0636 |  0.0636 |
|     Pastel pumpkin | `#ffd3c5` |  255 |  211 |  197 |   89 |   17 |   14 |    0.2 |  0.0255 |  0.0255 |
|               Gold | `#8b6600` |  139 |  102 |    0 |   45 |    4 |   96 |    0.1 |     0.0 |   0.126 |
|      Midnight gold | `#241600` |   36 |   22 |    0 |    8 |    3 |   18 |  0.025 |    -0.0 |    0.06 |
|          Dark gold | `#473000` |   71 |   48 |    0 |   21 |    4 |   47 |   0.05 |     0.0 |    0.09 |
|          Deep gold | `#714500` |  113 |   69 |    0 |   33 |   11 |   90 |  0.075 |     0.0 |    0.15 |
|         Vivid gold | `#e9b000` |  233 |  176 |    0 |   75 |    6 |  144 |  0.165 |    -0.0 |  0.1575 |
|         Light gold | `#e1c45c` |  225 |  196 |   92 |   80 |   -2 |   55 |  0.175 |     0.0 |    0.09 |
|        Pastel gold | `#efe5ba` |  239 |  229 |  186 |   91 |   -3 |   22 |    0.2 |     0.0 |   0.036 |
|               Lime | `#008e00` |    0 |  142 |    0 |   51 |  -60 |   54 |    0.1 | -0.0849 |  0.0849 |
|      Midnight lime | `#002600` |    0 |   38 |    0 |   11 |  -28 |   19 |  0.025 | -0.0424 |  0.0424 |
|          Dark lime | `#004900` |    0 |   73 |    0 |   25 |  -44 |   40 |   0.05 | -0.0636 |  0.0636 |
|          Deep lime | `#007300` |    0 |  115 |    0 |   40 |  -72 |   76 |  0.075 | -0.1061 |  0.1061 |
|         Vivid lime | `#00d810` |    0 |  216 |   16 |   75 |  -81 |   71 |   0.15 | -0.1061 |  0.1061 |
|         Light lime | `#7de97f` |  125 |  233 |  127 |   84 |  -52 |   42 |  0.175 | -0.0636 |  0.0636 |
|        Pastel lime | `#c9f5c7` |  201 |  245 |  199 |   92 |  -22 |   17 |    0.2 | -0.0255 |  0.0255 |
|               Mint | `#00996f` |    0 |  153 |  111 |   52 |  -85 |    6 |    0.1 |   -0.12 |     0.0 |
|      Midnight mint | `#002a1a` |    0 |   42 |   26 |   12 |  -39 |    3 |  0.025 |   -0.06 |     0.0 |
|          Dark mint | `#005036` |    0 |   80 |   54 |   26 |  -63 |    5 |   0.05 |   -0.09 |     0.0 |
|          Deep mint | `#008054` |    0 |  128 |   84 |   42 | -114 |    8 |  0.075 |   -0.15 |     0.0 |
|         Vivid mint | `#00eaab` |    0 |  234 |  171 |   77 | -115 |    9 |   0.15 |   -0.15 |    -0.0 |
|         Light mint | `#00f4c8` |    0 |  244 |  200 |   85 |  -69 |    6 |  0.175 |   -0.09 |    -0.0 |
|        Pastel mint | `#adf9e5` |  173 |  249 |  229 |   93 |  -28 |    3 |    0.2 |  -0.036 |     0.0 |
|                Sky | `#0081b3` |    0 |  129 |  179 |   47 |  -30 |  -40 |    0.1 | -0.0849 | -0.0849 |
|       Midnight sky | `#002133` |    0 |   33 |   51 |    9 |  -15 |  -19 |  0.025 | -0.0424 | -0.0424 |
|           Dark sky | `#004160` |    0 |   65 |   96 |   23 |  -22 |  -28 |   0.05 | -0.0636 | -0.0636 |
|           Deep sky | `#0063a2` |    0 |   99 |  162 |   35 |  -27 |  -49 |  0.075 | -0.1061 | -0.1061 |
|          Vivid sky | `#00c5ff` |    0 |  197 |  255 |   71 |  -39 |  -56 |   0.15 | -0.1061 | -0.1061 |
|          Light sky | `#00deff` |    0 |  222 |  255 |   82 |  -31 |  -34 |  0.175 | -0.0636 | -0.0636 |
|         Pastel sky | `#b5f0ff` |  181 |  240 |  255 |   91 |  -15 |  -14 |    0.2 | -0.0255 | -0.0255 |
|           Bilberry | `#5849cb` |   88 |   73 |  203 |   40 |   42 |  -65 |    0.1 |     0.0 |   -0.12 |
|  Midnight bilberry | `#0f093c` |   15 |    9 |   60 |    6 |   20 |  -31 |  0.025 |    -0.0 |   -0.06 |
|      Dark bilberry | `#271c6e` |   39 |   28 |  110 |   17 |   31 |  -46 |   0.05 |    -0.0 |   -0.09 |
|      Deep bilberry | `#4000bc` |   64 |    0 |  188 |   24 |   71 |  -83 |  0.075 |    -0.0 |   -0.15 |
|     Vivid bilberry | `#8b6fff` |  139 |  111 |  255 |   60 |   61 |  -92 |   0.15 |     0.0 |   -0.15 |
|     Light bilberry | `#adb0ff` |  173 |  176 |  255 |   76 |   25 |  -55 |  0.175 |    -0.0 |   -0.09 |
|    Pastel bilberry | `#d8deff` |  216 |  222 |  255 |   89 |    7 |  -22 |    0.2 |    -0.0 |  -0.036 |
|              Lilac | `#9b00a8` |  155 |    0 |  168 |   37 |   72 |  -49 |    0.1 |  0.0827 | -0.0827 |
|     Midnight lilac | `#2b0030` |   43 |    0 |   48 |    4 |   35 |  -24 |  0.025 |  0.0424 | -0.0424 |
|         Dark lilac | `#52005a` |   82 |    0 |   90 |   15 |   54 |  -36 |   0.05 |  0.0636 | -0.0636 |
|         Deep lilac | `#840095` |  132 |    0 |  149 |   21 |   99 |  -64 |  0.075 |  0.1061 | -0.1061 |
|        Vivid lilac | `#ee00ff` |  238 |    0 |  255 |   56 |  102 |  -70 |   0.15 |  0.1061 | -0.1061 |
|        Light lilac | `#f688ff` |  246 |  136 |  255 |   73 |   59 |  -43 |  0.175 |  0.0636 | -0.0636 |
|       Pastel lilac | `#facefe` |  250 |  206 |  254 |   88 |   24 |  -17 |    0.2 |  0.0255 | -0.0255 |
|          Raspberry | `#b60067` |  182 |    0 |  103 |   38 |   73 |   -8 |    0.1 |   0.117 |     0.0 |
| Midnight raspberry | `#350016` |   53 |    0 |   22 |    5 |   36 |   -3 |  0.025 |    0.06 |     0.0 |
|     Dark raspberry | `#620031` |   98 |    0 |   49 |   16 |   54 |   -6 |   0.05 |    0.09 |     0.0 |
|     Deep raspberry | `#9e004a` |  158 |    0 |   74 |   23 |   91 |  -11 |  0.075 |    0.15 |    -0.0 |
|    Vivid raspberry | `#ff00a0` |  255 |    0 |  160 |   57 |   99 |  -10 |   0.15 |  0.1462 |     0.0 |
|    Light raspberry | `#ff7dc0` |  255 |  125 |  192 |   73 |   64 |   -6 |  0.175 |    0.09 |     0.0 |
|   Pastel raspberry | `#ffc9e1` |  255 |  201 |  225 |   88 |   27 |   -3 |    0.2 |   0.036 |    -0.0 |
|             base00 | `#56707b` |   86 |  112 |  123 |   46 |   -7 |   -9 |    0.1 | -0.0154 | -0.0197 |
|             base03 | `#002330` |    0 |   35 |   48 |   12 |   -8 |  -13 |   0.03 | -0.0215 | -0.0276 |
|             base02 | `#133947` |   19 |   57 |   71 |   22 |   -8 |  -12 |   0.05 | -0.0215 | -0.0276 |
|             base01 | `#405964` |   64 |   89 |  100 |   36 |   -7 |   -9 |   0.08 | -0.0154 | -0.0197 |
|              base0 | `#7f8a8f` |  127 |  138 |  143 |   57 |   -3 |   -4 |  0.125 | -0.0062 | -0.0079 |
|              base1 | `#8b969b` |  139 |  150 |  155 |   61 |   -3 |   -4 |  0.135 | -0.0062 | -0.0079 |
|              base2 | `#ebe3d2` |  235 |  227 |  210 |   90 |    0 |    9 |    0.2 |  0.0021 |  0.0149 |
|              base3 | `#fbf2e1` |  251 |  242 |  225 |   96 |    0 |    9 | 0.2125 |  0.0021 |  0.0149 |
|        Medium grey | `#6b6b6b` |  107 |  107 |  107 |   45 |    0 |    0 |    0.1 |     0.0 |    -0.0 |
|              Black | `#000000` |    0 |    0 |    0 |    0 |    0 |    0 |    0.0 |     0.0 |     0.0 |
|          Dark grey | `#333333` |   51 |   51 |   51 |   21 |    0 |    0 |   0.05 |     0.0 |     0.0 |
|         Light grey | `#a6a5a5` |  166 |  165 |  165 |   68 |    0 |    0 |   0.15 |    -0.0 |     0.0 |
|              White | `#ffffff` |  255 |  255 |  255 |  100 |    0 |    0 | 0.2223 |    -0.0 |    -0.0 |


### J<sub>z</sub>a<sub>z</sub>b<sub>z</sub> hue/chroma

<img src="Plots/Jzazbz-Hue-Chroma.svg?raw=true&sanitize=true" alt="Jzazbz Hue/Chroma polar plot" width="45%">

### J'a'b' hue/chroma

<img src="Plots/Jab-Hue-Chroma.svg?raw=true&sanitize=true" alt="J'a'b' Hue/Chroma polar plot" width="45%">

### CIELAB hue/chroma

<img src="Plots/CIELAB-Hue-Chroma.svg?raw=true&sanitize=true" alt="CIELAB Hue/Chroma polar plot" width="45%">

### J<sub>z</sub>a<sub>z</sub>b<sub>z</sub> combined scatter

<img src="Plots/Jzazbz.svg?raw=true&sanitize=true" alt="Jzazbz 3D scatter-plot" width="45%">

### J'a'b' combined scatter

<img src="Plots/Jab.svg?raw=true&sanitize=true" alt="J'a'b' 3D scatter-plot" width="45%">

### CIELAB combined scatter

<img src="Plots/CIELAB.svg?raw=true&sanitize=true" alt="CIE L*a*b 3D scatter-plot" width="45%">

### sRGB combined scatter

<img src="Plots/sRGB.svg?raw=true&sanitize=true" alt="sRGB 3D scatter-plot" width="45%">

# Development and future direction

## Colour modelling

As noted in introduction, the current version of Stardust was developed using
a colour appearance model, or CAM, and specifically the J<sub>z</sub>a<sub>z</sub>b<sub>z</sub>
model, which is one of  the "Lab" family of models (which also includes CIE L*a*b*, OKLab, and
so on).

The easiest way to consider Lab models is:—

* The first axis represents "lightness", typically on a 0-100 scale (although values can fall outside of this range)
* Then, for a given lightness level, the other two values represent coordinates on that plane — together, these represent both the hue and the intensity (or "chromacity")
* If you plot a circle on the plane for a given lightness, with (0, 0) at the centre, then the radius of the circle will be the chromacity, and the angle of any point around that circle will represent the hue

In principle the colour space represented by such models is usually unbounded,
but we are generally only interested in the subset of it which can actually map
to values in the sRGB space. Colour values that don't map neatly to sRGB are
termed "out of gamut", which essentially means that one or more of the RGB
values is really less than 0 or greater than 1.0 (or 255, depending upon how
you represent your RGB values) and gets "clipped" at that level.

In appearance models, the aim is that distance between points within the colour
space is proportional to the _perceived_ difference between those two shades.
In practice, it is impossible to arrive at a single model that is
straightforward to work with, produces meaningful values at a wide range of
chromacity and brightness levels, and accurately represents the appearance
differences between shades on real-world devices under various different
realistic viewing conditions.

These limitations, coupled with the limited gamut of sRGB, means that it's not
sufficient to simply select some defined brightness and intensity levels, and
then split the colour wheel up evenly: what happens in practice is that in
some parts of the spectrum, particularly with high-intensity shades, multiple
hues end up giving the same sRGB values: by the time they're represented on
screen, they have become the same colour.

Rather than complicate the palette definition by using different models for the
different colour variants, the current version of Stardust is defined using a
single general-purpose model, and then a series of adjustments are applied to
specific shades. Without a significant amount of data gathering and analysis, this will
remain the most subjective aspect of the process. Fortunately, colour appearance models
are an active area of research, and so hopefully future versions of Stardust can
be more data-driven.

## Colour naming

Stardust's hue names are chosen to be evocative, rather than attempt to
match a well-known or standard _colour name_: there are no "reds", "blues", or
"greens", for example, because the problem quickly becomes "_which_ red?",
particularly in the larger palette from which Stardust is subsetted.

Using evocative names can also aid in translating the names of shades: "Dark sky"
(English) and „dunkler Himmel“ (German) are both evocative of the same concepts
to speakers of their respective languages, for example. Of course, care still
needs to be taken that colour names don't end up being too similar to one
another (this is why "Bilberry" is not "Blueberry"): for example, "Raspberry"
translated to German is „Himbeere“, which could be seen as too similar to
„Himmel“ (Sky). This particular quandry will not be resolved in this release of
Stardust.

