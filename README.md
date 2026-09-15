# XRPH Wallet Recovery

A self-contained offline tool to recover a family seed from XRPH padlock numbers and move funds to a secure wallet.

## How to use

1. Download `index.html` from the [latest release](../../releases/latest)
2. Save it to your device (do not open directly from a chat app)
3. Turn off WiFi and mobile data — on a computer also unplug ethernet
4. Open the saved file in your browser
5. Enter your 8 padlock numbers and recover your seed
6. Re-enable your network and import the seed into your wallet app of choice

## Security

- Runs entirely in your browser — no server, no network calls
- Crypto library (@noble/curves + @noble/hashes) is bundled inline
- Input fields are locked when any network connection is detected
- Verify the file hash before use:

```
SHA-256: 78e782a016678eae0a05ae852cc4dd0aa97052f0cd099b702af7839c329b2ef0
```

## Verification

To verify the file has not been tampered with:

**Mac / Linux**
```bash
shasum -a 256 index.html
```

**Windows (PowerShell)**
```powershell
Get-FileHash index.html -Algorithm SHA256
```

The output should match the hash above.

## What this tool does

Converts your 8 XRPH padlock numbers into an XRPL family seed (starts with `sEdS...`) that can be imported into any standard XRPL wallet — Xaman, Crossmark, Gem Wallet, or others.

## After recovery

1. Import the seed into your wallet app
2. Move all XRP and tokens to a fresh secure wallet
3. Delete the compromised account on-chain to recover the XRP reserve
4. Delete this file from your device

## Source

Prepared by [OnLedger / Elephant Tools](https://onledger.net) — September 2026  
Derivation logic verified against xrpl.js test vectors.
