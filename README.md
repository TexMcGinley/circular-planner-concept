Concept walkthrough wireframes

## Updating the walkthrough

The published `index.html` is encrypted with [StatiCrypt](https://github.com/robinmoisson/staticrypt) and needs a password to open.
The editable source lives in `src/index.html`, which is in `.gitignore` and is never committed.

1. Edit `src/index.html` (open it directly in a browser to preview).
2. Run `npm install` once, then `npm run build`. It asks for the password; type it at the prompt.
3. Commit and push the new `index.html`.

Use the same password every time so visitors who ticked "Remember me" stay unlocked.
`.staticrypt.json` holds the salt (not a secret) and must stay committed for the same reason.
`templates/password_template.html` is StatiCrypt's default password page with a `noindex` robots tag added and "Remember me" ticked by default.
"Remember me" never expires (`--remember 0`); a visitor can forget the password by opening the page with `?staticrypt_logout`.
