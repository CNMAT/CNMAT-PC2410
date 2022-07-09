# CNMAT-PC2410
A switchable pro to consumer pad for use with tactile transducer workflows

The PC-2410 accepts stereo Pro Level signals up to +24 dBu, pads them to -10 dBV and unbalances them for single-ended inputs.  

Often, composers working with a small budget buy the cheapest consumer amplifiers they can find--typically off the shelf class-D amplifiers that perform exceptionally well, are robust, small and portable.  The major drawback is that these amplifiers are designed for the consumer market.  Their "full-scale" (i.e. the point at which they start clipping) is typically -10 dBV, which is about 0.316 volts RMS or about 0.477 volts peak.  Usually, these amplifiers will tolerate up to 1 volt RMS on input, which is (exactly) 0 dBV or +2.2 dBu.  Depending on model, if you are lucky, they might even tolerate up to 2 volts RMS input, about +8 dBu or +6 dBV.  However, I have yet to encounter a consumer amplifier that can withstand the output signals of professional audio mixers and interfaces, which are designed to drive line signals up to +24 dBu (≈12.27 volts RMS).  In the best case, the amplifier will shut itself down when presented with such high input voltages.  In the worst case, the composer will hear a pop and smell burning as the amplifier blows its MOSFET.  Any composer who has worked with transducers has likely experienced something like this scenario.  All of a sudden, that cheap amplifier just doubled in price as it now needs to be replaced.


One of the most common failure modes when working with transducers is applying professional level signals to consumer level equipment, often to catastrophic consequence.  This is not something that is typically done in professional audio--the whole ecosystem is centered on turning things up, not down--so it turns out that there aren't all that many affordable ways to safely get a professional level balanced signal (+4 dBu and higher) into a consumer level (-10 dBV) unbalanced amplifier.  For this reason, I have devised a new tool I am calling the CNMAT PC-2410, which is designed to accept a balanced XLR or TRS input signal up to +24 dBu and pad that signal down to -10 dBV for use with consumer level amplifiers.   


The circuit consists of a switchable 32, 20 & 12 dB passive H-pad to drop the signal from +24, +12 and +4 dBu, respectively, to the necessary -10 dBV required by our consumer level amplifier. This padded signal is then unbalanced through a 1:1 audio transformer to provide reasonable impedance matching to our amplifier.


The files contained in this directory include all of the design files and gerbers for the circuit, PCB and enclosure.  As of this writing (June 2022) the main components are the following:


* XLR/TRS Jack:  Neutrik NCJFA-H combo jack
* RCA Jack: RCJ-2121
* Slide DP3T Switch: E•Switch 2315
* Transformer: Triad Magnetics TY-250P


All resistors are 1/4W unless otherwise specified.  Values are not included as of this writing (June 2022) pending changes during prototype fabrication, but will be chosen to provide the necessary padding of the signal while presenting a 600-720 ohm input impedance and good impedance matching to the transformer.  Given that variability in the transformer, impedance will affect the pad circuit, so all resistors have footprints that have been doubled in parallel to accommodate difficult to find resistor values. After considerable trial and error with a signal generator and oscilloscope, I found the following values provided the nominal padding while maintaining a reasonably flat frequency response through the transformer.

On the Rev B (red) board, use the following values:
- R1, R3, R11, R13: 100R
- R2, R4, R12, R14: 39R
- R5, R6, R15, R16: 22R
- R7, R17: 150R
- R8, R18: 1.5k
- R9, R19: 27R


The PCB in revision B does not currently have a ground lift switch, but rather, all signals are ground lifted by default.  The enclosure houses two channels, so the ground planes are isolated from each other to avoid crosstalk.  No RF or ESD protection is included in this prototype version.


The enclosure design put forth here is a quick and dirty 3D print in 2 piece construction consisting of a body and a faceplate.  All screws are #4-40 socket head cap screws.  I used 1/4" long screws to secure the jacks/PCB to the faceplate and 1/2" screws to attach the faceplate to the case body.


--Jeremy Wagner, June 2022
