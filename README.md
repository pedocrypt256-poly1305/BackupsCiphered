# BackupsCiphered
All critical files are stored here in case my laptop/phone gets destroyed. All manual sync.

VCRescueDisk.zip stores backup headers for my encrypted laptop.
2025TS.kbdx is my Keepass created database. It requires a keyfile to mount.
The keyfile is stored in KFileForKPass.kbdx.

VCRescueDisk.zip config)
Cipher: Classified
PIM: Classified
Hash: Classified

2025TS.kbdx config)
Database version: KBDX4
Cipher: Twofish
KDF: Argon2, Rounds=1, Memory=46 MiB, Parallelism=1

KFileForKPass.kbdx config)
Database version: KBDX4
Cipher: Twofish
KDF: Argon2, Rounds=600, Memory=9001 MiB, Parallelism=8

2025TS.kbdx) Uses own password.
VCRescueDisk.zip) Uses disk encryption password. (same as KFileForKPass.kbdx)
KFileForKPass.kbdx) Uses disk encryption password. (same as VCRescueDisk.zip)

Attack suggestions)
2025TS.kbdx uses a single cipher, brute forcing all 2^256 key combinations would get the juicy nuggets directly.
VCRescueDisk.zip uses PBKDF2, but the PIM/cipher might not be default, and disk encryption passwords can be up to 64 characters for system encryption. That's 440 bit entropy!!
KFileForKPass.kbdx only contains the keyfile required to mount 2025TS.kbdx. It uses insane amounts of Argon2 rounds and memory to store a keyfile.

In short, a direct brute force attack on 2025TS.kbdx seems to make the most logical sense.
