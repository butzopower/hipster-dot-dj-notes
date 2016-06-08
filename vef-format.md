# VEF - Vinyl Encoding Format used by Rocko Boy Records

## HEADER

- First 2 bytes represent VEF encoding format ID - always ACDC
- Next 2 bytes represent VEF encoding version number, eg 0001
- Next 4 bytes are numeric account identifier (provided by Rocko Boy Records) - eg. 00 00 00 01
- Next 16 bytes are MD5 account signature (provided by Rocko Boy Records) - eg. 9F 26 F0 E4 27 5E 43 FD 82 60 97 7C B9 0C BB FC
- Next 4 bytes represent length in bytes of body

## BODY

The body is built up of each record and side of the release

### Side

- First 2 bytes represent disc number: eg. 0001, 0002, etc
- Next byte represent side: 01 or 02
- Next 2 bytes represent total length of side in bytes in hexadecimal, big-endian, eg. 1A42 (note: 22min * 60 * 10 = 13200 = 0x3390 - largest possible length)
- Each second is represented by 10 bytes, eg: A1 A2 A3 A4 A5 B6 B7 B8 C9 D0
- 00 represents nothing etched into record
- FF represents smooth groove with no sound
- Half a second or more of nothing (00 00 00 00 00) will cause the needle to fall off the record
