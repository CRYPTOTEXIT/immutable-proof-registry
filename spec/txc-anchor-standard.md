# TXC Anchor Standard (Immutable Proof Registry)

## Neutral OP_RETURN Payload Rule

**On-chain commitment:** A Texitcoin (TXC) transaction MUST contain a single OP_RETURN output whose pushed data is exactly **32 bytes**.

Those 32 bytes MUST be the **raw SHA-256 digest bytes** of the work being registered.

### Requirements
1. The OP_RETURN pushed data length is exactly **32 bytes**.
2. The bytes equal the SHA-256 digest of the work (byte-for-byte).
3. No prefixes, identifiers, metadata, separators, JSON, or branding are included on-chain.

### Metadata location
All descriptive metadata (title/description, algorithm label, links, notes) is maintained **off-chain** in the public registry index.

### Verification
A commitment is valid if:
- the transaction is confirmed on TXC, and
- an OP_RETURN output contains exactly 32 bytes matching the registry’s SHA-256 hash.
