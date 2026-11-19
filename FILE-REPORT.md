# ToneMaster source audit and build decisions

The supplied sources were distinct, not exact clones: customer UI, Admin Studio, activation gate, Node licence issuer, service worker draft, wordmark and app icon. All relevant source files have been retained in their correct locations. The service worker was rewritten with scoped cache cleanup and the admin page's dangerous public-browser signing/upload actions were locked.

The new starter code is described in `BUILD-NOTES.md`. Missing credentials and sound banks were not invented. The supplied files hard-coded R250; the project config keeps R250 pending confirmation against the older R100 brief.
