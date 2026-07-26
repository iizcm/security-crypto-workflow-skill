---
name: security-crypto-workflow
description: "Safe workflow untuk BIP39 recovery phrase, auto-sweep, dan semua operasi crypto yang melibatkan private key. Menekankan keamanan, verifikasi alamat, dan tidak pernah sweep tanpa konfirmasi eksplisit user."
version: 1.0.0
author: User (iizcm)
license: Proprietary
tags: [security, crypto, wallet, recovery, sweep]
---

# Security & Crypto Workflow

Semua operasi crypto yang melibatkan private key, seed phrase, atau penyaluran dana HARUS mengikuti aturan ini.

## Aturan Emas

1. **JANGAN pernah menyimpan private key/mnemonic dalam script/bot** — gunakan env var dengan chmod 600.
2. **Verifikasi alamat wallet** sebelum apa pun — jangan asumsikan phrase yang direcover menghasilkan wallet milik user.
3. **Tidak ada auto-sweep** tanpa konfirmasi eksplisit user per-wallet. Ketik "CONFIRM SWEEP" huruf besar.
4. **Sweep semua wallet matching = DILARANG** — bisa include wallet orang lain, risiko pencurian & ilegal.

## Recovery Phrase (1 kata hilang)

### Format input user:
```
recover: word1 word2 word3 ... ____ word12
hint: huruf pertama 'x' / panjang '5' huruf
```

### Workflow:
1. Generate ~4096 kemungkinan (seluruh BIP39 wordlist)
2. Cek setiap address yang dihasilkan → cocok dengan wallet user?
3. Jika ADA yang match → LAPORKAN ke user, TIDAK auto-sweep
4. User pilih mana yang mau disweep → konfirmasi eksplisit → eksekusi per-wallet

### Pitfalls:
- BIP39 dengan 1 kata hilang = 2047 kemungkinan valid (2048 - kata yang ada). Bisa produce banyak address.
- Multiple wallets bisa match (false positive dari randomness). Verifikasi saldo + ownership.
- Jangan pernah dump semua address ke chat — hanya report yang ada saldo.

## Auto-Sweep Setup

### Validasi sebelum deploy:
1. Konfirmasi target address by user
2. Tentukan chain (Base, ETH, dll)
3. Tentukan token (USDC, WBTC, dll)
4. Setup cron job dengan interval scan (30s/1m/5m)
5. Log semua transaksi ke file terpisah

### Risk check:
- Gas fluktuasi bisa bikin tx fail atau mahal
- Bug/error → dana terjebak/permanen hilang
- Always test dengan jumlah kecil dulu
