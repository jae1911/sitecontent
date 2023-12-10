---
title: FIDO2
description: "Random FIDO2 documentation, list of key and supported websites."
---

# FIDO2

${toc}

## Security Keys Providers

- [Yubico](https://www.yubico.com/)
- [Nitrokey](https://www.nitrokey.com/)
- [Solokeys](https://solokeys.com/) - Note: cannot recommend at the moment due to state of the project
- [Thetis](https://thetis.io/)
- [Onlykey](https://onlykey.io/)
- [Google Titan](https://en.wikipedia.org/wiki/Titan_Security_Key) - Note: unavailable in most of the world
- [Feitian](https://www.ftsafe.com/)
- [ExcelSecu](https://www.excelsecu.com/)
- [Token2](https://www.token2.com/)
- [Hypersecu](https://www.hypersecu.com/)
- [Identiv](https://www.identiv.com/)
- [Kensington](https://www.kensington.com/)
- [GoTrust](https://gotrustid.com/)

## Websites supporting security keys

- [GitHub](https://github.com) - As 2FA
- [Google](https://google.com) - As 2FA + Passkey
- [Gandi](https://gandi.net) - As 2FA
- [Proton](https://proton.me) - As 2FA
- [Microsoft](https://microsoft.com) - As 2FA + Passwordless Login
- [DNSimple](https://dnsimple.com) - As 2FA
- [Discord](https://discord.com) - As 2FA

## Software supporting security keys

- [GitLab](https://gitlab.com) - As 2FA
- [Forgejo](https://forgejo.org/) - As 2FA
- [FireFish](https://joinfirefish.org/) - As 2FA + Passwordless Login
- [BitWarden](https://bitwarden.com/) - As 2FA
- [Mailcow](https://mailcow.email) - As 2FA + Passwordless Login

## Claims to support

- PayPal - As 2FA, could not test, nonworking implementation; passkeys supported but only with Android or iOS builtin
- Hetzner - As 2FA, only supports Yubikey TOTP

## Setting up SSH with a FIDO key

### Windows 11

Windows 11 ships with outdated software which means before all, you will need to install [the latest version of Win32-OpenSSH](https://github.com/PowerShell/Win32-OpenSSH/releases/latest) which supports FIDO2 flows.

The rest is pretty easy:

- Generating the key: `ssh-keygen -t ed25519-sk -O resident` and should output your new public key to `~/.ssh/id_ed25519_sk.pub`

Now trying to SSH into something should bring up a window asking you to touch your key to confirm the action.
