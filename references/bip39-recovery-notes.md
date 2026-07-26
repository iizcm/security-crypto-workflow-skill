# BIP39 Recovery Notes — Session 2026-07-25

## User's Partial Phrase (from image, word 11 obscured)
```
orphan (01) front (02) dry (03) vivid (04) best (05) journey (06) tired (07) phone (08) ability (09) kingdom (10) ___ (11) stove (12)
```

## Test Results
- Word ke-11 = "abandon" → address generated does NOT match any known wallet
- Verified against: `0xeA29bD21...2a361` and `0x732c86F49B2416D9D401070E8dBe59aC5e7331BF`
- **Conclusion: the phrase from image is NOT the user's wallet phrase**
- Hint "pake semua kata kamus bip39" for word 11 produced "abandon" which fails verification

## Tool Locations
- `/home/ubuntu/nft-work/recover_letter.js` — recover 1 missing BIP39 word
- `/home/ubuntu/nft-work/recover_check.js` — verify recovered phrase

⚠️ This phrase may be from a different source/image. User should check original image more carefully or provide hint about the missing word.
