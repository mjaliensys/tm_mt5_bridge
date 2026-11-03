# TradeMagic MT5 Bridge

Windows x64 bridge between your TradeMagic backend bot and its MetaTrader 5 account. Supports explicitly configured Demo and Live profiles. Each enabled profile needs its own terminal installation and account; exact account login, server, environment and ownership are verified before execution.

1. Install the broker's MT5 terminal, sign in to the intended account, and enable algorithmic trading and external Python trading access.
2. Run the Bridge installer as the Windows trading user and approve administrator elevation. Existing installations should choose Reuse configuration to preserve their journals and ownership.
3. Add a profile with the backend origin, bot ID/key, exact terminal executable, account login and broker server. Select DEMO or LIVE to match the actual MT5 account. Existing Demo profiles remain Demo after upgrade; create a separate profile for a different account/environment.
4. Select HEDGING or NETTING_EXCLUSIVE to match the account. Netting-exclusive profiles require exclusive control of the account/symbols they manage.
5. Enable automatic broker time and enter an exact liquid preferred symbol. The Bridge can also learn and renew broker time from other non-custom symbols already selected in that terminal's Market Watch. Each source must independently provide fresh advancing quotes. A stale or unavailable preferred symbol does not invalidate still-current clock evidence; cached quotes never extend its 90-second lifetime. If every source stops supplying proof until expiry, or clock trust fails, the profile blocks. Each trade still requires a fresh quote for its own instrument. Manual verified settings remain available. Historical gaps and uncertain clock changes are not silently assumed valid.
6. Save, run Test connection, and complete backend account/ownership approval if requested. Saving or installing never starts execution automatically.
7. Start the profile and use Pause entries / Resume entries as required. Pausing new entries still permits supported protection, closing and cancellation operations. Stopping a worker leaves broker positions and orders unchanged.
8. Configure Windows startup if unattended operation is wanted, then enable Resume after Windows login and validate/start the profile. A deliberate Stop remains stopped after reboot.

The backend supplies sizing, exact broker symbol mapping and execution-ready commands. The Bridge does not generate signals or choose risk settings. API keys and optional broker passwords are stored in Windows Credential Manager; unattended Windows credentials remain in protected LSA storage. Diagnostics exclude credentials.

New profiles with no explicit backend history start collect from their persisted Bridge connection period, not the account's earlier trading history. Existing explicitly configured Bridge history boundaries are preserved. Current open positions/orders are still observed for ownership and reconciliation.

The configured Demo/Live environment is part of the profile/journal identity. A mismatch, wrong account/server/terminal, stale lease, invalid quote, or unresolved submission blocks the corresponding operation. An uncertain submission is reconciled from broker evidence and is not blindly repeated.

Closing the configuration UI keeps workers running. When Windows manages the agent, the full shutdown action is hidden; the tray menu can still close only the UI. Export diagnostics and inspect command history when investigating an issue. Never delete journals or reset ownership to force a retry.
