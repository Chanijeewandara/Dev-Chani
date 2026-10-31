# Chani & Dev wedding invitation

Free hosting on GitHub Pages. Replies go to a Google Sheet in your own Google Drive.

Files:

- `index.html` is the invitation (this is what guests open)
- `links.html` makes a personal link for each guest (only you use it)
- `photos/` is where the couple photos go
- `apps-script/Code.gs` is the code for the Google Sheet (step 1)

---

## 1. Replies in a Google Sheet (about 5 minutes)

1. Go to https://sheets.new and name the sheet "Chani Dev RSVP".
2. Click **Extensions > Apps Script**.
3. Delete everything in the editor, paste all of `apps-script/Code.gs`, and click the save icon.
4. In the function drop-down choose `setup` and click **Run**. Allow the permissions it asks for (Google may say "unverified app": click Advanced, then Go to project). This creates the `RSVP` and `Summary` tabs.
5. Click **Deploy > New deployment**. Under the gear icon pick **Web app**.
   - Execute as: **Me**
   - Who has access: **Anyone**
6. Click **Deploy** and copy the **Web app URL** (it ends with `/exec`).
7. Open `index.html`, find the line `var RSVP_ENDPOINT = "";` and paste the URL between the quotes.

Each time a guest taps **OK**, a new row appears in the `RSVP` tab: time, name, Coming / Not coming, number of guests, message. If the same name replies again, their row is updated. The `Summary` tab counts who is coming and the total guests. The sheet stays private in your Drive.

If you change the Apps Script code later, use **Deploy > Manage deployments > Edit > New version** so the same URL keeps working.

## 2. Couple photos

Upload these into the `photos` folder (JPG, ideally under 500 KB each):

- `couple1.jpg` first arch frame, also the faint background behind the names
- `couple2.jpg` second arch frame
- `watermark.jpg` optional, a different photo for the background

Missing files simply show a gold placeholder.

## 3. Put it online with GitHub Pages

1. Sign in at https://github.com and click **New repository**. Name it, for example, `chani-dev`. Choose **Public** (free Pages need a public repository).
2. Click **uploading an existing file**, drag in `index.html`, `links.html`, the `photos` folder and `README.md`, then **Commit changes**. You do not need to upload `apps-script`.
3. Open **Settings > Pages**. Under Build and deployment choose **Deploy from a branch**, branch `main`, folder `/ (root)`, then **Save**.
4. After about a minute your invitation is at `https://YOUR-USERNAME.github.io/chani-dev/`.

## 4. Send to guests

Open `https://YOUR-USERNAME.github.io/chani-dev/links.html`, type the guest names (one per line) and use **Send on WhatsApp** or **Copy link** for each. A link looks like `.../index.html?to=Nimal%20Perera`, and the guest sees "Dear Nimal Perera," on top. The plain address (no name) says "Dear Family & Friends".

Guests who open the page tap **I will be there** or **I can't make it**, then **OK**. If the sheet can't be reached, the page offers a WhatsApp message to 076 210 7148 instead.

## 5. WhatsApp preview picture (optional)

After the site is online, open `index.html` on GitHub (pencil icon) and remove the comment marks around the `og:image` line near the top. Put the full web address of a photo there, for example `https://YOUR-USERNAME.github.io/chani-dev/photos/couple1.jpg`. WhatsApp then shows that photo when the link is shared.

## Good to know

- Anyone who knows the page address can open it, and the repository is public. Don't put private information in the files.
- The Apps Script URL is visible in the page source. That is normal. Someone could send fake replies if they found it, but they can't read your sheet.
- To change wording, dates or numbers, edit `index.html` on GitHub and commit. The page updates in a minute or two.
