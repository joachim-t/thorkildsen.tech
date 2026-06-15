# thorkildsen.tech

En enkel statisk landingsside for `thorkildsen.tech`, laget for gratis publisering med GitHub Pages.

## Publisering på GitHub Pages

1. Opprett et nytt repository på GitHub, for eksempel `Thorkildsen.tech`.
2. Last opp filene i denne mappen til repositoriet.
3. Gå til repository-innstillinger på GitHub: `Settings` -> `Pages`.
4. Velg `Deploy from a branch`, branch `main`, folder `/root`, og lagre.
5. Under `Custom domain`, bruk `thorkildsen.tech`.
6. Slå på `Enforce HTTPS` når GitHub har verifisert domenet.

`CNAME`-filen ligger allerede i prosjektet og forteller GitHub Pages hvilket domene siden skal bruke.

## DNS i Cloudflare

Hvis domenet fortsatt bruker navneservere fra en annen leverandør, må navneserverne først byttes hos domeneregistraren til navneserverne Cloudflare viser for domenet.

Legg deretter inn disse DNS-postene i Cloudflare:

| Type | Name | Content |
| --- | --- | --- |
| A | @ | 185.199.108.153 |
| A | @ | 185.199.109.153 |
| A | @ | 185.199.110.153 |
| A | @ | 185.199.111.153 |
| AAAA | @ | 2606:50c0:8000::153 |
| AAAA | @ | 2606:50c0:8001::153 |
| AAAA | @ | 2606:50c0:8002::153 |
| AAAA | @ | 2606:50c0:8003::153 |
| CNAME | www | joachim-t.github.io |

Start gjerne med `DNS only` mens GitHub verifiserer domenet og lager HTTPS-sertifikat. Etter at alt virker kan Cloudflare-proxy vurderes om du ønsker Cloudflare foran siden.
