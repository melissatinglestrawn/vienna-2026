# Vienna Christmas Getaway 2026 website (simple version)

Every page is a single self-contained file. There are no folders, so you can
select all the .html files at once and drag them into GitHub in one batch.

- `index.html` : home page with the itinerary, travel, packing and extras
- `event-*.html` : one page per stop, with tickets, history and photos
- `gallery.html` : the shared photo wall

## Put it online (GitHub Pages, free)
1. In your repo click **Add file > Upload files**.
2. Select ALL the .html files in this folder (Ctrl+A or Cmd+A after clicking one) and drag them in.
3. Click **Commit changes**. Choose "replace" if it asks about index.html.
4. Settings > Pages > Source: Deploy from a branch, branch `main`, folder `/ (root)`, Save.
5. Your site is live in a minute or two at https://YOUR-USERNAME.github.io/vienna-2026/

Tip: if you already uploaded loose files like style.css or site.js, you can delete them.
They are not used anymore. Open each one in GitHub, click the trash icon, then Commit.

## Turn on the photo gallery (Cloudinary, free)
1. Sign up at cloudinary.com and copy your **Cloud name** from the Dashboard.
2. Settings > Upload > Upload presets > Add upload preset. Signing mode **Unsigned**,
   folder `vienna-2026`. Save and copy the preset **name**.
3. Settings > Security > Restricted image types: UNCHECK **Resource list**. Save.
4. In GitHub, open `gallery.html`, click the pencil icon, and find these lines near
   the top of the file (around line 229):

       cloudName: "",
       uploadPreset: "",

   Put your values between the quotes, for example:

       cloudName: "melissa-vienna",
       uploadPreset: "vienna_uploads",

5. Optional: set `passcode: "gluhwein"` to require a shared word before friends see the gallery.
6. Commit changes. The gallery works within a minute.

## Connect your Namecheap domain
1. GitHub Settings > Pages > Custom domain: enter your domain and Save.
2. Namecheap > Domain List > Manage > Advanced DNS. Remove the default parking records, then add:

| Type | Host | Value |
|---|---|---|
| A Record | @ | 185.199.108.153 |
| A Record | @ | 185.199.109.153 |
| A Record | @ | 185.199.110.153 |
| A Record | @ | 185.199.111.153 |
| CNAME Record | www | YOUR-USERNAME.github.io |

3. Wait up to a few hours, then check **Enforce HTTPS** in GitHub Pages settings.

## Notes
- Pages are set to noindex, but anyone with the link can view them.
- The home page lists the apartment address. Edit `index.html` to remove it if you prefer.
