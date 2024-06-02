
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

This preview version of Stardust was developed using the [J'a'b'](https://doi.org/10.1002/col.20227)
colour appearance model, with a number of manual adjustments applied. Future
versions are likely to use [J<sub>z</sub>a<sub>z</sub>b<sub>z</sub>](https://doi.org/10.1364/OE.25.015131).

Colour model conversions are performed using the [colorspacious](https://github.com/njsmith/colorspacious)
Python module.

<img src="overview.svg?raw=true&sanitize=true" width="95%" alt="Palette overview">

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

* 2024-06-02 - added colour values as a [tab-delimited text file](Values/Stardust.txt)
* 2024-06-02 - iTerm2: Adjusted _Stardust Solar_ themes to more closely match Solarized; added _Stardust High Contrast_ theme.
* 2024-06-01 - Pre-release preview _(all values subject to change)_

## History

Stardust is a carefully-chosen balanced subset of a colour palette developed
throughout 2023/24 that forms part of a much more comprehensive design system.
Shades were selected initially in sRGB, subsequently re-modelled in CIELab,
then later J'a'b'.

## Using Stardust

If your application isn't listed here, you're welcome to use [the colour values](#colour-values);
pull requests containing samples are gratefully received and credit will naturally be given for
any contributions. Please do include a link to any documentation that explains the file format,
so that theme files can be generated rather than needing to be manually updated if values changed.

### Terminals

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

### HTML and CSS

The Stardust palette is available as [a set of CSS Variables](CSS/Stardust.css?raw=true).

### Non-screen use

Stardust has not been designed with non-sRGB gamuts in mind, nor have its tones
been matched to any dye/pigment combinations. However, that doesn't mean that
Stardust is entirely unsuitable for print use, particularly with respect to the
medium tones, whose shades ought to lie within the gamut of most colour processes,
and the L*a*b* values should aid in achieving consistent results.

A future version of Stardust may include specific support for non-screen use
of the palette, but there are no current plans to do so. Contributions are of
course welcome.

## Colour values

The J'a'b' values are canonical. Conversions were performed using the UCS
space; future verions may vary the space used for the different variations to
better approximate display reproduction and human perception. D65 is used as
the reference white point where relevant. RGB values are sRGB.

The following table is also available in [tab-delimited text format](Values/Stardust.txt?raw=true).

|        Name        |    Hex    |  R   |  G   |  B   |  L*  |  a*  |  b*  |  J'  |  a'  |  b'  |
| ------------------ | --------- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- |
|            Pumpkin | `#be4000` |  190 |   64 |    0 |   45 |   48 |   60 |   50 |   25 |   25 |
|   Midnight pumpkin | `#381102` |   56 |   17 |    2 |   11 |   18 |   16 |   15 |   12 |   12 |
|       Dark pumpkin | `#680f00` |  104 |   15 |    0 |   21 |   38 |   36 |   25 |   22 |   22 |
|      Vivid pumpkin | `#ff5d00` |  255 |   93 |    0 |   76 |   85 |  107 |   82 |   35 |   35 |
|     Pastel pumpkin | `#ffd7a3` |  255 |  215 |  163 |   96 |   34 |   42 |   98 |   18 |   18 |
|               Gold | `#9f6c00` |  159 |  108 |    0 |   49 |   12 |   84 |   52 |    0 |   40 |
|      Midnight gold | `#2d1e00` |   45 |   30 |    0 |   13 |    3 |   21 |   16 |    0 |   20 |
|          Dark gold | `#543100` |   84 |   49 |    0 |   24 |   11 |   42 |   26 |    0 |   36 |
|         Vivid gold | `#ffb900` |  255 |  185 |    0 |   83 |   27 |  152 |   87 |    0 |   58 |
|        Pastel gold | `#fff481` |  255 |  244 |  129 |   97 |   -2 |   59 |   98 |    0 |   25 |
|               Lime | `#2b8a11` |   43 |  138 |   17 |   50 |  -48 |   50 |   51 |  -23 |   23 |
|      Midnight lime | `#0d2706` |   13 |   39 |    6 |   13 |  -18 |   16 |   15 |  -11 |   11 |
|          Dark lime | `#004700` |    0 |   71 |    0 |   25 |  -38 |   38 |   26 |  -21 |   21 |
|         Vivid lime | `#00e000` |    0 |  224 |    0 |   77 |  -90 |   95 |   77 |  -34 |   34 |
|        Pastel lime | `#caffaf` |  202 |  255 |  175 |   99 |  -38 |   38 |   98 |  -18 |   18 |
|               Mint | `#009771` |    0 |  151 |  113 |   51 |  -92 |    4 |   50 |  -36 |    0 |
|      Midnight mint | `#002b1f` |    0 |   43 |   31 |   13 |  -29 |    1 |   15 |  -18 |    0 |
|          Dark mint | `#005237` |    0 |   82 |   55 |   26 |  -92 |    3 |   25 |  -32 |    0 |
|         Vivid mint | `#00fdb1` |    0 |  253 |  177 |   79 | -208 |    7 |   75 |  -50 |    0 |
|        Pastel mint | `#93fff7` |  147 |  255 |  247 |   99 |  -43 |    3 |   98 |  -25 |    0 |
|                Sky | `#0086be` |    0 |  134 |  190 |   50 |  -24 |  -42 |   50 |  -23 |  -23 |
|       Midnight sky | `#002535` |    0 |   37 |   53 |   13 |   -9 |  -15 |   15 |  -11 |  -11 |
|           Dark sky | `#004673` |    0 |   70 |  115 |   25 |  -17 |  -37 |   25 |  -21 |  -21 |
|          Vivid sky | `#00ddff` |    0 |  221 |  255 |   78 |  -36 |  -90 |   75 |  -34 |  -34 |
|         Pastel sky | `#abffff` |  171 |  255 |  255 |   99 |  -18 |  -27 |   98 |  -18 |  -18 |
|           Bilberry | `#5957f1` |   89 |   87 |  241 |   46 |   46 |  -77 |   48 |    0 |  -35 |
|  Midnight bilberry | `#171a41` |   23 |   26 |   65 |   11 |   13 |  -26 |   14 |    0 |  -18 |
|      Dark bilberry | `#2e14a2` |   46 |   20 |  162 |   23 |   52 |  -70 |   24 |    0 |  -32 |
|     Vivid bilberry | `#6c88ff` |  108 |  136 |  255 |   75 |   86 | -142 |   75 |   -6 |  -48 |
|    Pastel bilberry | `#e9f4ff` |  233 |  244 |  255 |   98 |   14 |  -41 |   98 |    0 |  -25 |
|              Lilac | `#a734cd` |  167 |   52 |  205 |   46 |   67 |  -57 |   50 |   24 |  -24 |
|     Midnight lilac | `#2f1139` |   47 |   17 |   57 |   11 |   23 |  -19 |   15 |   12 |  -12 |
|         Dark lilac | `#5f007f` |   95 |    0 |  127 |   21 |   60 |  -50 |   25 |   22 |  -22 |
|        Vivid lilac | `#df41ff` |  223 |   65 |  255 |   70 |  111 | -125 |   73 |   17 |  -42 |
|       Pastel lilac | `#ffdcff` |  255 |  220 |  255 |   96 |   39 |  -33 |   98 |   18 |  -18 |
|          Raspberry | `#c2286e` |  194 |   40 |  110 |   44 |   64 |   -2 |   50 |   34 |    0 |
| Midnight raspberry | `#380d1f` |   56 |   13 |   31 |   11 |   24 |   -1 |   15 |   17 |    0 |
|     Dark raspberry | `#6d0035` |  109 |    0 |   53 |   20 |   49 |   -1 |   25 |   31 |    0 |
|    Vivid raspberry | `#ff00a8` |  255 |    0 |  168 |   65 |  101 |   -3 |   73 |   46 |    0 |
|   Pastel raspberry | `#ffcef5` |  255 |  206 |  245 |   95 |   48 |   -1 |   98 |   25 |    0 |
|             base00 | `#5b777f` |   91 |  119 |  127 |   48 |   -8 |   -8 |   50 |   -9 |   -7 |
|             base03 | `#002735` |    0 |   39 |   53 |   13 |  -14 |  -14 |   15 |  -14 |  -11 |
|             base02 | `#003341` |    0 |   51 |   65 |   19 |  -14 |  -14 |   20 |  -14 |  -11 |
|             base01 | `#4d6b74` |   77 |  107 |  116 |   43 |   -8 |   -8 |   45 |  -10 |   -8 |
|              base0 | `#7e8d8e` |  126 |  141 |  142 |   58 |   -5 |   -3 |   60 |   -7 |   -3 |
|              base1 | `#8a9a9b` |  138 |  154 |  155 |   62 |   -6 |   -2 |   65 |   -7 |   -3 |
|              base2 | `#f5eddc` |  245 |  237 |  220 |   94 |    0 |    9 |   95 |    0 |    5 |
|              base3 | `#fff7e6` |  255 |  247 |  230 |   97 |    0 |    9 |   98 |    0 |    5 |
|        Medium grey | `#727070` |  114 |  112 |  112 |   48 |    1 |    1 |   50 |    0 |    0 |
|              Black | `#000000` |    0 |    0 |    0 |    0 |    0 |    0 |    0 |    0 |    0 |
|          Dark grey | `#383636` |   56 |   54 |   54 |   23 |    0 |    0 |   25 |    0 |    0 |
|         Light grey | `#b4b0b0` |  180 |  176 |  176 |   72 |    1 |    1 |   75 |    0 |    0 |
|              White | `#ffffff` |  255 |  255 |  255 |  100 |    0 |    0 |  100 |    0 |    0 |


### J'a'b' hue/chroma

<img src="Plots/Jab-Hue-Chroma.svg?raw=true&sanitize=true" alt="J'a'b' Hue/Chroma polar plot" width="45%">

### J'a'b' hue/lightness

<img src="Plots/Jab-Hue-Lightness.svg?raw=true&sanitize=true" alt="J'a'b' Hue/Lightness polar plot" width="45%">

### J'a'b' combined scatter

<img src="Plots/Jab.svg?raw=true&sanitize=true" alt="J'a'b' 3D scatter-plot" width="45%">

### CIELAB combined scatter

<img src="Plots/CIELAB.svg?raw=true&sanitize=true" alt="CIE L*a*b 3D scatter-plot" width="45%">

### sRGB combined scatter

<img src="Plots/sRGB.svg?raw=true&sanitize=true" alt="sRGB 3D scatter-plot" width="45%">

# Development and future direction

## Colour modelling

As noted in introduction, Stardust was developed using a colour appearance
model, or CAM, and specifically the J'a'b' (CAM16) model, which is one of 
the "Lab" family of models (which also includes CIE L*a*b*, OKLab, and so on).

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
single general-purpose model, and then a series of adjustments are applied.
Without a significant amount of data gathering and analysis, this will remain
the most subjective aspect of the process. Fortunately, colour appearance models
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

