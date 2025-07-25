# Drosera-Piram-trap

## About the Project

Drosera-Piram-trap is a Solidity trap contract for the Drosera project.  
It monitors the balance of the PIRAM token at a specific address and triggers when the balance decreases by more than 1 token.

---

## Trap Logic

- Monitors the PIRAM ERC-20 token balance at address:  
  `0x4a61B89655A5903224A1b82Eec50c320DD899e1c`

- If the balance decreases by more than 1 PIRAM token (1e6 units given 6 decimals), the trap activates.

- The trap contract implements the required Drosera interface functions:
  - `collect()` — collects the current balance snapshot.
  - `shouldRespond()` — analyzes data history and decides whether to trigger.

---

## Project Structure

```
Drosera-Piram-trap/
├── src/
│   └── PiramTrap.sol        # Trap contract
├── drosera.toml             # Drosera configuration
├── README.md                # Documentation
└── .gitignore               # Git ignore rules
```

---

## drosera.toml

The Drosera configuration file contains connection parameters and trap settings:

- `ethereum_rpc` — Ethereum node RPC URL  
- `drosera_rpc` — Drosera relay RPC URL  
- `drosera_address` — Drosera contract address  
- `[traps.piramtrap]` section with trap parameters: ABI path, response contract, function to call, cooldown, operators, and whitelist.

---

## Deployment and Testing

Contracts can be compiled and tested using Foundry or other Solidity tools.

---

## License

UNLICENSED
