# Bloom downloads

Bloom is a private darkroom for your photographs, by Lotus: develop them, keep
the whole record of each one, and carry them between your own devices, with no
cloud between. Every image holds a moment.

This repository publishes signed Bloom Windows releases. The application
source, signing keys, private symbols and build system are not stored here;
GitHub's generated source archives contain only this small distribution shell.

## Install

Download `Bloom-Windows-vX.Y.Z-Setup.exe` from the latest release and run it.
It installs for your user only under `%LOCALAPPDATA%\Programs\Lotus\Bloom`.
Your photographs and settings live outside that folder and survive every
upgrade and uninstall.

During setup Bloom offers to let itself sync on your **private** network
(inbound TCP 45456 and UDP 45454, for Bloom only, never on public networks).
That one step asks Windows for administrator approval; leave it unticked and
Bloom still works on this computer, it just can't receive from your other
devices until you allow it.

Windows SmartScreen may say the publisher is unknown: Bloom is not signed with
a paid Windows publisher certificate. Choose **More info → Run anyway** if you
trust this release, and verify it first if you like (below).

## Verify

Each release carries `SHA256SUMS.txt` and its detached Ed25519 signature
`SHA256SUMS.txt.sig`, made with the Lotus Bloom release key whose public half
is `bloom-release-ed25519-public.pem` in this repository.

```
openssl pkeyutl -verify -pubin -inkey bloom-release-ed25519-public.pem -rawin -in SHA256SUMS.txt -sigfile SHA256SUMS.txt.sig
certutil -hashfile Bloom-Windows-vX.Y.Z-Setup.exe SHA256
```

The hash must match the line in `SHA256SUMS.txt`. See
`LOTUS_RELEASE_IDENTITY.md` for the permanent fingerprint of the key.

## License

Bloom is free to use, including at work. Selling, redistributing, modifying,
repackaging, or monetizing Bloom itself is not permitted. See `LICENSE`.

Icon by Sol.
