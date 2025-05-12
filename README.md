# Cobra 2 (Turbo Spectrum) IO extension board v5
IO extension board for Turbo Spectrum (aka Cobra-2) 8 bit computer

S.V. Pantazi (svpantazi@gmail.com)

Aug, 2024

## Features:
- complete Spectrum FEh port decoding option to allow even IO ports for peripherals; 
    - requires (reversible) hardware modifications to the original TS (see Cobra2_mainboard_modifications)
    - if no modification, the only possible way to use the SIO, IDE and sound hardware is to reprogam the GAL to decode odd ports and modify SIO and IDE software accordingly
- SIO 0/1/2 ($84-$87 port decoding) featuring 2 serial ports with settable (jumper) baud rates up to 115200
- dual 8 bit IDE ($10-$17 main port range and $20-$27 for additional IDE registers); can be modified by reprogramming the GAL); 2nd CF card, uses the same port range for decoding; card selection is done in software (primary/secondary card)
- Turbo Sound (2nd AY3 8910 xor 8912 xor 8913) option with $A3 switching done through writing 0 or 1 to the port
    - AY-3 MSX-compatible ($A0-$A2) and Spectrum ($FFFD, $BFFD) decoding
- RCBus backplane compatible extension to allow RC2014 and RCBus add-on cards and other experimental additions

## NOTE: AY3 Turbo sound
  - Some of the original AY-3 TurboSound designs call for decoding of data bus bits D0-D7 using an 8 input AND gate (7430) to achieve switching without any additional port decoding; however, since port decoding is easy present and done with GAL logic, the switching between AY3 chips done the usual way, through writing on a separate port to set/reset a flip-flop.

## Acknowledgements:
  - S. Cismas, Turbo Spectrum (CoBra-2); https://www.cobrasov.org  
  - N. Muntean, Turbo Spectrum (CoBra-2), hardware development, testing and support
  - B. Shen, Simple80; CF card interface; https://www.retrobrewcomputers.org/doku.php?id=builderpages:plasmo:simple80r1
  - NedoPC, Velesoft and others; Turbo Sound; https://velesoft.speccy.cz/turbosound-cz.htm
