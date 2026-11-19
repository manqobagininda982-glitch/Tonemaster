# ToneMaster by MG:SOUNDS

A root-deployable Vercel website foundation. The public user app is at `/`; the separate admin shell is at `/tonemaster-admin/`.

## Included now
- Responsive mobile-first ToneMaster interface
- Browser audio engine with sample playback, voice limiting, transpose, octave, sustain, release and basic EQ filters
- Local WAV import backed by IndexedDB; imported samples reload on next visit
- Virtual keyboard and Web MIDI note input where the browser supports Web MIDI
- Supabase email/password authentication and published sound-pack catalogue reader
- Device-bound signed licence verification foundation
- Separate admin shell with privileged actions deliberately disabled until server-side authorization exists
- Scoped service worker and Vercel configuration

## Deploy
1. Upload the contents of this folder as the Vercel project root (not a nested subfolder).
2. Set `shared/config.js` with the Supabase project URL and public publishable/anon key. Never place a service-role/secret key in browser code.
3. Confirm the Supabase project is active, review `supabase/schema.sql` against existing tables, then apply only the required schema changes.
4. Configure Firebase Storage separately. The current app does not yet implement protected Firebase downloads or pack decryption.
5. Generate a production ECDSA P-256 keypair on a trusted machine. Publish only the public JWK in `shared/config.js`; keep the private JWK offline.
6. Run `npm run check` before deployment.

## Known blockers
- Supabase project `xgxkdyaorhgrisrawxhu` was returned as **INACTIVE** at the time of this build check. Auth and database calls cannot be confirmed until it is active.
- Supabase public key is not configured in the source.
- Firebase Storage configuration and security rules are not supplied; no protected pack download flow exists yet.
- Production licence public key is not configured. Licence activation therefore remains unavailable until key generation and issuer endpoint are completed.
- Admin publishing and licence issuance are intentionally disabled in the browser. They require a server-side endpoint with verified admin authorization.
- No original WAV tone banks were supplied or included. The user can import WAVs locally to test basic sample playback.
- Web MIDI is browser-dependent and may not be available on all Android browsers.
- Browser-delivered audio cannot be made impossible to copy or record. Use authorization, short-lived downloads, encryption at rest, watermarking where appropriate, and clear licensing; do not promise perfect anti-copy protection.
- The current engine is a functional foundation, not a finished multisample workstation. Advanced layered zones, splits, sample loops, pitch bend, modulation, effects chains and low-latency device testing remain.

## Licence price
The source files supplied for this build specify R250. The earlier project brief mentioned R100. R250 is retained pending the owner's decision; the price must be made consistent across UI, issuer and backend before sales.
