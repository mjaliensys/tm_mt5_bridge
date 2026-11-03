# Releases and updates

Public installers and checksums: https://github.com/mjaliensys/tm_mt5_bridge/releases

Download the Windows x64 installer from a published release and compare its SHA-256 with that release's SHA256SUMS.txt. The release metadata states whether the installer is signed. This initial public release is unsigned; no signing certificate was supplied.

Updates use the same installed application identity and a versioned payload. Run the new installer as the trading Windows user and choose Reuse existing configuration. Profiles are stopped, entries paused, and data backed up before replacement. Journals, identities, credentials, broker terminals and existing broker positions/orders are preserved. After installation, Test connection, Start, and explicitly resume entries as appropriate.

An installer failure leaves retained data and repair evidence. Do not use Fresh, delete data, or restore an old database over later trades as a shortcut. Retry a compatible installer with Reuse after reviewing the failure. Automatic taskbar unpin depends on Windows support; its helper is bounded. If an obsolete pin remains, unpin it manually and use the new desktop shortcut.

New fixes are published as new versioned releases. Existing release assets should not be silently replaced with different bytes. The latest manifest and release notes identify the current version and installer hash. Updates are installed explicitly; this release does not silently replace a running trading process.

For normal uninstall, use the in-app maintenance preparation first, then Windows uninstall. Trading data, journals and credentials are retained. Fresh installation and multiple-account/provider rehearsals will continue after the initial public release; their results and fixes will be reflected in subsequent release notes.


## Reboot versus upgrade

An ordinary reboot does not invalidate a profile's successful connection test. With Windows startup management and Resume after Windows login enabled, a profile that was explicitly Started can resume using its saved validation and entry intent. Clock evidence is learned again automatically; an old lease may need to expire. A manual Stop remains stopped. Saving changed configuration, rotating credentials, or installing an update requires another connection test. Upgrades pause entries and leave profiles stopped for explicit review and restart.

## Remove or permanently delete a profile

Stop the selected profile, then use Settings > Delete profile. Local removal hides it from the active list and removes its saved API/broker credentials while retaining its execution archive and backend bot. The archived bot identity remains reserved; use transfer or recovery rather than creating a duplicate profile for it.

For permanent deletion, pause its backend dashboard bot, close its positions and pending orders, and resolve all execution. A recent coherent account snapshot is required; run Test connection if prompted, leaving the profile stopped. Type the exact confirmation shown. The backend checks the bot-scoped credential and authorized installation/profile, freezes new commands and sessions, and removes its bot definition and executor records. Only a matching confirmed deletion receipt permits erasing active local profile data and credentials. Installer backups and user-exported files remain separate and are not rewritten. The server retains a minimal deletion receipt/tombstone for safe retries.

If confirmation is lost or cleanup is interrupted, the profile remains stopped with deletion pending. Retry the same scope through Delete profile; do not create a duplicate profile or clear its journal. Permanent backend deletion is unavailable until the supporting server patch is deployed; local data is retained when that endpoint is missing.

## Partial broker-time history

Verified history windows continue uploading around gaps caused by restarts, outages or missing clock evidence. History > Partial and exported unverified_gaps identify periods whose time conversion remains unverified. No gap is silently called complete, and deferred raw order/deal records are retained for retry. Adding verified historical intervals permits those periods to be revisited. A current verified clock allows normal instrument-specific trade checks even while historical coverage is partial. This does not import account history before the configured/default Bridge start.
