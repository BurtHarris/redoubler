# REDOUBLER-DIY

[REDOUBLER](https://github.com/alwynallan/redoubler) is  Peter Allan's  deisgn for a hardware Random Number Generator, which I have forked this project from.   The device plugs into a host's USB port, and enumerates as a standard microphone. The assertion Peter has made is that the output of this pseudo-microphone is effectively white noise which contains a high proportion of random entropy, and that it can be recorded and used for any purpose that requires a non-deterministic entropy source.  If this is an accurate analysis of the device's behavior, it could be useful in addressing certain cryptographic vulnerabilities which have been documented over the past several years.

REDOUBLER-DIY is an easy-to-assemble version of REDOUBLER which requires no custom printed circuit boards or tricky soldering of surface mount devices.  It was assembled with the original designer's support and advice.   This version starts with a $10  [Cypress CY8CKIT-059](http://www.cypress.com/documentation/development-kitsboards/cy8ckit-059-psoc-5lp-prototyping-kit-onboard-programmer-and)  prototyping kit.   The kit is available direct from Cypress, or through [DigiKey](http://www.digikey.com/product-detail/en/cypress-semiconductor-corp/CY8CKIT-059/428-3390-ND/5184557).   Some other distributors have it available, but are  charging a higher price.  I've added just eight 1% tolerance resistors to the kit in an attempt to duplicate REDOUBLER's behavior.     Assembled, my prototype looked like this:

![REDOUBLER-DIY, hand built](images/WP_20160626_15_29_31_Pro.jpg?raw=true "assembled")

After some initial debugging, a small change was made in the resistor connections, the next photo shows the resistor wiring which corrected a mistake I made.

![close up of resistors](images/WP_20160629_21_06_49_Pro.jpg?raw=true "resistors")

Once assembled correctly, and running a version of the REDOUBLER's firmware, measurement of the voltage at the junction of each pair of resistors (the op-amp's inverting input) shows an interesting looking signal as shown below: 

![oscope trace of op-amp inverting input](images/WP_20160629_21_10_32_Pro.jpg?raw=true "scope")
![oscope trace of op-amp inverting input](images/WP_20160629_21_12_33_Pro.jpg?raw=true "scope")

But listening to the "sound" output from my Redoubler, I detected a sort of odd tone to it.   You can find my recordings in the data directory.   I used Audicity to record the data, resetting the board between files.   Analyzing them carefully showed they were periodic, but that is sometimes more obvious than others.        

Here's a time series and frequency analyis of pseudonoise.wav.   This one "sounds" like noise to my ears, but performing a frequency analysis shows there is a repeating pattern to the noise-like data.

![Pseudo Noise](images/pseudonoise.png)

Other times after pressing reset it sounded more like a square wave to me.   To my surprise looking at the data, it wasn't even close, but it in this case the repeating pattern is obvious in Audacity:

![Less noise like 1](images/Audacity1.png)
![Less noise like 2](images/Audacity2.png)

