# Portfolio Maintenance Guide

## 1. Updating Song Lists (Catalog)
**Good news!** You do **not** need to edit any code to update your song lists.

Since the "VIEW LIST" buttons link directly to your **Notion pages**, you simply need to:
1.  Open your Notion workspace.
2.  Go to the page (e.g., "Classical / Semi-Classical").
3.  Add, remove, or edit songs there.

Updates happen instantly because the website just links visitors to your live Notion page.

---

## 2. Updating Live Performances (Videos)
The videos are embedded directly in the website code using Google Drive. To change them, you will need to edit the `index.html` file.

### Step A: Get the Google Drive Link
1.  Upload your video to Google Drive.
2.  Right-click the video > **Share** > **Copy Link**.
    *   *Make sure "General access" is set to "Anyone with the link".*
3.  The link will look like this:
    `https://drive.google.com/file/d/YOUR_FILE_ID/view?usp=sharing`

### Step B: Convert to Preview Link
You must change `/view` to `/preview` for it to work on the website.
*   **Original**: `.../d/YOUR_FILE_ID/view?usp=sharing`
*   **Preview Version**: `https://drive.google.com/file/d/YOUR_FILE_ID/preview`

### Step C: Update the Code
1.  Open `index.html` in a text editor (like Notepad or VS Code).
2.  Search for `id="videos"`.
3.  Look for the `<iframe>` tags inside that section.
4.  Replace the `src` link with your new **Preview Version** link.

**Example Code:**
```html
<div class="video-wrapper">
    <iframe 
        src="https://drive.google.com/file/d/YOUR_NEW_FILE_ID/preview" 
        title="Performance Video" ... >
    </iframe>
</div>
```

5.  Save the file and refresh your browser to see the change.
