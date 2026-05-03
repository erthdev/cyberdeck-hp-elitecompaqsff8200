## Log 02 — April 30, 2026

After the initial teardown and early power experiments, I shifted focus toward locking in a more stable and realistic power 
architecture for the cyberdeck build. The original idea of modifying or forcing the stock PSU into a compact form is now 
fully abandoned. After it failed and the system showed multiple blinking error indicators, I confirmed that continuing to 
experiment with it would only introduce more instability. At this point, the PSU is considered dead and no longer part of 
the build. The direction is now fully centered on a battery-powered DC system feeding a DC-ATX module, with proper adapter
cables handling the motherboard’s proprietary power layout.

---

## Power Architecture (Current Plan)

Battery pack --> DC-ATX (12V input, up to 250W output) --> adapter harness --> HP 8200 motherboard

This removes the need for an AC inverter and reduces unnecessary power conversions, making the system more 
compact and better suited for a portable enclosure.

---

## Battery Planning

For the battery stage, I am still evaluating between:
- 12V 20,000mAh lithium pack 
- 24V 20,000mAh lithium pack
- 2× 12V pack configuration for extended runtime

The 12V option is currently the most practical because it directly matches the DC-ATX input requirement and avoids 
additional voltage conversion losses.

---

## DC-ATX Module

The selected DC-ATX unit:
- Input: 12V DC
- Output: Standard 24-pin ATX
- Max rated output: ~250W (manufacturer claim)
- Includes SATA and CPU power outputs

This simplifies the core power conversion stage, but it is still not enough on its own for the HP motherboard
without proper adapter wiring.

---

## Motherboard Power Requirements (HP 8200 SFF)

The HP 8200 SFF motherboard does not use a standard single-connector ATX layout. Instead, it uses:

- P1: Main power input
- P2: Power control / status signals
- P3: CPU 12V power input

Because of this, a direct 24-pin ATX connection is not sufficient. A proper adapter harness or custom wiring 
solution is required to correctly map the DC-ATX outputs to the motherboard inputs.

---

## Adapter Planning

Adapter design is now a critical requirement in the build.

Needed:
- ATX 24-pin --> HP P1 adapter
- CPU 4-pin (EPS) --> HP P3 adapter
- P2 signal mapping (PS_ON / PWR_OK handling)

This step will determine whether the system boots reliably or behaves unpredictably.

---

## Cooling Plan (Preliminary)

Cooling is being redesigned for a compact enclosure. The current direction is:
- Replace large stock fans with smaller blower-style fans
- Dedicated CPU heatsink + fan assembly
- Optimized airflow channel inside wooden chassis

This will help balance thermals while freeing internal space for battery and power modules.

---

## What I did today

- Confirmed PSU failure and removed it from the build plan  
- Defined battery --> DC-ATX --> adapter --> motherboard architecture  
- Selected 12V DC-ATX input as the preferred direction  
- Evaluated 12V vs 24V battery configurations  
- Identified HP adapter harness as a required component  
- Set cooling redesign direction toward compact blower-based airflow  

---

## Current Status

The power system design is now stable in concept. The build has moved from teardown phase into structured system 
architecture planning.

---

## Next Step

- Finalize battery selection  
- Source correct HP motherboard adapter harness  
- Begin internal layout planning for chassis, cooling, and power placement  
