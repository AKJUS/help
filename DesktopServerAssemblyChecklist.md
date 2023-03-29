# Desktop Server Assembly Checklist

## UEFI Settings

- [X] Update BIOS.
- [X] Enable memory XMP profile.
- [X] Ensure CPU power limits are forced according to standard specification.
  - Intel: PL1 is set to *Processor Base Power* and PL2 to *Maximum Turbo Power*.

- [X] Enable *Power On After Failure*
- [X] Disable Audio Controller.
- [X] Disable Wi-Fi Controller.

## Operating System

- [X] Make sure ESP partition is present on *both* disks.
- [X] Setup IPv4 statically and disable IPv6.
  - Same applies to PiKVM if present.

## Stress and Stability Test

- [X] Run [Karhu RAM Test](https://www.karhusoftware.com/ramtest) until it reaches 10,000 % with no errors. Validate CPU temperatures (e.g. [HWINFO64](https://www.hwinfo.com/download/)).
- [X] Optional: Run MemTest86 (PassMark). This test will **not** detect RAM instabilities.

## Labels

- [X] Add server number labels (white on blue) at following locations:
  - Front
  - Housing Cover
  - Back
  - Inside
 
- [X] Add component labels (black on white) including model number, serial number and size to following components:
  - SSDs

- [X] Add property label inside the case.

## Seal

- [X] Add tamper-proof seal to case **and** note down the serial number.
