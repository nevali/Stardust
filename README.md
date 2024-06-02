
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

The base shades as they appear in Stardust do not match the Solarized values:
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

* Major versions (`x`) will be incremented when there is a change to one or more J'a'b' values, or the addition or removal of colours altogether
* Minor versions (`y`) will be incremented when there is a change to derived colour values
* Revisions (`z`) will be incremented when there's a change to anything else (e.g., adding or adjusting a theme)

Where this diverges from Semantic Versioning is that the addition of _new_
colours is considered a "backwards-incompatible" change (so that you only need
to look at the major version number to know which colours are available), but
adjustments to sRGB values (which are non-canonical) is not.

## ChangeLog

### Pre-release versions:

*All values are subject to change*

* 2024-06-02 - *Major change*: Switch from J'a'b' to J<sub>z</sub>a<sub>z</sub>b<sub>z</sub> as the source model
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
|            Pumpkin | `#aa3d28` |  170 |   61 |   40 |   41 |   44 |   36 |    0.1 |  0.0707 |  0.0707 |
|   Midnight pumpkin | `#370900` |   55 |    9 |    0 |    9 |   22 |   14 |   0.03 |  0.0354 |  0.0354 |
|       Dark pumpkin | `#600000` |   96 |    0 |    0 |   18 |   39 |   32 |   0.05 |  0.0636 |  0.0636 |
|      Vivid pumpkin | `#df3e25` |  223 |   62 |   37 |   51 |   61 |   50 |  0.125 |  0.0928 |  0.0928 |
|     Pastel pumpkin | `#dec2bb` |  222 |  194 |  187 |   81 |    9 |    7 |   0.18 |  0.0141 |  0.0141 |
|               Gold | `#846900` |  132 |  105 |    0 |   46 |    1 |   66 |    0.1 |     0.0 |     0.1 |
|      Midnight gold | `#281d00` |   40 |   29 |    0 |   11 |    0 |   21 |   0.03 |     0.0 |    0.05 |
|          Dark gold | `#473000` |   71 |   48 |    0 |   21 |    4 |   47 |   0.05 |     0.0 |    0.09 |
|         Vivid gold | `#c29000` |  194 |  144 |    0 |   62 |    6 |  134 | 0.1375 |    -0.0 |    0.15 |
|        Pastel gold | `#d0cbb5` |  208 |  203 |  181 |   82 |   -2 |   12 |   0.18 |     0.0 |    0.02 |
|               Lime | `#188925` |   24 |  137 |   37 |   50 |  -50 |   43 |    0.1 | -0.0707 |  0.0707 |
|      Midnight lime | `#002a00` |    0 |   42 |    0 |   13 |  -26 |   19 |   0.03 | -0.0354 |  0.0354 |
|          Dark lime | `#004900` |    0 |   73 |    0 |   25 |  -44 |   40 |   0.05 | -0.0636 |  0.0636 |
|         Vivid lime | `#00b023` |    0 |  176 |   35 |   63 |  -65 |   56 |  0.125 | -0.0884 |  0.0884 |
|        Pastel lime | `#bdd4bc` |  189 |  212 |  188 |   83 |  -12 |    9 |   0.18 | -0.0141 |  0.0141 |
|               Mint | `#00936e` |    0 |  147 |  110 |   51 |  -69 |    5 |    0.1 |    -0.1 |    -0.0 |
|      Midnight mint | `#002d1f` |    0 |   45 |   31 |   14 |  -35 |    3 |   0.03 |   -0.05 |    -0.0 |
|          Dark mint | `#005036` |    0 |   80 |   54 |   26 |  -63 |    5 |   0.05 |   -0.09 |     0.0 |
|         Vivid mint | `#00bd8c` |    0 |  189 |  140 |   64 |  -91 |    7 |  0.125 |  -0.125 |     0.0 |
|        Pastel mint | `#b0d6cb` |  176 |  214 |  203 |   83 |  -15 |    1 |   0.18 |   -0.02 |     0.0 |
|                Sky | `#007fa7` |    0 |  127 |  167 |   47 |  -28 |  -33 |    0.1 | -0.0707 | -0.0707 |
|       Midnight sky | `#002635` |    0 |   38 |   53 |   12 |  -15 |  -16 |   0.03 | -0.0354 | -0.0354 |
|           Dark sky | `#004160` |    0 |   65 |   96 |   23 |  -22 |  -28 |   0.05 | -0.0636 | -0.0636 |
|          Vivid sky | `#00a2da` |    0 |  162 |  218 |   59 |  -34 |  -44 |  0.125 | -0.0884 | -0.0884 |
|         Pastel sky | `#b3d1d9` |  179 |  209 |  217 |   82 |   -8 |   -7 |   0.18 | -0.0141 | -0.0141 |
|           Bilberry | `#5954ba` |   89 |   84 |  186 |   41 |   30 |  -53 |    0.1 |    -0.0 |    -0.1 |
|  Midnight bilberry | `#15153c` |   21 |   21 |   60 |    9 |   14 |  -25 |   0.03 |    -0.0 |   -0.05 |
|      Dark bilberry | `#271c6e` |   39 |   28 |  110 |   17 |   31 |  -46 |   0.05 |    -0.0 |   -0.09 |
|     Vivid bilberry | `#7164f5` |  113 |  100 |  245 |   51 |   44 |  -71 |  0.125 |     0.0 |  -0.125 |
|    Pastel bilberry | `#c4c8df` |  196 |  200 |  223 |   81 |    3 |  -12 |   0.18 |    -0.0 |   -0.02 |
|              Lilac | `#942a9e` |  148 |   42 |  158 |   39 |   58 |  -41 |    0.1 |  0.0689 | -0.0689 |
|     Midnight lilac | `#2e0231` |   46 |    2 |   49 |    8 |   29 |  -20 |   0.03 |  0.0345 | -0.0345 |
|         Dark lilac | `#510059` |   81 |    0 |   89 |   15 |   53 |  -35 |   0.05 |   0.062 |  -0.062 |
|        Vivid lilac | `#bf20cd` |  191 |   32 |  205 |   48 |   77 |  -54 |  0.125 |  0.0862 | -0.0862 |
|       Pastel lilac | `#d6c0d8` |  214 |  192 |  216 |   80 |   12 |   -9 |   0.18 |  0.0138 | -0.0138 |
|          Raspberry | `#ad1b68` |  173 |   27 |  104 |   39 |   61 |   -6 |    0.1 |  0.0975 |    -0.0 |
| Midnight raspberry | `#38001c` |   56 |    0 |   28 |    8 |   31 |   -3 |   0.03 |  0.0488 |    -0.0 |
|     Dark raspberry | `#620031` |   98 |    0 |   49 |   16 |   53 |   -6 |   0.05 |  0.0877 |     0.0 |
|    Vivid raspberry | `#dc1884` |  220 |   24 |  132 |   49 |   75 |   -8 |  0.125 |  0.1158 |     0.0 |
|   Pastel raspberry | `#e0bdc9` |  224 |  189 |  201 |   80 |   14 |   -1 |   0.18 |  0.0195 |    -0.0 |
|             base00 | `#5b777f` |   91 |  119 |  127 |   48 |   -8 |   -8 | 0.1048 | -0.0162 |  -0.017 |
|             base03 | `#002735` |    0 |   39 |   53 |   13 |  -14 |  -14 | 0.0317 | -0.0317 |  -0.032 |
|             base02 | `#003341` |    0 |   51 |   65 |   19 |  -14 |  -14 | 0.0423 | -0.0316 | -0.0319 |
|             base01 | `#4d6b74` |   77 |  107 |  116 |   43 |   -8 |   -8 | 0.0944 | -0.0175 | -0.0184 |
|              base0 | `#7e8d8e` |  126 |  141 |  142 |   58 |   -5 |   -3 |  0.126 | -0.0093 | -0.0059 |
|              base1 | `#8a9a9b` |  138 |  154 |  155 |   62 |   -6 |   -2 | 0.1368 | -0.0092 | -0.0053 |
|              base2 | `#f5eddc` |  245 |  237 |  220 |   94 |    0 |    9 | 0.2082 |  0.0021 |  0.0145 |
|              base3 | `#fff7e6` |  255 |  247 |  230 |   97 |    0 |    9 | 0.2161 |  0.0021 |  0.0144 |
|        Medium grey | `#727070` |  114 |  112 |  112 |   48 |    1 |    1 | 0.1051 |  0.0013 |  0.0011 |
|              Black | `#000000` |    0 |    0 |    0 |    0 |    0 |    0 |    0.0 |     0.0 |     0.0 |
|          Dark grey | `#383636` |   56 |   54 |   54 |   23 |    0 |    0 |  0.053 |  0.0008 |  0.0007 |
|         Light grey | `#b4b0b0` |  180 |  176 |  176 |   72 |    1 |    1 | 0.1598 |  0.0016 |  0.0014 |
|              White | `#ffffff` |  255 |  255 |  255 |  100 |    0 |    0 | 0.2221 | -0.0001 | -0.0001 |


### J'a'b' hue/chroma

<img src="Plots/Jab-Hue-Chroma.svg?raw=true&sanitize=true" alt="J'a'b' Hue/Chroma polar plot" width="45%">

### CIELAB hue/chroma

<img src="Plots/CIELAB-Hue-Chroma.svg?raw=true&sanitize=true" alt="CIELAB Hue/Chroma polar plot" width="45%">

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

