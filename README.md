
<picture>
<source srcset="Logo/Stardust-Black.svg?raw=true&sanitize=true" media="(prefers-color-scheme: light)"/>
<source srcset="Logo/Stardust-White.svg?raw=true&sanitize=true" media="(prefers-color-scheme: dark)"/>
<img src="Logo/Stardust-Black.svg?raw=true&sanitize=true" alt="Stardust">
</picture>

** ⚠️ COLOUR VALUES ARE NOT CURRENTLY STABLE AND WILL CHANGE **

* [Introduction](#introduction)
  * [Compatibility with Solarized](#compatibility-with-solarized)
* [Releases](#releases)
  * [Release versioning](#release-versioning)
  * [ChangeLog](#changelog)
  * [History](#history)
* [Using Stardust](#using-stardust)
  * [Palettes and swatches](#palettes)
  * [Terminal emulators](#terminal-emulators)
  * [SVG, HTML, and CSS](#svg-html-and-css)
  * [Non-screen use](#non-screen-use)
* [Development and future direction](#development-and-future-direction)
  * [A colour primer](#a-colour-primer)
  * [Colour appearance modelling](#colour-appearance-modelling)
  * [Colour naming](#colour-naming)
  * [Build process](#build-process)
  * [Future direction](#future-direction)
* [Colour values](#colour-values)
* [Plots](#plots)

## Introduction

Stardust is a modern, general-purpose colour palette optimised for screen
use that follows similar design principles to [Ethan Schoonover's Solarized](https://ethanschoonover.com/solarized/),
and is intended to be useable, for some applications, as a drop-in replacement.

The palette consists of eight balanced hues, each in five shades (Midnight, Dark,
Medium, Vivid, and Pastel), along with five grey scales (Black, Dark grey,
Medium grey, Light grey, and White), and lightly-adapted versions of Solarized's
`base` tones.

The eight hues are evenly spaced around the colour wheel, and because there is
an even number of them, four of the hues are the direct complements of the
other four: Pumpkin, Gold, Lime, and Spearmint complement Sky, Bilberry, Lilac, and
Raspberry.

This preview version of Stardust was developed using the [J<sub>z</sub>a<sub>z</sub>b<sub>z</sub>](https://doi.org/10.1364/OE.25.015131)
colour appearance model, with a number of manual adjustments applied to specific
shades to ensure balance in practice.

Colour model conversions are performed using the [colorspacious](https://github.com/njsmith/colorspacious)
and [ColorAide](https://github.com/facelessuser/coloraide) Python modules.

<img src="overview.svg?raw=true&sanitize=true" width="100%" alt="Palette overview">

### Compatibility with Solarized

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

## Releases

### Release versioning

Stardust uses an `x.y.z` versioning scheme, similar to but not entirely
matching [Semantic Versioning](https://semver.org):-

* Major versions (`x`) will be incremented when there is a change to one or more J<sub>z</sub>a<sub>z</sub>b<sub>z</sub> values, or the addition or removal of colours altogether
* Minor versions (`y`) will be incremented when there is a change to derived colour values
* Revisions (`z`) will be incremented when there's a change to anything else (e.g., adding or adjusting a theme)

Where this diverges from Semantic Versioning is that the addition of _new_
colours is considered a "backwards-incompatible" change (so that you only need
to look at the major version number to know which colours are available), but
adjustments to sRGB values (which are non-canonical) is not.

### ChangeLog

#### Pre-release versions:

*All values are subject to change*

* 2024-06-06 - Renamed _Mint_ to _Spearmint_; adjusted Raspberry, Pumpkin, and Gold mid tones
* 2024-06-04 - Corrected/re-balanced all brightness levels; adjustments to vivid and pastel shades (Lilac, Raspberry, Pumpkin, Bilberry)
* 2024-06-03 - *Major change*: Switch from J'a'b' to J<sub>z</sub>a<sub>z</sub>b<sub>z</sub> as the source model; all shades have been re-specified and re-adjustted
* 2024-06-02 - Palettes: added Apple Color Picker `.clr` file
* 2024-06-02 - Values: added colour values as a [tab-delimited text file](Values/Stardust.txt)
* 2024-06-02 - iTerm2: adjusted _Stardust Solar_ themes to more closely match Solarized; added _Stardust High Contrast_ theme.
* 2024-06-01 - Initial preview _(all values subject to change)_

### History

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

## Development and future direction

To say that [colour](https://en.wikipedia.org/wiki/Color) is complicated would be a 
[monstrous understatement](https://www.gutenberg.org/files/26054/26054-h/26054-h.htm);
colour is complicated in ways that we are still [learning about today](https://www.nature.com/articles/s41467-024-45820-z).
Digital colour, and in particular digital _colour synthesis_ (i.e., _reproducing_ colours
using combinations of red, green, and blue light emitters driven by digital
signals) is itself a complex, constantly-evolving field of scientific and
industrial research. New display technologies are being [continually developed](https://displayweek.org/2024/Program/Seminar),
often vastly altering our ability to reproduce colours on screens.

This short introduction is unlikely to do the subject justice.

### A colour primer

[Light](https://youtu.be/QqY8fY0TqaQ?si=48oSPUKHoIv4NEPz), and so colour,
is conveyed through [wave packets](https://en.wikipedia.org/wiki/Photon)
of [electromagnetic radiation](https://en.wikipedia.org/wiki/Electromagnetic_radiation)
that [travel in a straight line](https://en.wikipedia.org/wiki/Fermat%27s_principle)
[through](https://en.wikipedia.org/wiki/Geodesic) [curved](https://en.wikipedia.org/wiki/General_relativity)
[spacetime](https://en.wikipedia.org/wiki/Special_relativity) until they collide
with some [matter](https://en.wikipedia.org/wiki/Matter), such as that making up
your [retinal cells](https://en.wikipedia.org/wiki/Retina), or the [paint](https://en.wikipedia.org/wiki/Paint)
on the wall nearest to you.

The [amount of energy](https://en.wikipedia.org/wiki/Planck_relation)
in one of these wave packets is proportional to its [frequency](https://en.wikipedia.org/wiki/Frequency),
which is _inversely_ proportional to its [wavelength](https://en.wikipedia.org/wiki/Wavelength).
Or to put it another way, the radiation frequency, wavelength, and energy
of a single photon (wave packet) are different ways of expressing the same
thing. [Perhaps counterintuitively](https://www.nobelprize.org/prizes/physics/1921/summary/),
this means light being brighter doesn't mean its individual photons have any
more energy—there are just more of them—[whereas if the light was _bluer_ they would](https://www.khanacademy.org/science/physics/quantum-physics/photons/a/photoelectric-effect).

(Obviously, it's possible for the _total_ energy in a lot of redder photons to
add up to more than the total energy in a few bluer photons, but it's not
especially relevant to this discussion).

[For practical purposes](https://www.itu.int/en/ITU-R/information/Pages/default.aspx#gsc.tab=0),
we split the [electromagnetic spectrum](https://en.wikipedia.org/wiki/Electromagnetic_spectrum)
into different [frequency _bands_](https://en.wikipedia.org/wiki/Spectral_band)
which we tend to refer to with names like "[shortwave radio](https://en.wikipedia.org/wiki/Shortwave_radio)",
"[X-rays](https://en.wikipedia.org/wiki/X-ray)" and "[gamma rays](https://en.wikipedia.org/wiki/Gamma_ray)",
based upon the common characteristics and applications of radiation whose
frequency lies within that band.

The 420-700 [terahertz](https://en.wikipedia.org/wiki/Hertz) frequency band
(wavelengths of between 700 and 400 [nanometres](https://en.wikipedia.org/wiki/Nanometre)
respectively) is termed the [_visible light_ band](https://en.wikipedia.org/wiki/Visible_spectrum),
or _visible spectrum_, so-called for the probably-obvious reason that it's
the range within which typical human photoreceptor cells [have good frequency response](https://commons.wikimedia.org/wiki/File:Cones_SMJ2_E.svg).

This range therefore corresponds broadly with the colours you can see looking
at a [rainbow](https://en.wikipedia.org/wiki/Rainbow) or at [warm light](https://en.wikipedia.org/wiki/Standard_illuminant#Illuminant_series_D)
through another type of [prism](https://en.wikipedia.org/wiki/Prism_%28optics%29):
[red](https://en.wikipedia.org/wiki/Red) is towards the 420 THz end of the band,
having a wavelength of up to about 700 nm, and [violet](https://en.wikipedia.org/wiki/Violet_%28color%29)
towards 750 THz (with a much shorter wavelength of about 400 nm).

Radiation outside of this range is all around us, but humans can't see it
directly: for example [infrared](https://en.wikipedia.org/wiki/Infrared) lies
just below the visible light band, and [ultraviolet](https://en.wikipedia.org/wiki/Ultraviolet)
just above it, although all electromagnetic radiation follows the same rules
(even if we are still figuring out what some of them are).

If you're speaking about radiation of a single wavelength, then its _colour_
could perhaps be said to be defined by its wavelength: reds are one band of
frequencies, oranges a little further along, then yellows, greens, blues,
indigos, and finally violets. Indeed, the colour of [laser](https://en.wikipedia.org/wiki/Laser)
light is [usually specified in terms of its wavelength](https://en.wikipedia.org/wiki/List_of_laser_types).

But lasers are quite special in that they're designed (to the extent
possible) to [emit only one wavelength of light](https://en.wikipedia.org/wiki/Monochromatic_radiation):
that's not a property shared by the most of the light sources humanity has
experienced throughout the majority of its existence. Moreover, there are
colours that don't appear in a rainbow: you may have heard for example that
[magenta "doesn't exist"](https://www.bbc.co.uk/reel/video/p0f00wp9/magenta-the-colour-that-doesn-t-exist).

#### I can sing a rainbow…

In a (very real) sense, you can think of each of the colours of the rainbow as being like a
[pure sine-wave tone](https://en.wikipedia.org/wiki/Pure_tone) at a particular
[pitch](https://en.wikipedia.org/wiki/Pitch_%28music%29), and the _names_ of
the colours are sort of like the names of musical notes, [a subject which rivals this for complexity](https://en.wikipedia.org/wiki/Musical_tuning#Tuning_systems).
And just as most sounds we hear don't consist of single, pure sine-wave tones,
most light we see doesn't either.

Radiation from the Sun is emitted across [quite a broad spectrum of wavelengths](https://scied.ucar.edu/interactive/sun-compare-multispectral),
which is to say it produces waves of electromagnetic radiation at [many different frequencies simultaneously](https://en.wikipedia.org/wiki/Black-body_radiation):
you probably knew that "white" sunlight is not any one colour in the rainbow,
but all of them mixed together (indeed, it _has_ to be all of them mixed
together, because that's what a rainbow shows you). A significant 
[proportion of the radiation is scattered and deflected by the Earth's atmosphere](https://en.wikipedia.org/wiki/Solar_irradiance#Absorption_and_reflection)
before reaching us on the surface, although [not all of the harmful radiation](https://en.wikipedia.org/wiki/Health_effects_of_sunlight_exposure)
is filtered before it gets here.

It's generally unwise and counterproductive to [look more than fleetingly at the Sun](https://www.astronomy.com/observing/some-of-the-the-science-behind-why-you-should-never-look-directly-at-the-sun-without-proper-eye-protection/),
and given that light travels in straight lines, most of the daylight we see has
not come directly from our star to our eyes, but instead has reached us after
it's interacted with some matter—[such as that floating around in the atmosphere](https://en.wikipedia.org/wiki/Rayleigh_scattering),
or the environment around you—and each of those interactions will alter the
light in some way.

You probably remember learning at school that the colours of _things_ are dictated by
which wavelengths of light they absorb and which they [reflect](https://en.wikipedia.org/wiki/Reflection_(physics)#Reflection_of_light),
and this—depending upon your point of view—you may find to be a perfectly good model
or one that leads to be more questions than answers (such as "what does it mean for a
_photon_ to be _reflected_ by an _atom_? are atoms… shiny?")

#### Quantum quantum quantum

A complete picture of photon-matter interactions is
[probably](https://en.wikipedia.org/wiki/Optical_phenomenon)
[beyond](https://en.wikipedia.org/wiki/Optical_tweezers)
[the](https://en.wikipedia.org/wiki/Attosecond_physics)
[scope](https://en.wikipedia.org/wiki/Coherent_perfect_absorber)
[of](https://pubs.acs.org/doi/10.1021/acsami.1c02368)
[this](https://www.nrc.gov/docs/ML1122/ML11229A667.pdf)
[document](https://phys.libretexts.org/Bookshelves/Quantum_Mechanics/Quantum_Mechanics_III_(Chong)/05%3A_Quantum_Electrodynamics/5.04%3A_The_Electron-Photon_Interaction),
but [one way to look at it](https://en.wikipedia.org/wiki/Quantum_electrodynamics)
is that _all_ of the wave packets that manage to collide with matter (rather
than zipping through it unimpeded) are absorbed. The difference is what happens
to that energy: one option is that the it's turned into heat.  It's probably 
fair to say that _most_ radiation that collides with matter is absorbed by it
and converted to heat.

(Matter which absorbs _all_ light within the visible spectrum in this way would
appear completely black to human vision no matter the light shone upon it; it's
[highly sought-after for some applications](https://en.wikipedia.org/wiki/Super_black),
and remains (appropriately) elusive).

But converting the photon's energy into kinetic energy is just one option. If
the photon is energetic enough (so depending upon its wavelength),
having [just the right energy](https://en.wikipedia.org/wiki/Color_of_chemicals)
that an electron absorbing it would be able to jump up to another energy level, then that jump
and subsequent fall back will result in the emission of more electromagnetic 
radiation: i.e., a new photon. Reflection, [refraction](https://en.wikipedia.org/wiki/Refraction), and
[photoluminesence](https://en.wikipedia.org/wiki/Photoluminescence)
[can all be thought of](https://en.wikipedia.org/wiki/QED:_The_Strange_Theory_of_Light_and_Matter)
[as variations on this same process](https://physics.stackexchange.com/questions/2041/how-are-classical-optics-phenomena-explained-in-qed-snells-law),
where the direction, wavelength, and in the case of [phospheresence](https://en.wikipedia.org/wiki/Phosphorescence),
the number of emitted photons and over what duration, differ.

The colour of something could therefore be defined as being the combined
intensities (number of photons) emitted by this process at all visible
wavelengths over some specified short period of time—and if you pointed
a [spectrometer](https://en.wikipedia.org/wiki/Optical_spectrometer) at
it, you'd get just that data which could be plotted on a chart that would
tell you how much light was emitted by it across the visible wavelengths
(and depending on the equipment, quite far beyond)—exactly like an audio
[spectrum analyser](https://en.wikipedia.org/wiki/Spectrum_analyzer#Audio-frequency_uses) shows
you how much bass, mid-range, or treble is in a sound signal.

But if you tried to measure the same thing again a few hours later, you'd likely
find you get very different data: this is because the relative amounts of
light at different wavelengths being emitted still depends upon the relative
amounts being absorbed—what we might call "environmental factors" generally,
but in the case of light and colour, we can be more specific: [lighting conditions](https://en.wikipedia.org/wiki/Color_temperature#Categorizing_different_lighting)—which
we'll come back to later.

You could try to arrange for consistent lighting conditions before trying to
take your spectrogram, but [for the most part](https://en.wikipedia.org/wiki/The_dress)
humans are able to tell what colour something is without doing that. You could
say that colour seems to be relative.

#### Look into my eyes and tell me what you see

Before you can even look at the spectrogram of your colour, we have to deal
with what happens when these photons actually reach your eyes. Humans, like
[many primates](https://en.wikipedia.org/wiki/Evolution_of_color_vision_in_primates),
typically have [red-green-blue trichromatic vision](https://en.wikipedia.org/wiki/Trichromacy),
which means we have red-sensitive, green-sensitive, and blue-sensitive [cones](https://en.wikipedia.org/wiki/Cone_cell)
in our retinas, all of which generate signals in our optic nerves
simultaneously, the intensities of which depending upon the amount of light in
their respective ranges that they receive.

There are two interesting cases here: one is [magenta](https://en.wikipedia.org/wiki/Magenta),
mentioned above. It's the colour we see when approximately equal amounts of red
and blue, but not green, hit our retinas. The existence of [fuchsias](https://en.wikipedia.org/wiki/Fuchsia) in nature
is enough to tell us that this colour is very much _real_, but it's not a single "note"
in the same way as a hue that appears in the rainbow.

With our sense of hearing, humans have the ability to focus in on one part of
the audible spectrum, allowing us to pick out individual sounds or voices in
a rich soundscape, but with very limited spatial awareness. If you were able
to turn your spectrogram's output into a [continuous wave](https://en.wikipedia.org/wiki/Fourier_inversion_theorem),
you would have a signal that you could play as audio, and it would produce a
distinct sound for each colour of light that you pointed it at, but you would
only be able to point it at one colour at a time—your brain might be able to
perform clever tricks with sound, but the _information density_ of colour vision
is huge in comparison—we can't see magenta as "red _and_ blue", but we _can_ see
a whole field of vision's worth of colours simultaneously and distinguish them.

Being able to mentally decompose what we see into reds, greens, and blues so that
you could tell that magenta was "lots of red and lots of blue but not green"
would be a neat trick, but probably wouldn't have conveyed any evolutionary
benefit as compared to what happens now: we see magenta.

Vision varies hugely [across the animal kingdom](https://en.wikipedia.org/wiki/Eye).
Many species can distinguish fewer colours than we typically can, because they have
[dichromatic](https://en.wikipedia.org/wiki/Dichromacy) or even
[monochromatic](https://en.wikipedia.org/wiki/Monochromacy) vision; others
have a [broader or quite different range](https://en.wikipedia.org/wiki/Tetrachromacy#Pentachromacy_and_greater)
to humans.  Jumping spiders have been [studied quite extensively](https://youtu.be/nfAqTSjMBJk?si=kSJKI5gp0HKXUJhG)
in part because different sub-species have evolved trichromatic and tetrachromatic
vision multiple times, sometimes employing the same mechanisms, sometimes
novel ones.

The cones in our retinas do not respond only to light at one specific frequency
and no other, but instead have a [_response curve_](https://en.wikipedia.org/wiki/Frequency_response),
which peaks at a particular frequency, but then falls off as you move away from
it in either direction. As with most things to do with our eyes, the precise
response curves for the photoreceptors in your retinas are dependent on
genetics and age.

These response curves have tradeoffs: if the response curve for one of the sets
of photoreceptors is very broad, then you might be able to see a wider range of
colour, but have a harder time distinguishing hues, because the broader range
means there are more combinations of light wavelengths that resulting in the
same intensity of response being sent down your optic nerve.

#### Is all that glisters really gold?

But these response curves bring us to the other interesting case: [yellow](https://en.wikipedia.org/wiki/Yellow).
Yellow _does_ appear in the rainbow, right where you'd expect it to be at roughly 580 nm. But
we don't have yellow photoreceptors: instead, we _infer_ yellow when green cones
and the red cones in the same part of our retinas are stimulated at the same
time a great deal and the blue cones aren't—in the exact same way that we
_infer_ the existence of magenta.

Does this mean there are two different _kinds_ of yellow? The yellow in the
rainbow—"pure yellow", if you will—and the yellow that we perceive when we
see a combination of red and green? Yes—and we have no way of telling them
apart with our eyes. Fortunately, we can use this to our advantage, which we'll
come back to in a moment.

You may have been told once that the [primary colours](https://en.wikipedia.org/wiki/Primary_color)
are "red, blue, and yellow", and you may also have been told that it's wrong
and that they're not. We know that we have red, green, and blue photoreceptors,
so where on earth does this red-blue-yellow thing come from?

This is one of those things that is simultaneously correct and incorrect.

Imagine that you were to draw a circle, and then found the largest equilaterial
triangle that could fit within it, and put bright red at one corner of it, bright
green at another, and bright blue at the third. Then, halfway between red and blue,
you put bright magenta. Between red and green you put bright yellow. Between green
and blue, bright cyan. This arrangement probably looks quite familiar: it's a
standard [colour wheel](https://en.wikipedia.org/wiki/Color_wheel), and the
relative positions of the hues are ultimately defined by how our eyes work,
although colour wheels [predate that understanding](https://en.wikipedia.org/wiki/Opticks).

If you look at the spots on the colour wheel halfway between red, green,
and blue, you'll see they're cyan, magenta, and yellow: these three primaries,
together with black, are used for [CMYK](https://en.wikipedia.org/wiki/CMYK_color_model)
printing, _the_ standard modern [colour printing process](https://en.wikipedia.org/wiki/Color_printing).

So yellow _is_ a primary colour? Or isn't it?

It's probably worth clarifying what we mean by "primary colour". And also
probably "red" and "blue" in this context.

At its simplest, a primary colour is one that you mix with other primary
colours to make different colours: its definition then depends a great deal
on context. If you're working with paints, you can mix varying quantities of
red, blue, and yellow to get a reasonable range of colours.

If you look at magenta and red on the colour wheel, you don't need to move
them a great deal closer together (adjusting their hues as you do) before
they start to look like roughly the same sort of pinkish hue, and the same
happens with cyan and blue as well.

We talk about _reds_ and _blues_ as whole families of colours, but you'd
very rarely talk about _magentas_ or _cyans_, and so part of the story is
that "red-yellow-blue" and "cyan-magenta-yellow" are really talking about
the exact same thing—it's just that when you're talking about modern
printing processes, we can be more precise.

But why _yellow_? And _why_ are these primaries rotated?

What we're looking at here is not really about rotation—showing the three
sets of primaries on the same colour wheel is a little bit of a red herring,
but rather _inversion_: CMY(K) and RGB are not just different colour models
with different primaries, but different _kinds_ of colour model: [additive](https://en.wikipedia.org/wiki/Additive_color)
and [subtractive](https://en.wikipedia.org/wiki/Subtractive_color). In other
words, we use cyan, magenta, and yellow, because they're the inverse of red,
green, and blue respectively.

Much of our understanding of colour was derived not from understanding how
light or our optical cells behave necessarily, but how [pigments](https://en.wikipedia.org/wiki/Pigment)
do: and in particular, how to mix pigments, [paints](https://en.wikipedia.org/wiki/Paint),
and [dyes](https://en.wikipedia.org/wiki/Dye) to arrive at one which
[_reflects_](https://en.wikipedia.org/wiki/Diffuse_reflection) a desired colour.
As a consequence, these colour models are _subtractive_, because as you add more
pigment, the darker the result gets.

(The "K" or "key" in CMYK printing refers to the use of a specific blank ink
or toner alongside the other three: partly because this is more much more
efficient when much of what is printed is black text, but also because it
produces "blacker blacks" than simply mixing lots of cyan, magenta, and
yellow together).

In an subtractive model, the biggest factor in how many primaries you use is
cost: because we have three sets of photoreceptors, three is the _minimum_
you can use to achieve a broad gamut, but you [don't have to stop there](https://en.wikipedia.org/wiki/Hexachrome).

Most of what follows pertains to additive, rather than subtractive, colour
models, because the focus is on on-screen colour, but knowing about subtractive
models is still useful.

#### Photo... synthesis

For the longest time, incandescence was [the hottest thing in light production](https://www.english-heritage.org.uk/visit/inspire-me/blog/blog-posts/history-of-lighting/):
either by [setting things on fire](https://en.wikipedia.org/wiki/Candle), or by
[trying very hard to _not_ set them on fire](https://en.wikipedia.org/wiki/Incandescent_light_bulb).
This was variously inefficient, extremely imprecise from a colour perspective
(despite valiant efforts involving [translucent gels](https://en.wikipedia.org/wiki/Color_gel)),
and quite perilous when it came to the whole naked flame thing; yelling "fire!"
in a crowded theatre was something that unfortunately had to happen quite a lot.

As well as great leaps in theoretical physics, the 20th century also heralded
significant developments in [photographic](https://www.youtube.com/watch?v=wbbH77rYaa8&list=PLv0jwu7G_DFV6yW240e6CbiwCLaZ0Z6PV&pp=iAQB),
[movie production](https://en.wikipedia.org/wiki/Color_motion_picture_film), and
[television](https://www.youtube.com/watch?v=l4UgZBs7ZGo&list=PLv0jwu7G_DFUGEfwEl0uWduXGcRbT7Ran&pp=iAQB)
technology, all of which help form the foundation of our understanding of light and colour today.
Perhaps knowing what you do now about photons and electrons,
the idea of making pictures appear on a screen by firing [an electron beam](https://en.wikipedia.org/wiki/Electron_gun)
at [phosphors](https://en.wikipedia.org/wiki/Phosphor) to [excite them into giving off photons](https://en.wikipedia.org/wiki/Cathode-ray_tube)
doesn't seem all that wild.

Thankfully, given the picture size of contemporary televisions, [interesting states of matter](https://en.wikipedia.org/wiki/Liquid_crystal) 
and [semiconductors](https://en.wikipedia.org/wiki/Light-emitting_diode) have
rendered the vacuum tube-based display technologies obsolete for all but the
most niche of applications. Nowadays, the biggest difference between televisions
and computer monitors is that the former come with a computer built-in: for
the most part, a TV, a laptop, a desktop monitor, a phone, and a tablet can
all use the same display technologies, and what follows is generic enough to
apply to all of them.

Colour is reproduced on screens somewhat analogously to the way that video is:
by doing just enough to provide the right _sorts_ of signals that your brain 
(or eyes) will interpret to get the desired result, whether that's by displaying
a sequence of still images quickly enough that it looks like smooth motion, or
by emitting combinations of red, green, and blue light that fool your retinas
into seeing a huge range of hues and shades.

And it's not that a display can produce different _shades_ of red,
green, or blue in each of its [pixels](https://en.wikipedia.org/wiki/Pixel):
only the _intensity_ of each can be varied, the wavelengths are fixed. Just
by varying those intensity levels, light can be produced that _looks to us_
like hot pink, or deep teal, or bright white, or yellow. When you see
[yellow on screen](https://commons.wikimedia.org/wiki/File:Cornwall_Daffodils.jpg),
you're seeing red and green sub-pixels really close together, closely
enough that you can't distinguish them. It's not even that your _brain_ is
being tricked, so much as the cones in your retinas: they [simply can't tell the difference](https://commons.wikimedia.org/wiki/File:Cone-fundamentals-with-srgb-spectrum.svg)
between "red and green photons arriving together in the same part
of your field of vision" and "yellow photons arriving".

#### I see fields of green, red roses too...

Most of us know from first-hand experience that this approach of tricking
us into seeing motion and colour works pretty well in general, but
it's not without challenges.

First, there is the _gamut_ of a display: that is, the range of colours it
is able to reproduce. There are many colours that displays _cannot_ reproduce.
If you want to _specify_ colours, it's therefore important that you work
within the gamut of the device that will display (or print) them.

Second, there's _consistency_: every display is different, most are not
professionally calibrated, and rigour of factory calibration can vary
wildly. Consistency is even more challenging if you need to reproduce
colours between media: for example when devising a palette that needs
to be suitable for both web and print use, for example.

Third, there's _subjectivity_: every single human's eyesight and colour
vision and different. We have common reference points, but that doesn't
mean we _see_ the same colours: we might look at the same patch of grass
and agree that it's a rich green, but we have no way of knowing that we
see it exactly the same way, especially not in relation to other colours.

If you were to take a photo of that same patch of grass, you'd immediately
notice that it doesn't look quite the same on your phone's screen as it does
right in front of you. With careful adjustment of filters and white balance,
you manage to get it close, but there's still something not quite right. Why?

Partly this is down to your phone's display and the range of colours its
pixels are capable of reproducing, but also your phone's camera, which will
have it's own gamut (which may not entirely line up with the display's), 
and our old friend lighting conditions play a big role in both the capture
of the photo and how colour appears on a display.

There are also limits to how much all of this can be compensated for in
post-processing (either through manual adjustments to the photo, or as
a result of intelligent display adjustment technology, the sort increasingly
found in higher-end phones and laptops).

Fortunately, improvements in camera, display, and print technology in recent
decades have come hand in hand with improvements to the ways that we
represent and manage colour in digital systems. It wasn't that long ago that
colour values in web pages or image files were interpreted as being, in effect,
the raw RGB values to send to your computer monitor, regardless of its
characteristics. Nowadays, the values are interpreted as existing within a
_reference space_, specifically [sRGB](https://en.wikipedia.org/wiki/SRGB), and
then _transformed_ into a colour space specific to the target device, using
a [colour profile](https://en.wikipedia.org/wiki/ICC_profile)—virtually every
device capable of reproducing colour sold in the last two decades has a colour
profile available for it.

#### It's a match!

The combination of colour profiles and reference spaces has greatly improved
our ability to achieve consistency across a range of devices. Meanwhile,
contemporary image and video formats don't typically store red, green, and blue
values at all, but instead use a differently-arranged colour model to suit their
needs (such as [Y'CbCr](https://en.wikipedia.org/wiki/YCbCr)), which will often
have a much wider theoretical gamut than any output device.

But plenty of challenges remain: colour profiles, like factory calibration,
vary significantly in quality; and more importantly, they are only ever the
"average". How much this matters depends upon the application: if you care
that the photo you just took will look pretty much like you see it on you
screen when you send it to a friend, colour profiles have basically solved
this problem. If you're a professional designer, or a filmmaker, or a TV
graphics editor, or somebody designing safety-critical systems, then they
help, but only so much.

How do you find complementary colours in RGB? How do you increase lightness
and decrease intensity? How do you guarantee minimum contrast levels in a
range of lighting conditions? How do you guarantee those contrast levels when
the colours are printed onto a reflective metal roadsign?

Colour systems such as those from [PANTONE](https://www.pantone.com/) and
[RAL](https://www.ral-farben.de) have been the traditional answer to these
questions, and will doubtless continue to be for some time to come. They work
by defining what is now a huge number of named colours, and for each have
specified not only the red, green, and blue values for on-screen use, but also
the specific combinations of different kinds of inks needed to achieve
consistent results. They also provide physical samples in a variety of forms,
and support many different kinds of inks—many with a gamut far outside
of sRGB. In these cases the RGB values are considered to be just a rough
approximation, like a low-resolution preview (but the resolution is
colour space instead of phsyical dimensions) and professionals will rely
on the physical samples and published specifications, which will include
information about contrast levels under different lighting conditions.

Systems of this scale are not produced without some significant human effort,
but rely on colour models to do a lot of heavy lifting. Whilst RGB is _one_
family as models, there are others—as mentioned above—and the choice of
model is defined by what mathematical properties it exhibits. For example,
whether "lightness" is defined as a single axis, or computed from a combination
of axes as it is in RGB.

And whilst you can straightforwardly compute hue, saturation and lightness values
from sRGB primaries and vice versa, there's no requirement that any colour model
have a _linear_ relationship with sRGB, and indeed most don't.

sRGB, to use as an example, means that we have a pretty good idea of what
wavelengths of light will be emitted by a display for a given set of RGB
colour values (on average, with error bars, and so on). But how well
do those wavelengths actually match up with human photoreceptors? How
much does that vary? How much does that _matter_?

### Colour appearance modelling

As noted in the introduction, the current version of Stardust was developed using
a [colour appearance model](https://en.wikipedia.org/wiki/Color_appearance_model) (or _CAM_),
and specifically the J<sub>z</sub>a<sub>z</sub>b<sub>z</sub>
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
you represent your RGB values) and gets "clipped" at that level. [High Dynamic Range](https://www.bbc.co.uk/rd/projects/high-dynamic-range)
displays (and their accompanying colour models) have a broader gamut,
and so an sRGB "1.0" is not the same as an HDR "1.0".

In appearance models, the aim is that distance between points within the colour
space is proportional to the _perceived_ difference between those two shades.
In practice, it is impossible to arrive at a single model that is
straightforward to work with, produces meaningful values at a wide range of
chromacity and brightness levels, and accurately represents the appearance
differences between shades on real-world devices under various different
realistic viewing conditions.

These limitations, coupled with the limited and uneven gamut of sRGB, means
that it's not sufficient to simply select some defined brightness and intensity
levels, and then split the colour wheel up evenly: at higher intensity levels,
there's a higher chance of straying outside of sRGB's gamut—but it's more
pronounced with some hues than others. Where this happens, you have multiple
distinct colours (in your source colour space) that end up with the same
sRGB values. Meanwhile, some shades need to have their intensity _increased_
in order to appear evenly-matched with others at the same notional intensity
and brightness level.

Rather than complicate the palette definition by using different models for the
different colour variants, the current version of Stardust is defined using a
single general-purpose model, and then a series of adjustments are applied to
specific shades. Without a significant amount of data gathering and analysis, this will
remain the most subjective aspect of the process. Fortunately, colour appearance models
are an active area of research, and so hopefully future versions of Stardust can
be more data-driven.

### Colour naming

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

### Build process

All of the files in this repository that are influenced in some way by the
individual colour values in the Stardust palette were generated by a fairly
extensive (if not necessarily good quality from a coding standards
perspective) Python tool, whose role could be best characterised as a
"colour publication system", and was written specifically for this purpose.

For multiple reasons, it's unlikely that this code will be released as
open source, and on a practical basis, describing what it does and how it
works is arguably much more useful.

The tool, called _Chromatik_, processes JSON files as input and produces
various kinds of output — SVG renderings of the palette, an Objective-C
program that will create and save an NSColorList, the CSS variables, and
so on.

Each JSON file, which specifies a _Colourset_, may contain:

* Global options (the title of the palette, which formats to generate plots in, etc.)
* Specific colours, with their values specified in any supported colour space
* _Variants_ of those colours (e.g., "Pastel gold"), whose values are specified in the same way
* Colour _generation_ parameters
* _Bulk adjustment_ parameters to create variants that weren't explicitly specified
* _Imports_ of other Coloursets; the import may be restricted to particular hues, variants, or even individual colours
* _Individual adjustments_ to make to specific colours

A colour's values can be specified in more than one space simultaneously;
Chromatik will only convert values from one space to another if they're not
already specified. Unfortunately, this also means that no checks are performed
to confirm that the supplied values are all within a reasonable range of
each other—supplied values are simply assumed to be canonical.

In more extensive palettes such as Stardust's, a colour as specified at 
the top level of a Colourset is taken to be the _base_ shade of that hue:
"Spearmint" or "Lime" for example. Each hue can then have any number of
variant shades. Different hues don't all need to have the same variants,
but if bulk-adjustment parameters were specified for a particular variant,
then all hues will have a colour generated in that variant if one isn't
already specified.

Those "bulk-adjustment parameters" are simply absolute or relative values
in one or more of a colour space's axes. For example, a pastel variant
might be specified as 5% chroma and 95% brightness in the J'C'h' space,
which is the polar form of J'a'b' — Chromatik simply takes the base shade,
converts it into whichever colour space the adjustment is to be performed
in, applies the adjustments to those values as specified in the JSON,
and creates a new colour object from those values, and attaches it to the
base shade's object as a variant.

Individual adjustments work the same way, but target a specific colour
once all generation has happened. Individual adjustments can also rename
a colour if the scheme doesn't fit in an individual case: for example,
we always refer to white as "white" and not "pastel grey" or something.

Generation happens in a similar way to adjustment, albeit prior to it:
the JSON specifies the colour space, the number of divisions, and which
axes have fixed/limited range; the JSON specifies a list of name
mappings, either as an array or a dictionary; if a dictionary, one of
the axes (e.g., the hue angle) is used as the lookup key — this means
that if the range or number of divisions is altered, the names won't
get out of sync with the colours themselves (as long as their hues were
still in the generated set). Manually-specified colours will always
_override_ generated colours.

One Colourset can import another, either in whole or part. Imports can
be limited to specific individual colours, particular hues as a whole,
and particular variants. Stardust works in this way: its JSON file
doesn't contain any colour values, nor adjustments, nor generation
parameters, just imports and information about the various outputs
that should be produced. Indeed, splitting the palette up into
multiple source files in this way is what makes it feasible to derive
Stardust as a subset in the first place. Imports happen before adjustments
are applied to the Colourset doing the importing, which means it can
perform _additional_ adjustments on top of those already applied.

Once a Colourset has been loaded, including all of its imports, it's
passed through various _generators_, which are simply Python classes
that turn Coloursets into useful output. A simple generator is the one that
writes the tab-delimited text file in this repository, for example. In the
Stardust build process, several generators are run in sequence and then
the results (including this README with its big table of colour values) are
copied to the Stardust public repository and the results committed.

This does have the slightly unfortunate side-effect (besides an unpleasant
commit log) of re-generating the SVG plots, which contain both embedded
timestamps _and_ random values (internal object identifiers), even if the
colour values haven't changed. Perhaps there's a way to prevent matplotlib
from doing that, or to only commit the SVGs if their PNG equivalents differ.

### Future direction

The palette from which Stardust is specified consists of 72 hues in a number of
different chromacity/lightness variations, which is far too large for good
results by performing manual adjustments alone.

One approach might be that each individual axis of each adjustment is treated
as a kind of "adjustment layer" that applies to the whole colour space, but with
an intensity which drops off the further away (in the other two dimensions)
you get from the target colour, for example using the inverse-square law
multiplied by a spread factor (a spread of zero meaning it only applies to that
colour and none of its neighbours).

This approach would mean that rather than adjusting colours, the colour space
itself is adjusted, using the named colours as reference or anchor points. This
starts to sound a great deal like a colour profile, and so perhaps it would
be best to just learn how to specify and apply those instead.

## Colour values

The J<sub>z</sub>a<sub>z</sub>b<sub>z</sub> values are canonical. D65 is used as
the reference white point where relevant. RGB values are sRGB unless otherwise
noted.

The following table is also available in [tab-delimited text format](Values/Stardust.txt?raw=true).

|        Name        |    Hex    |  R   |  G   |  B   |  L*  |  a*  |  b*  |   Jz   |   az    |   bz    |
| ------------------ | --------- | ---- | ---- | ---- | ---- | ---- | ---- | ------ | ------- | ------- |
|            Pumpkin | `#c13e28` |  193 |   62 |   40 |   46 |   51 |   42 |  0.111 |  0.0806 |  0.0806 |
|   Midnight pumpkin | `#3f0600` |   63 |    6 |    0 |   10 |   26 |   17 | 0.0333 |  0.0424 |  0.0424 |
|       Dark pumpkin | `#670a00` |  103 |   10 |    0 |   20 |   39 |   34 | 0.0555 |  0.0636 |  0.0636 |
|      Vivid pumpkin | `#ff5034` |  255 |   80 |   52 |   71 |   85 |   68 | 0.1749 |  0.1167 |  0.1167 |
|     Pastel pumpkin | `#ffe0d2` |  255 |  224 |  210 |   94 |   17 |   14 |  0.211 |  0.0255 |  0.0255 |
|               Gold | `#9c7200` |  156 |  114 |    0 |   50 |    6 |  112 |  0.111 |    -0.0 |   0.138 |
|      Midnight gold | `#2d2000` |   45 |   32 |    0 |   13 |    1 |   26 | 0.0333 |    -0.0 |    0.06 |
|          Dark gold | `#4d3700` |   77 |   55 |    0 |   24 |    3 |   51 | 0.0555 |     0.0 |    0.09 |
|         Vivid gold | `#ffc600` |  255 |  198 |    0 |   83 |    7 |  154 | 0.1833 |     0.0 |   0.165 |
|        Pastel gold | `#fef3c7` |  254 |  243 |  199 |   96 |   -3 |   23 |  0.211 |    -0.0 |   0.036 |
|               Lime | `#009c16` |    0 |  156 |   22 |   56 |  -61 |   53 |  0.111 | -0.0849 |  0.0849 |
|      Midnight lime | `#002f00` |    0 |   47 |    0 |   15 |  -30 |   24 | 0.0333 | -0.0424 |  0.0424 |
|          Dark lime | `#005000` |    0 |   80 |    0 |   28 |  -43 |   41 | 0.0555 | -0.0636 |  0.0636 |
|         Vivid lime | `#00f02e` |    0 |  240 |   46 |   83 |  -83 |   72 | 0.1666 | -0.1061 |  0.1061 |
|        Pastel lime | `#d6ffd4` |  214 |  255 |  212 |   97 |  -23 |   18 |  0.211 | -0.0255 |  0.0255 |
|          Spearmint | `#00a87c` |    0 |  168 |  124 |   57 |  -85 |    7 |  0.111 |   -0.12 |    -0.0 |
| Midnight spearmint | `#003423` |    0 |   52 |   35 |   16 |  -42 |    3 | 0.0333 |   -0.06 |    -0.0 |
|     Dark spearmint | `#00573c` |    0 |   87 |   60 |   29 |  -62 |    5 | 0.0555 |   -0.09 |     0.0 |
|    Vivid spearmint | `#00ffc0` |    0 |  255 |  192 |   85 | -118 |    9 | 0.1666 |   -0.15 |     0.0 |
|   Pastel spearmint | `#b9fff2` |  185 |  255 |  242 |   98 |  -28 |    3 |  0.211 |  -0.036 |     0.0 |
|                Sky | `#008fc3` |    0 |  143 |  195 |   53 |  -32 |  -41 |  0.111 | -0.0849 | -0.0849 |
|       Midnight sky | `#002b3d` |    0 |   43 |   61 |   14 |  -17 |  -18 | 0.0333 | -0.0424 | -0.0424 |
|           Dark sky | `#004867` |    0 |   72 |  103 |   26 |  -22 |  -28 | 0.0555 | -0.0636 | -0.0636 |
|          Vivid sky | `#00dcff` |    0 |  220 |  255 |   78 |  -41 |  -58 | 0.1666 | -0.1061 | -0.1061 |
|         Pastel sky | `#c1feff` |  193 |  254 |  255 |   96 |  -15 |  -14 |  0.211 | -0.0255 | -0.0255 |
|           Bilberry | `#6356db` |   99 |   86 |  219 |   45 |   41 |  -67 |  0.111 |    -0.0 |   -0.12 |
|  Midnight bilberry | `#181546` |   24 |   21 |   70 |   10 |   18 |  -30 | 0.0333 |     0.0 |   -0.06 |
|      Dark bilberry | `#2c2475` |   44 |   36 |  117 |   20 |   29 |  -46 | 0.0555 |    -0.0 |   -0.09 |
|     Vivid bilberry | `#816bff` |  129 |  107 |  255 |   70 |   97 | -143 | 0.1833 | -0.0296 | -0.2079 |
|    Pastel bilberry | `#cce1ff` |  204 |  225 |  255 |   90 |    5 |  -29 | 0.2005 | -0.0067 | -0.0474 |
|              Lilac | `#aa12b7` |  170 |   18 |  183 |   42 |   72 |  -50 |  0.111 |  0.0827 | -0.0827 |
|     Midnight lilac | `#35003a` |   53 |    0 |   58 |    8 |   36 |  -24 | 0.0333 |  0.0424 | -0.0424 |
|         Dark lilac | `#590061` |   89 |    0 |   97 |   18 |   53 |  -36 | 0.0555 |  0.0636 | -0.0636 |
|        Vivid lilac | `#e43af4` |  228 |   58 |  244 |   58 |   84 |  -59 | 0.1499 |  0.0902 | -0.0902 |
|       Pastel lilac | `#ffdbff` |  255 |  219 |  255 |   93 |   24 |  -18 |  0.211 |  0.0255 | -0.0255 |
|          Raspberry | `#bb1f71` |  187 |   31 |  113 |   42 |   64 |   -7 | 0.1082 |   0.102 |     0.0 |
| Midnight raspberry | `#40001f` |   64 |    0 |   31 |    9 |   37 |   -4 | 0.0333 |    0.06 |    -0.0 |
|     Dark raspberry | `#6a0037` |  106 |    0 |   55 |   18 |   54 |   -6 | 0.0555 |    0.09 |     0.0 |
|    Vivid raspberry | `#ff21a0` |  255 |   33 |  160 |   59 |   86 |   -9 | 0.1499 |  0.1275 |    -0.0 |
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


## Plots

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
