# Official Lotus release identity

**Publisher brand:** Lotus  
**Product:** Bloom

- Ed25519 release public-key file SHA-256: `1905a04fd60db9a4c0292985eff5b576f203d8dc54356de49e7a6207c228a51d`
- Android APK signing certificate SHA-256: `be2fd0ca6dd2e0bcc56989346d597ab45cd88d11e53ba85d68fa427bcb4be5b0`

Every official Bloom release signs its `SHA256SUMS.txt` with the matching
private key; `bloom-release-ed25519-public.pem` beside this record verifies it.
Every official Bloom APK is signed with the Android certificate above
(`apksigner verify --print-certs Bloom-Android-vX.Y.Z.apk`).

Lotus is the independent creator and publisher brand for Bloom. This does not
claim that Lotus is a registered corporation, nor that the Windows installer has
a CA-verified publisher identity. The fingerprint, the Lotus GitHub
organization and the official Lotus website (made-by-lotus.vercel.app) together
distinguish authentic releases from repackages or mirrors.
