# Free clothing preorder website (GitHub Pages + Google Sheets)

This starter website is designed for a small clothing brand testing product demand.
It collects preorder interest and feedback only. It does not take payments and does
not treat a submission as a confirmed order.

## Included
- `index.html` — responsive product catalogue and customer interest form
- `Code.gs` — Google Apps Script endpoint that saves submissions to Google Sheets

## Part A — publish the website on GitHub Pages
1. Sign in at https://github.com and create a **public** repository named
   `YOURUSERNAME.github.io` (replace YOURUSERNAME with your GitHub username).
2. Upload `index.html` to the root of the repository.
3. Open repository **Settings → Pages**. Select **Deploy from a branch**,
   choose `main` and `/ (root)`, then save.
4. Your website address will be `https://YOURUSERNAME.github.io/`.

## Part B — create a Google Sheet to save submissions
1. Create a new Google Sheet at https://sheets.google.com.
2. Open **Extensions → Apps Script**.
3. Replace the starter code in the editor with the full contents of `Code.gs`.
4. Save the project.
5. Click **Deploy → New deployment** and select **Web app**.
6. Set **Execute as** to **Me** and **Who has access** to **Anyone**, if available.
   Review your organisation/account security settings before enabling public access.
7. Deploy and authorize the script when Google prompts you. Copy the Web app URL
   ending in `/exec`.
8. In `index.html`, find `const SCRIPT_URL = "";` and paste the URL between the quotes.
9. Upload the updated `index.html` to GitHub again.

The public web app endpoint is needed so the static website can send responses.
Anyone who obtains the endpoint may be able to submit entries, so monitor the sheet
for spam. Do not store sensitive information. Keep the spreadsheet private.

## Part C — personalise your brand and products
In `index.html`, edit:
- `const BRAND_NAME = "Your Brand";`
- the `PRODUCTS` list: IDs, names, prices, descriptions and suggested colours
- each product's `image` value with a publicly accessible HTTPS image URL

For example:
`image:"https://example.com/my-top-photo.jpg"`

Use your own image URL. Do not use the example URL as a real product image.
Prices in the starter are examples; change or remove them before publishing.

## Test before sharing
1. Open the published website.
2. Submit a test entry using your own test details.
3. Check that a new row appears in the Google Sheet.
4. If it does not, check that the script is deployed as a web app, the URL ends
   with `/exec`, and the latest URL is in `SCRIPT_URL`.
5. Since the browser uses a no-cors request for compatibility with Apps Script,
   the website cannot verify the server's response. Confirm the test row in Sheets
   before announcing the form publicly.

## Important
- This is an interest/preorder request, not a paid or guaranteed order.
- A customer can enter false details; verify demand before production.
- Tell customers how you will use their contact details and remove data you no
  longer need.
- Google Apps Script and Google Sheets have usage limits and terms that can change.
- GitHub Pages is for static hosting. Do not put private keys, passwords, or
  admin credentials in the website code.
