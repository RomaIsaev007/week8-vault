# Week 8 — Liquidity Vault Test Plan (Devnet)

- **Wallet:** `EUpX3WNe7Uv3YP1nya2h2bBo6sRJCMVdDcsFhLc6fESQ`
- **Token:** `romaisaev` (`ROMA`, Token-2022)
- **Mint:** `5mYLe...XU9az`

## Test Cases
1. `initialize_vault`: creates Vault PDA (`["vault", authority]`) and Vault Token Account (`ROMA`), sets `total_deposited = 0`.
2. `deposit(amount > 0)`: transfers `ROMA` from user token account to vault token account and increments `total_deposited`.
3. `deposit(amount == 0)`: fails with `InvalidAmount`.
4. `withdraw(amount)`: transfers `ROMA` back to user token account using PDA signer seeds and decrements `total_deposited`.
5. `withdraw(amount > total_deposited)`: fails with `InsufficientVaultBalance`.
