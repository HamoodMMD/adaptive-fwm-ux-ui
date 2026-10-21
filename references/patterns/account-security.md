# Sign-in, passwords and account security

The screens where people prove who they are and protect their account: sign-in, creating and changing a password, one-time codes, passkeys, account recovery, session expiry, and security settings. Security that confuses people gets worked around, so ease of use here is part of security, not a trade against it.

**Load when:** the surface has sign-in, sign-up with a password, a one-time code, two-step verification, passkeys, password reset or account recovery, a session timeout, a security or devices page, API keys, or sign-out.
**Skip when:** the product has no accounts.
**Pair with (when present):** `core/accessibility` (3.3.8 and 2.2.1), `patterns/forms`, `patterns/onboarding`, `profiles/high-stakes`.

## Objectives

The rightful owner gets in quickly and reliably, on any device, without memorizing or transcribing anything they do not have to. When they cannot get in, they can recover without guessing. Security steps appear where risk justifies them and are explained in plain words. Nothing about the account is weakened for convenience, and nothing is made harder without a security reason.

## Priority principles

1. **Do not weaken security for convenience, and do not add friction and call it security.** Every extra step should answer a real risk.
2. **Let the tools do the remembering.** Password managers, paste, autofill and passkeys reduce errors and are what current standards ask for.
3. **Recovery is part of sign-in.** A sign-in page is only as usable as its way back in.
4. **Say what happened without helping an attacker.** Tell the user what to do next without revealing which part of their credentials was wrong.
5. **Interface changes only.** Password rules, lockouts, timeouts, code length and expiry are security policy. Report them; never change them in a fix pass.

## Checks

### Sign-in
- Fields use the right `autocomplete` values (`username` or `email`, `current-password`) so password managers fill them.
- Paste is allowed in every credential and code field (WCAG 2.2, 3.3.8).
- A "show password" control is offered.
- Sign-in does not require solving a puzzle, transcribing characters or remembering anything beyond what a password manager or a passkey can supply, unless an alternative is offered (3.3.8). A CAPTCHA that is a cognitive test needs a non-cognitive alternative.
- A failed attempt says the details did not match and what to do next, without saying which field was wrong. The password field is cleared; the username is kept.
- Lockout or slow-down after repeated failures is explained in the message before it happens, with the way to recover.
- "Forgot password" is next to the password field, not hidden at the foot of the page.

### Creating and changing a password
- Rules are stated before the user types, the same everywhere a password is set.
- Length is the main requirement. Current US federal guidance asks for at least 15 characters when the password is the only factor, at least 8 with a second factor, allows at least 64, and forbids composition rules (a digit, a symbol, mixed case) and scheduled changes. A UK government pattern asks for at least 8 characters with no maximum.
- Common and breached passwords are refused with a plain reason and guidance.
- `autocomplete="new-password"` lets password managers suggest a strong one.
- There are no password hints and no security questions.
- Confirming a new password by typing it twice is allowed by WCAG (3.3.7 exception); showing it once with a show control is the simpler alternative.

### One-time codes and two-step verification
- The code field uses `autocomplete="one-time-code"` and `inputmode="numeric"`, and accepts spaces and hyphens.
- The code is one field, not one box per digit: split boxes force transcription and fail 3.3.8 unless pasting fills them all.
- The page says where the code was sent (without showing the full number on sign-in), that it can take a few minutes, how long it lasts, and offers a "send a new code" link.
- A person who no longer has the phone or device is told what to do.

### Passkeys
- The word "passkey" is used consistently, with a short explanation where it is first offered.
- Creating a passkey is offered at a natural moment (after sign-in, or in account settings), never forced, and the account settings page lists, names and removes passkeys.
- Sign-in with a passkey can fall back to another method.

### Recovery
- Password reset sends a time-limited link or code to an address or number already on the account, and tells the user it has been sent without confirming whether an account exists.
- The user is told by email when their password or security settings change, with what to do if it was not them.
- Recovery is possible without the device that was lost, through a path the user set up in advance or through support.

### Sessions and time limits
- Before a session expires, the user is warned with time to extend it by a simple action, unless an exception applies (2.2.1). In-progress work is kept or restorable after signing back in.
- After expiry, signing in returns the user to where they were.
- "Sign out" is easy to find. Signing out of other devices is available where the product supports it.

### Security settings and secrets
- Security settings are in one findable place, named in plain words.
- API keys and tokens are shown once at creation with a clear "copy" control and the warning that they cannot be shown again; afterwards only a masked suffix is displayed.
- Removing access, revoking keys or deleting an account follows the confirmation rules in `profiles/high-stakes`.

## Anti-patterns

- Paste blocked on password or code fields.
- A six-box code entry that does not accept paste.
- Composition rules ("one capital, one number, one symbol") and forced password changes on a schedule.
- "Incorrect password" on sign-in, telling an attacker the username was right.
- Security questions or password hints.
- A session that expires silently and throws away a half-finished form.
- A CAPTCHA on every sign-in with no alternative.
- Signing out hidden three menus deep.

## Exceptions and context

- **Regulated and high-assurance services** (banking, health, government) may be required to use shorter session limits and stronger factors. Check the timeouts against the level the service needs before calling them unfriendly.
- **Internal tools on single sign-on** have no sign-in screen to audit; check what happens when the session ends.
- **Consumer apps** benefit most from passkeys and password managers, because their users reuse passwords most.

## Implementation cautions

- Safe UI work: `autocomplete`, `inputmode`, removing a script that blocks paste, adding a show-password control that only toggles the input type, wording of messages, and placing links.
- Functional work, recommend only: password rules, lockout thresholds, code length or expiry, session limits, adding passkeys or two-step verification, changing what an error reveals in the server response, recovery flows.
- Never log, display, store or send credentials or codes in anything you add, including screenshots in the report.

## Sources

- [W3C-10] Accessible authentication; [W3C-30] adjustable time limits; [W3C-31] redundant entry
- [NIST-01] Password length, no composition rules or forced changes, paste and password managers, blocklists, no hints or security questions, session limits
- [GOV-10] A government passwords pattern; [GOV-11] security codes
- [FIDO-01] Passkey creation, sign-in with fallback, management in settings
- [NNG-80] Password creation; [NNG-06] confirmation dialogs
