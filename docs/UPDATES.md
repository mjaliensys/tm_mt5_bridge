# Releases and updates

Public installers and checksums: https://github.com/mjaliensys/tm_mt5_bridge/releases

Download the Windows x64 installer from a published release and compare its SHA-256 with that release's SHA256SUMS.txt. The release metadata states whether the installer is signed. This initial public release is unsigned; no signing certificate was supplied.

Updates use the same installed application identity and a versioned payload. Run the new installer as the trading Windows user and choose Reuse existing configuration. Profiles are stopped, entries paused, and data backed up before replacement. Journals, identities, credentials, broker terminals and existing broker positions/orders are preserved. After installation, Test connection, Start, and explicitly resume entries as appropriate.

An installer failure leaves retained data and repair evidence. Do not use Fresh, delete data, or restore an old database over later trades as a shortcut. Retry a compatible installer with Reuse after reviewing the failure. Automatic taskbar unpin depends on Windows support; its helper is bounded. If an obsolete pin remains, unpin it manually and use the new desktop shortcut.

New fixes are published as new versioned releases. Existing release assets should not be silently replaced with different bytes. The latest manifest and release notes identify the current version and installer hash. Updates are installed explicitly; this release does not silently replace a running trading process.

For normal uninstall, use the in-app maintenance preparation first, then Windows uninstall. Trading data, journals and credentials are retained. Fresh installation and multiple-account/provider rehearsals will continue after the initial public release; their results and fixes will be reflected in subsequent release notes.
