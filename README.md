
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

* 2024-06-04 - Corrected/re-balanced all brightness levels; adjustments to vivid and pastel shades (Lilac, Raspberry, Pumpkin, Bilberry)
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
|            Pumpkin | `#c43921` |  196 |   57 |   33 |   45 |   54 |   45 |  0.111 |  0.0849 |  0.0849 |
|   Midnight pumpkin | `#3f0600` |   63 |    6 |    0 |   10 |   26 |   17 | 0.0333 |  0.0424 |  0.0424 |
|       Dark pumpkin | `#670a00` |  103 |   10 |    0 |   20 |   39 |   34 | 0.0555 |  0.0636 |  0.0636 |
|       Deep pumpkin | `#9f0000` |  159 |    0 |    0 |   28 |   69 |   63 | 0.0777 |  0.1061 |  0.1061 |
|      Vivid pumpkin | `#ff5034` |  255 |   80 |   52 |   71 |   85 |   68 | 0.1749 |  0.1167 |  0.1167 |
|      Light pumpkin | `#ffa78d` |  255 |  167 |  141 |   81 |   44 |   34 | 0.1888 |  0.0636 |  0.0636 |
|     Pastel pumpkin | `#ffe0d2` |  255 |  224 |  210 |   94 |   17 |   14 |  0.211 |  0.0255 |  0.0255 |
|               Gold | `#997300` |  153 |  115 |    0 |   50 |    4 |   97 |  0.111 |    -0.0 |   0.126 |
|      Midnight gold | `#2d2000` |   45 |   32 |    0 |   13 |    1 |   26 | 0.0333 |    -0.0 |    0.06 |
|          Dark gold | `#4d3700` |   77 |   55 |    0 |   24 |    3 |   51 | 0.0555 |     0.0 |    0.09 |
|          Deep gold | `#754800` |  117 |   72 |    0 |   34 |   11 |   93 | 0.0777 |    -0.0 |    0.15 |
|         Vivid gold | `#ffc700` |  255 |  199 |    0 |   83 |    6 |  130 | 0.1833 |     0.0 |  0.1575 |
|         Light gold | `#f3d56a` |  243 |  213 |  106 |   86 |   -2 |   56 | 0.1888 |     0.0 |    0.09 |
|        Pastel gold | `#fef3c7` |  254 |  243 |  199 |   96 |   -3 |   23 |  0.211 |    -0.0 |   0.036 |
|               Lime | `#009c16` |    0 |  156 |   22 |   56 |  -61 |   53 |  0.111 | -0.0849 |  0.0849 |
|      Midnight lime | `#002f00` |    0 |   47 |    0 |   15 |  -30 |   24 | 0.0333 | -0.0424 |  0.0424 |
|          Dark lime | `#005000` |    0 |   80 |    0 |   28 |  -43 |   41 | 0.0555 | -0.0636 |  0.0636 |
|          Deep lime | `#007600` |    0 |  118 |    0 |   41 |  -72 |   77 | 0.0777 | -0.1061 |  0.1061 |
|         Vivid lime | `#00f02e` |    0 |  240 |   46 |   83 |  -83 |   72 | 0.1666 | -0.1061 |  0.1061 |
|         Light lime | `#8dfc8e` |  141 |  252 |  142 |   90 |  -53 |   43 | 0.1888 | -0.0636 |  0.0636 |
|        Pastel lime | `#d6ffd4` |  214 |  255 |  212 |   97 |  -23 |   18 |  0.211 | -0.0255 |  0.0255 |
|               Mint | `#00a87c` |    0 |  168 |  124 |   57 |  -85 |    7 |  0.111 |   -0.12 |    -0.0 |
|      Midnight mint | `#003423` |    0 |   52 |   35 |   16 |  -42 |    3 | 0.0333 |   -0.06 |    -0.0 |
|          Dark mint | `#00573c` |    0 |   87 |   60 |   29 |  -62 |    5 | 0.0555 |   -0.09 |     0.0 |
|          Deep mint | `#008457` |    0 |  132 |   87 |   43 | -113 |    8 | 0.0777 |   -0.15 |    -0.0 |
|         Vivid mint | `#00ffc0` |    0 |  255 |  192 |   85 | -118 |    9 | 0.1666 |   -0.15 |     0.0 |
|         Light mint | `#00ffd9` |    0 |  255 |  217 |   91 |  -70 |    6 | 0.1888 |   -0.09 |     0.0 |
|        Pastel mint | `#b9fff2` |  185 |  255 |  242 |   98 |  -28 |    3 |  0.211 |  -0.036 |     0.0 |
|                Sky | `#008fc3` |    0 |  143 |  195 |   53 |  -32 |  -41 |  0.111 | -0.0849 | -0.0849 |
|       Midnight sky | `#002b3d` |    0 |   43 |   61 |   14 |  -17 |  -18 | 0.0333 | -0.0424 | -0.0424 |
|           Dark sky | `#004867` |    0 |   72 |  103 |   26 |  -22 |  -28 | 0.0555 | -0.0636 | -0.0636 |
|           Deep sky | `#0066a6` |    0 |  102 |  166 |   37 |  -28 |  -49 | 0.0777 | -0.1061 | -0.1061 |
|          Vivid sky | `#00dcff` |    0 |  220 |  255 |   78 |  -41 |  -58 | 0.1666 | -0.1061 | -0.1061 |
|          Light sky | `#00f0ff` |    0 |  240 |  255 |   88 |  -32 |  -35 | 0.1888 | -0.0636 | -0.0636 |
|         Pastel sky | `#c1feff` |  193 |  254 |  255 |   96 |  -15 |  -14 |  0.211 | -0.0255 | -0.0255 |
|           Bilberry | `#6356db` |   99 |   86 |  219 |   45 |   41 |  -67 |  0.111 |    -0.0 |   -0.12 |
|  Midnight bilberry | `#181546` |   24 |   21 |   70 |   10 |   18 |  -30 | 0.0333 |     0.0 |   -0.06 |
|      Dark bilberry | `#2c2475` |   44 |   36 |  117 |   20 |   29 |  -46 | 0.0555 |    -0.0 |   -0.09 |
|      Deep bilberry | `#4300c0` |   67 |    0 |  192 |   25 |   70 |  -83 | 0.0777 |    -0.0 |   -0.15 |
|     Vivid bilberry | `#816bff` |  129 |  107 |  255 |   70 |   97 | -143 | 0.1833 | -0.0296 | -0.2079 |
|     Light bilberry | `#bdc1ff` |  189 |  193 |  255 |   82 |   25 |  -56 | 0.1888 |    -0.0 |   -0.09 |
|    Pastel bilberry | `#cce1ff` |  204 |  225 |  255 |   90 |    5 |  -29 | 0.2005 | -0.0067 | -0.0474 |
|              Lilac | `#aa12b7` |  170 |   18 |  183 |   42 |   72 |  -50 |  0.111 |  0.0827 | -0.0827 |
|     Midnight lilac | `#35003a` |   53 |    0 |   58 |    8 |   36 |  -24 | 0.0333 |  0.0424 | -0.0424 |
|         Dark lilac | `#590061` |   89 |    0 |   97 |   18 |   53 |  -36 | 0.0555 |  0.0636 | -0.0636 |
|         Deep lilac | `#870099` |  135 |    0 |  153 |   22 |   99 |  -64 | 0.0777 |  0.1061 | -0.1061 |
|        Vivid lilac | `#e43af4` |  228 |   58 |  244 |   58 |   84 |  -59 | 0.1499 |  0.0902 | -0.0902 |
|        Light lilac | `#ff97ff` |  255 |  151 |  255 |   79 |   61 |  -44 | 0.1888 |  0.0636 | -0.0636 |
|       Pastel lilac | `#ffdbff` |  255 |  219 |  255 |   93 |   24 |  -18 |  0.211 |  0.0255 | -0.0255 |
|          Raspberry | `#c70074` |  199 |    0 |  116 |   42 |   74 |   -8 |  0.111 |   0.117 |     0.0 |
| Midnight raspberry | `#40001f` |   64 |    0 |   31 |    9 |   37 |   -4 | 0.0333 |    0.06 |    -0.0 |
|     Dark raspberry | `#6a0037` |  106 |    0 |   55 |   18 |   54 |   -6 | 0.0555 |    0.09 |     0.0 |
|     Deep raspberry | `#a2004d` |  162 |    0 |   77 |   25 |   91 |  -11 | 0.0777 |    0.15 |    -0.0 |
|    Vivid raspberry | `#ff21a0` |  255 |   33 |  160 |   59 |   86 |   -9 | 0.1499 |  0.1275 |    -0.0 |
|    Light raspberry | `#ff8cd1` |  255 |  140 |  209 |   79 |   66 |   -6 | 0.1888 |    0.09 |    -0.0 |
|   Pastel raspberry | `#ffd6ef` |  255 |  214 |  239 |   92 |   28 |   -3 |  0.211 |   0.036 |    -0.0 |
|             base00 | `#627d89` |   98 |  125 |  137 |   51 |   -7 |   -9 |  0.111 | -0.0154 | -0.0197 |
|             base03 | `#002633` |    0 |   38 |   51 |   13 |   -8 |  -12 | 0.0333 | -0.0215 | -0.0276 |
|             base02 | `#0b3340` |   11 |   51 |   64 |   19 |   -8 |  -12 | 0.0444 | -0.0215 | -0.0276 |
|             base01 | `#56707b` |   86 |  112 |  123 |   46 |   -7 |   -9 | 0.0999 | -0.0154 | -0.0197 |
|              base0 | `#899499` |  137 |  148 |  153 |   61 |   -3 |   -4 | 0.1332 | -0.0062 | -0.0079 |
|              base1 | `#96a1a6` |  150 |  161 |  166 |   66 |   -3 |   -4 | 0.1443 | -0.0062 | -0.0079 |
|              base2 | `#f9f1e0` |  249 |  241 |  224 |   95 |    0 |    9 |  0.211 |  0.0021 |  0.0149 |
|              base3 | `#fff9e8` |  255 |  249 |  232 |   98 |    0 |    9 | 0.2176 |  0.0021 |  0.0149 |
|        Medium grey | `#787878` |  120 |  120 |  120 |   50 |    0 |    0 |  0.111 |    -0.0 |     0.0 |
|              Black | `#000000` |    0 |    0 |    0 |    0 |    0 |    0 |    0.0 |     0.0 |     0.0 |
|          Dark grey | `#3a3939` |   58 |   57 |   57 |   24 |    0 |    0 | 0.0555 |     0.0 |     0.0 |
|         Light grey | `#bab9b9` |  186 |  185 |  185 |   75 |    0 |    0 | 0.1666 |    -0.0 |     0.0 |
|              White | `#ffffff` |  255 |  255 |  255 |  100 |    0 |    0 | 0.2221 |    -0.0 |     0.0 |


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

