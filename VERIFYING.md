Verification Notes (Operational)

Status: Informational / Non-authoritative
Related Specification: TXC Anchor Standard (v1.0, Frozen)
Last updated: Dec 24, 2025

Purpose

This document provides practical guidance for verifying Immutable Proof Registry anchors given current Texitcoin (TXC) tooling limitations.

It does not modify, replace, or supersede the authoritative specification:

TXC Anchor Standard (spec/txc-anchor-standard.md, v1.0, Frozen)

The protocol rules remain unchanged.

Summary of the Anchoring Rule (Normative Reference)

Per the TXC Anchor Standard (v1.0):

A valid registry anchor is a TXC transaction containing exactly one OP_RETURN output

The OP_RETURN pushed data is exactly 32 bytes

Those 32 bytes are the raw SHA-256 digest bytes of the registered work

No prefixes, identifiers, metadata, JSON, or branding are included on-chain

All descriptive metadata is maintained off-chain

This document assumes familiarity with those rules and does not restate them in full.

Current TXC Tooling Reality (Important)

As of this writing:

The official Texitcoin wallet UI does not expose:

scriptPubKey data

OP_RETURN outputs

raw transaction hex

a debug console or RPC interface for end users

The official Texitcoin block explorer displays:

transaction existence

inputs, outputs, amounts

confirmations and timestamps
but does not display OP_RETURN / script data

As a result:

OP_RETURN data required for verification may not be visible using first-party TXC tools alone.

This is a tooling visibility limitation, not a protocol or consensus issue.

About Third-Party Explorers and Indexers

Some third-party services (e.g., Bevis-indexed views, mempool-style viewers) may display OP_RETURN data for certain TXC transactions.

Important distinctions:

Transactions registered or indexed through third-party services may appear with decoded OP_RETURN data

Transactions created directly via a wallet with a neutral OP_RETURN (per the spec) may:

exist on-chain

be fully valid

yet not be discoverable by explorers that rely on off-chain indexing or submission paths

Explorer visibility does not determine validity.

Verification Methods (Operational)
Track A — Explorer / Indexer (Convenience)

Use when an explorer or indexer exposes OP_RETURN/script data.

Open the transaction by TXID.

Locate the OP_RETURN output.

Copy the pushed data (often shown as 64 hex characters, representing 32 bytes).

Compute SHA-256 of the file or data locally.

Verification succeeds if the computed hash matches byte-for-byte.

Availability depends on the explorer’s indexing policy.

Track B — Node / RPC (Trust-Minimized, Advanced)

Use when a TXC full node and RPC interface are available.

Retrieve the raw transaction by TXID (e.g., getrawtransaction <txid> 1).

Inspect vout[].scriptPubKey for the OP_RETURN output.

Extract the pushed 32-byte payload.

Compare against the locally computed SHA-256 digest.

This method is canonical but may not be accessible to most users until TXC tooling exposes it.

Track C — Registry Cross-Check (Interim Fallback)

Until OP_RETURN visibility is universally available:

Obtain the TXID and the extracted OP_RETURN hash from the public registry index.

Compute SHA-256 of the file locally.

Compare the result to the published extracted hash.

This method verifies hash correctness and registry integrity, with on-chain inspection deferred until tooling improves.

Important Clarifications

Lack of OP_RETURN visibility in a wallet or explorer does not invalidate an anchor.

Explorer support is not a consensus rule.

The protocol deliberately avoids on-chain identifiers to remain neutral and censorship-resistant.

Future improvements to TXC explorers or wallets may enable direct OP_RETURN inspection without any protocol changes.

Forward Compatibility

If and when Texitcoin tooling exposes:

OP_RETURN outputs

scriptPubKey data

raw transaction hex

or a public RPC/debug interface

verification becomes simpler, but no changes to the TXC Anchor Standard are required.

This document may be updated to reflect tooling improvements while the v1.0 specification remains frozen.

Disclaimer

This document is provided for operational clarity only.
The authoritative rules governing Immutable Proof Registry anchors are defined exclusively in the TXC Anchor Standard (v1.0).
