# bitwarden-json-print

Turns a Bitwarden JSON export into a dense, printable table — roughly 200 logins on 4–5 sheets of
A4 — for keeping a paper backup of a password vault. One HTML file, no dependencies, no network
access.

Not affiliated with Bitwarden, Inc.

## Use

1. In Bitwarden: **Tools → Export vault → File format `.json`** (unencrypted).
2. Open `bitwarden-json-print.html` in **Chrome** (Safari and Firefox break the pagination).
3. Drop the `.json` file onto the page.
4. Adjust the settings until the page count looks right.
5. **Print / Save as PDF**, with margins set to **None** (they are baked into each page),
   headers and footers **off**, background graphics **on**, scale **100%**.

A cover page, then the table: **Name · Username · Password · URI · Other fields / notes**. The last
column holds TOTP secrets, custom fields, card details, identity fields and notes. Digits print in
blue so `0`/`O` and `1`/`I`/`l` stay apart at 6pt.

## Settings

| | |
| --- | --- |
| **Export name / As of** | Cover page title. |
| **Page footer** | Title and `page N of M` on each page. |
| **Size** | A4, A5, A3, Letter, Legal, or custom mm. |
| **Orientation** | Portrait or landscape. |
| **Two columns** | Landscape only. Two tables side by side, each with its own header. |
| **Margins** | In mm. Keep ≥ 5mm — most printers cannot print to the edge. |
| **Font pt** | Main density control. Default 6.4. |
| **Group by folder** | Folder headings, or one flat alphabetical list. |
| **URI: host only** | `example.com` instead of the full URL. |
| **Include TOTP secrets** | Off keeps 2FA seeds off the paper. |
| **Blue digits** | Separately for credentials and for the other-fields column. |
| **Columns** | Which columns to print, built from the loaded file. |

Page count updates live, so you can tune the font size and watch a page drop off.

## Security

The file is parsed locally and nothing is uploaded. But **Save as PDF writes every password to disk
in plaintext**, and network printers keep the job on their spool — print locally where you can, and
delete the export when you are done. Store the printout like cash: a safe, a deposit box, or a
sealed envelope with your will.

## Licence

MIT — see [LICENSE.md](LICENSE.md).
