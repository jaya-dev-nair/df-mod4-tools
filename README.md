# df-mod4-tools: Digital Forensics Module 4 Project

This project explores core digital forensics techniques, including hashing, evidence tagging, hex sector analysis, and simple encryption. The exercises demonstrate how these methods help identify, organize, examine, and protect digital evidence.

## Exercise 1: Autopsy - Import Hash Database (Known Files)

- Verification screenshot: ![Exercise 1 verification screenshot](images/exercise-1-verification.png)
- Importing the National Software Reference Library (NSRL) database of "Known" cryptographic hashes allows Autopsy to automatically identify and filter out standard operating system components, common applications, and benign utility files. Because these baseline files are cryptographically verified as unaltered commercial or open-source software, investigators can safely exclude them from manual review. This dramatically reduces investigative noise and shrinks the volume of data, allowing examiners to focus their time on unknown, altered, or potentially incriminating user files.

## Exercise 2: Autopsy - Create Hash Database (Evidence Files)

- Verification screenshot: ![Exercise 2 verification screenshot](images/exercise-2-verification.png)
- Building a custom "Notable" hash database allows investigators to catalog the exact cryptographic fingerprints of confirmed illicit or evidentiary files discovered during an examination. Once compiled, this hash set can be deployed across additional workstations, servers, or mobile devices on a network to automatically flag matching files—even if a suspect has renamed the files or altered their extensions. This targeted hash-matching approach accelerates multi-device triage and prevents examiners from having to manually inspect every drive for known contraband or intellectual property leaks.

## Exercise 3: Hex Editor - Match File Remnants

- Verification screenshot: ![Exercise 3 verification screenshot](images/exercise-3-verification.png)
- When a file is deleted, the operating system removes its file-system directory pointer while leaving the underlying raw data clusters intact in unallocated space until they are eventually overwritten. Because a partially overwritten file will no longer match its original whole-file hash, computing cryptographic hashes of individual 512-byte sectors (such as bytes 0x00 through 0x1FF) creates granular fingerprints of surviving file headers and fragments. Scanning unallocated disk space against these sector-level hashes enables investigators to reliably identify and prove the prior existence of deleted evidence remnants.

## Exercise 4: Simple Encryption

- Verification screenshot: ![Exercise 4 verification screenshot](images/exercise-4-verification.png)
- Using CyberChef, plaintext from evidence.txt was obscured with a polyalphabetic Vigenère cipher into nothing.txt and cleanly restored into recovered.txt using the matching secret keyword. In digital forensics, suspects frequently hide sensitive files or strings using low-level bit manipulation—such as bitwise XOR or bit-shifting—which transforms readable ASCII characters into unrecognizable binary patterns that bypass standard keyword searches. When reversing or testing bit-shift obfuscation within a fixed-width byte or register, shifting bits left before shifting right ensures high-order bits are moved out and back cleanly within the available bit boundary (or without truncating the least-significant bits against the right edge first), preventing permanent data loss during transformation.

## Optional Bonus: Crack a Passcode with a Rainbow Table

- Verification screenshot: ![Optional bonus verification screenshot](images/optional-bonus-verification.png)
- Write-up notes: Explain why rainbow tables are useful to understand in digital forensics.
