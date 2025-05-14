We made a lot of substitutions to encrypt this. Can you decrypt it? Connect with `nc jupiter.challenges.picoctf.org 39894`.

Hints:
1. Flag is not in the usual flag format

## Solución.
Encontramos el alfabeto de sustitución y el texto descifrado usando una herramienta de criptoanalisis para cifrado por sustitución:
```
Input: -------------------------------------------------------------------------------
soqdfuit wlfl pt koaf mbud - mflnalqsk_pt_s_orlf_buevhu_udmbsdikal
-------------------------------------------------------------------------------
zl zlfl qoi easw eofl iwuq u naufilf om uq woaf oai om oaf twpy ipbb zl tuz wlf tpqg, uqh iwlq p aqhlftiooh mof iwl mpfti ipel zwui zut eluqi vk u twpy moaqhlfpqd pq iwl tlu.  p eati usgqozblhdl p wuh wufhbk lklt io boog ay zwlq iwl tluelq iobh el twl zut tpqgpqd; mof mfoe iwl eoelqi iwui iwlk fuiwlf yai el pqio iwl voui iwuq iwui p epdwi vl tuph io do pq, ek wlufi zut, ut pi zlfl, hluh zpiwpq el, yufibk zpiw mfpdwi, yufibk zpiw woffof om epqh, uqh iwl iwoadwit om zwui zut kli vlmofl el.

Output: ------------------------------------------------------------------------------- CONGRATS HERE IS YOUR FLAG - FREQUENCY_IS_C_OVER_LAMBDA_AGFLCGTYUE ------------------------------------------------------------------------------- WE WERE NOT MUCH MORE THAN A QUARTER OF AN HOUR OUT OF OUR SHIP TILL WE SAW HER SINK, AND THEN I UNDERSTOOD FOR THE FIRST TIME WHAT WAS MEANT BY A SHIP FOUNDERING IN THE SEA. I MUST ACKNOWLEDGE I HAD HARDLY EYES TO LOOK UP WHEN THE SEAMEN TOLD ME SHE WAS SINKING; FOR FROM THE MOMENT THAT THEY RATHER PUT ME INTO THE BOAT THAN THAT I MIGHT BE SAID TO GO IN, MY HEART WAS, AS IT WERE, DEAD WITHIN ME, PARTLY WITH FRIGHT, PARTLY WITH HORROR OF MIND, AND THE THOUGHTS OF WHAT WAS YET BEFORE ME.

Alfabeto de sustitución:
ULJGMRKDTXYEFQOINVCSABHZPW

Flag: FREQUENCY_IS_C_OVER_LAMBDA_AGFLCGTYUE
```