# Gentrit & Lea: wedding invitation

Static site (no build step). Deploy the folder to Vercel as is.

| File | What it is |
|---|---|
| `index.html` | The invitation. Edit the `CONFIG` block at the top of the script for date, venue, times, RSVP deadline and music. |
| `links.html` | Private page for making personal invitation links (`/links.html`). Not linked from the invitation. |
| `zarfi.jpg` | The embossed ivory envelope (client reference, with the old R&Z seal painted out). The G&L wax seal is drawn by the page. |
| `ftesa.png` | The inner card: linen paper with the wine wax seal on top, cut out of the client's velvet-curtain picture so the silk shows around it. The invitation text is laid over the paper. |
| `mendafshi.jpg`, `lustra.png` | Wine silk background and the crystal chandelier cut out of the client's chandelier picture. |
| `dantella.png` | The lace card (client reference, background cut out) used for the greeting section. |
| `gentrit-femije.jpg`, `lea-femije.jpg` | The couple's childhood photos shown in the heart locket. Replace them keeping the same names. |
| `muzika.mp3` | Music that starts when the envelope is opened. Replace it keeping the same name, and update `musicCredit`. |
| `google-apps-script.gs` | Backend that writes RSVPs into a Google Sheet. |

## 1. Set up the RSVP sheet (about 5 minutes)

1. Make a new Google Sheet, e.g. "Dasma Gentrit & Lea – Konfirmimet".
2. **Extensions → Apps Script**. Replace the code with the contents of `google-apps-script.gs` and save.
3. Choose the `setup` function and click **Run**. Accept the permissions. This creates the *Konfirmimet* and *Përmbledhje* sheets.
4. **Deploy → New deployment → Web app**. Set *Execute as: Me* and *Who has access: Anyone*, then **Deploy**.
5. Copy the `https://script.google.com/macros/s/…/exec` URL into `rsvpEndpoint` in `index.html`.
6. Share the Google Sheet with the couple:
   - **Konfirmimet** has one row per answer: invitation name, the name typed in, whether they're coming (Po/Jo), and their message.
   - **Përmbledhje** has the number of Po and Jo answers.

Guests only confirm yes or no. They are not asked how many people are coming, and the invitation doesn't show how many are invited.

## 2. Make personal links (optional)

Open `https://<your-site>/links.html` and enter a name (e.g. *Familja Krasniqi*), then press **Kopjo** or **WhatsApp**. The name shows on the envelope and on the card. The plain site URL also works for everyone.
