
# 64kB ROM
  Purpose: to allow multiple ROM options at boot from a 64k EPROM

  Cuts (red)
    top
      A) M.27 - M.28      ; disconnect M.27 from M.28 (if socket present, it needs to be removed)
    bottom
      B) M.1 - M.28       ; disconnect M.1 from M.28
      C) M.1 - VCC        ; disconnect M.1 from VCC
      
  Straps (blue)
    top
    bottom
      A) M.28 - VCC       ; re-connect M.28 to VCC
      B) M.27 - F5.19     ; connect M.27 to bit Q7 (previously unused)
      C) M.1 -  F5.9      ; connect M.1 to bit Q3 (tape output)

# FEh decoding (reversible)
   Purpose: to bring the full 8-bit port address (FEh) decoded signal to G7 and F5 instead of just the one address line A0

  Cuts (red)
    top
      - install 3 pin jumper J in some appropriate location for easy access from top of board
    bottom
      D) G7.5 - A0        ; disconnect A0 input from /IORD+A0 OR gate
      E) F5.1 - A0        ; disconnect A0 from /CE of F5 register

  Straps (blue)
    top
      - none
    bottom
      D) G7.5 - J.2       ; connect jumper pin 2 to /IORD+FEh_decode OR gate
      E) F5.1 - J.2       ; connect jumper pin 2 to /CE of F5 register
      F) J.1  - A0        ; connect jumper pin 1 to A0
      G) J.3  - FEh_decode; connect jumper pin 3 to a 0xFEh decode signal (e.g., from a GAL)


S.V. Pantazi, July 2024
