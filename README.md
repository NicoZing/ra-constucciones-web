# RA Construcciones · Deploy package

## Files
- index.html - the whole site (images and font embedded, no external requests)
- _headers - security headers for Netlify / Cloudflare Pages
- .htaccess - the same for Apache hosting (most Spanish shared hosting)
- nginx-security.conf - the same for nginx (VPS)
- .well-known/security.txt - contact for reporting vulnerabilities
- robots.txt

Upload index.html, robots.txt, .well-known/ and only the headers file for your server type.
Do not upload LEEME.md or nginx-security.conf to the public folder.

## Before going live
1. Fill in every highlighted [placeholder] in index.html (owner name, NIF/CIF, address, phone,
   hosting provider, accounting firm, retention period).
2. Set WA_NUMBER and the tel: links in index.html.
3. Have the legal texts (Aviso legal, Privacidad, Cookies) reviewed by a lawyer / data protection advisor.

## IMPORTANT: Content-Security-Policy hashes
The CSP only allows the exact <style> and <script> in index.html (sha256 hashes).
If you edit anything inside <style> or <script>, the hashes change and the page will break
until you regenerate them (in the meta tag of index.html AND in the headers file).
Text/HTML edits outside those two blocks are fine.

## Check after deploying
- https://securityheaders.com - should give A or A+
- https://observatory.mozilla.org
- https://www.ssllabs.com/ssltest - should give A
