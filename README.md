# Who Wrote This Code?

This code was written by Jed Smith and Juan Pablo Zambrano. The base I believe was written by Jed Smith, and Juan Pablo Zambrano added the AgX mechanisms.

This repository includes some minor changes by the repository owner.

# AgX-Resolve

AgX Picture Formation for DaVinci Resolve

# Who

If you don't know what this is, it probably isn't for you just yet.

# What

Provides a flexible picture formation chain for DaVinci Resolve users.

# When

Currently testing out some things for folks who happen to find this repository. Not quite baked fully just yet.

# Where

In your DaVinci Resolve application `LUT` folder, create a subfolder called AgX. Place both files in there, and refresh your DaVinci Resolve installation.

# Why

You'll have to take it for a try.

# How

  1. Install as per Where above.
      1. Insert a Colour Space Transform node *as required*.
      1. Turn DaVinci's Garbage Tone Mapping to None.
      1. Place the DCTL node after the CST. Select the Camera-AgX DCTL.
2. Experiment.

Note that defaults are set for colourists, and are tuned to:
  * ARRI Wide Gamut Version 3
  * ARRI LogC Version 3

That said, an author can set the values to whatever they choose, and the AgX mechanic will hold up.

# Parameters
These parameters work together, and thus one can expect any single parameter to drive other potential colour qualia.

## Attenuation Rate
Greater values increase the rate of chromaticity attenuation as tristimulus values ascend. Lower values will slow the rate of attenuation. Slower rates may induce posterization.

## Hue Flight
Controls the direction and rate of chromaticity angle flights. Value is degrees in CIE xy. Higher values will increase chromaticity angle flight speed toward the direction specified.

## Purity
Controls the general purity of the primary when processing is complete. Some colourimetries will yield values that are too strong, breaking the surface of the picture. To reduce purity, decrease value. For a complete round trip no operation, set to match the Attenuation Rate above.

## Contrast
General contrasts of specified regions.

## Input Primaries
Input CIE colourimetry primaries for the working space.

## Input Transfer Characteristic Encoding
Input transfer characteristic. Now you can avoid a CST if coming from an EXR.

## Working Log Encoding
Log-like transfer for the working space.

## Output Primaries
Output primaries encoding.

## Working Middle Grey
Working middle grey point. Set to the working middle grey encoded value of the Working Log Encoding.

## Log Encoded Output
Toggle to control whether to encode to the Working Log Encoding with Output Primaries for the output

# When using AgX Kraken...
Likely easiest to use the AgX Kraken DCTL directly with the proper defaults set.

If one wants to manually put the values in, the following settings *should* match the default output of AgX Kraken:
  * RGB Attenuation `0.2`
  * RGB Hue Flight: `0.0`
  * RGB Purity: `0.2` (Match Attenuation)
  * Shoulder Contrast: `3.25`
  * Toe Contrast: `3.0`
  * General Contrast: `2.0`
  * Working Middle Grey: `0.6061` (`6.5 / (6.5 + 10.0)`)