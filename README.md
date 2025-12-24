
# Immutable Proof Registry

Immutable Proof Registry is a public, neutral proof-of-existence registry that records cryptographic hashes anchored to the Texitcoin Layer-2 blockchain.

The registry provides an auditable, timestamped record that certain data existed at or before a specific point in time, without asserting ownership, authorship, value, or legal rights.

---

## Purpose

The purpose of Immutable Proof Registry is to provide a simple, verifiable method for recording proof-of-existence using a public blockchain, while maintaining a clear separation between:

- On-chain cryptographic proof
- Off-chain descriptive metadata
- Public human-readable indexing

---

## What This Registry Does

- Records cryptographic proof-of-existence
- Anchors entries to the Texitcoin Layer-2 blockchain
- Provides public, independent verification via a blockchain explorer
- Maintains a human-readable public registry index

---

## What This Registry Does NOT Do

- Does **not** store files, images, or data payloads
- Does **not** assert ownership, copyright, or authorship
- Does **not** establish authenticity, provenance, or value
- Does **not** provide legal, financial, or regulatory guarantees

This registry records existence only.

---

## Canonical Sources

For clarity and avoidance of ambiguity, the following sources are considered canonical:

- **Canonical Proof:**  
  The on-chain transaction hash (TXID) recorded on the Texitcoin Layer-2 blockchain.

- **Canonical Registry Index:**  
  The public Google Sheet titled:  
  **“Immutable Proof Registry – Public Index”**

- **Canonical Project Description:**  
  This GitHub repository.

All other representations are informational only.

---

## Blockchain Network

All registry entries are anchored to:

- **Network:** Texitcoin Layer-2  
- **Explorer:** https://explorer.texitcoin.org

The authoritative timestamp for any entry is derived from the block containing the transaction hash (TXID).

---

## Registry Structure

Each registry entry includes:

- Entry identifier (registry index)
- Type of representation
- Blockchain network
- On-chain anchoring reference
- Confirmation status
- Transaction hash (TXID)
- Public explorer link
- Descriptive public notes

The registry index is maintained as a read-only public ledger.

---

## How to Verify an Entry

1. Locate the entry in the public registry index.
2. Click the **Texitcoin Explorer** link associated with the entry.
3. Confirm the transaction hash (TXID).
4. Verify the on-chain timestamp and confirmation status.

The blockchain record is the authoritative source of verification.

---

## Public Registry

The live, read-only public registry index is available at:

👉 https://immutableproofregistry.com

---

## Independence Notice

Immutable Proof Registry is an independent service.

It is not affiliated with, endorsed by, or operated by the Texitcoin project or any blockchain organization.  
Registry entries are informational records only.

---

## Project Status

This project is live and operational.

Registry entries are added through a controlled, manual process to ensure accuracy, consistency, and integrity.

## TXC Anchor Standard

This registry anchors cryptographic proof-of-existence records to the Texitcoin (TXC) blockchain using a neutral OP_RETURN payload rule.

The canonical TXC anchoring specification is defined here:

- TXC Anchor Standard:  
  https://github.com/CRYPTOTEXIT/immutable-proof-registry/tree/main/spec/txc-anchor-standard.md

## Verification

To independently verify a registry entry:

1. Obtain the original file or data.
2. Compute its SHA-256 hash (raw 32 bytes).
3. Locate the corresponding TXC transaction.
4. Confirm the OP_RETURN payload equals the SHA-256 digest exactly.
5. Verify the transaction confirmation timestamp on the Texitcoin blockchain.

No metadata, identifiers, or formatting are stored on-chain.
Only the cryptographic hash is anchored.


## Governance & Neutrality

The Immutable Proof Registry operates as a neutral, content-agnostic registry.

The registry does not assert:
- Ownership
- Authorship
- Copyright
- Legal rights
- Economic value

Only cryptographic proof-of-existence is recorded.

  

