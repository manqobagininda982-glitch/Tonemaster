# ToneMaster build notes

## Work completed in this pass
- Promoted the user app to the repository root so Vercel can serve `/` without deploying a nested folder whose imports escape the deployment root.
- Removed the duplicate nested user-app copy; root `index.html` is the single canonical client entry point.
- Expanded the Web Audio engine: WAV sample root-note detection from filenames, pitch transposition, octave shift, sustain, release envelope, voice cap and simple bass/treble/brightness filters.
- Connected the existing transpose, octave, release, EQ, sustain and max-voice controls.
- Restore locally imported WAV samples from IndexedDB at startup.
- Fixed `db.isSignedIn()` to return an actual awaited boolean rather than a truthy Promise.
- Added Vercel root config, package metadata and a local project-structure check.

## Checks
- JavaScript syntax checks passed for project source files.
- HTML-to-JavaScript selector scan found one optional selector (`#licencePrice`) not present in the HTML; it is guarded and does not block startup.
- Root deployment layout and required file paths checked.
- Full live browser, Supabase, Firebase and MIDI hardware tests are not possible without active services/configuration and a connected keyboard.

## Remaining work
1. Resume Supabase project `xgxkdyaorhgrisrawxhu` and configure the public key.
2. Review existing `profiles`, `licenses` and `user_settings` tables before applying SQL; do not overwrite existing user data.
3. Configure Firebase Storage and implement authenticated, short-lived sound-pack delivery.
4. Implement server-side licence signing/verification and admin authorization. Never expose private signing keys in frontend code.
5. Complete multisample/layer/split/loop performance engine and test with the owner's keyboard and original tone files.
6. Confirm final price (R100 vs R250) consistently across UI and issuer.
