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
2. Add a Colour Space Transform node to your footage. Convert to ARRI Wide Gamut Version 3, and ARRI LogC Version 3.
3. Turn DaVinci's Garbage Tone Mapping to None.
5. Place a DCTL node after the footage. Select the Camera-AgX DCTL.
6. Experiment.

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

## Working Log Encoding
Log-like transfer for the working space.

## Output Primaries
Output primaries encoding.

## Working Middle Grey
Working middle grey point. Set to the working middle grey encoded value of the Working Log Encoding.

## Log Encoded Output
Toggle to control whether to encode to the Working Log Encoding with Output Primaries for the output
