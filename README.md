# TradeMagic MT5 Bridge

Official public downloads for the Windows MT5 Bridge.

**[Download the latest release](https://github.com/mjaliensys/tm_mt5_bridge/releases/latest)**

Supports explicitly configured **Demo and Live** MetaTrader 5 accounts. The backend supplies sizing, symbol mapping and execution instructions. Each enabled profile uses its own terminal/account, with verified identity, ownership fencing and durable command reconciliation.

![Example running profile and state-aware controls](images/bridge-running.png)

## Install

Download the Windows x64 installer and `SHA256SUMS.txt` from the same release. Compare the installer SHA-256 before running it. See [setup](docs/SETUP.md) for profile, account environment, connection testing and startup configuration. The initial public installer is **unsigned**.

## Update

Install the new release using **Reuse existing configuration**. Profiles stop and entries pause during maintenance; journals, identities and credentials are retained. Test the connection and explicitly restart/resume afterward. See [updates and recovery](docs/UPDATES.md).

Fixes are published as new versioned releases. Existing release assets are not silently replaced with different bytes. This repository distributes installers, checksums, release notes and update metadata; development is handled separately. It does not grant public write access: pushes require an authorized owner, collaborator or repository deploy key.

## Release status

The public release supports Demo/Live environment matching. Native acceptance has used a Demo account; Live guards have deterministic adapter coverage without release-preparation trades on real-money accounts. Fresh-install and multiple-account/provider rehearsals will continue, and fixes will ship through subsequent releases. The public binary will be used for the continuing week-long run. Earlier account history is outside the default Bridge history scope.

Third-party notices and licenses are included in the installer and its release assets. No credentials, private trading records or operator acceptance reports are published here.
