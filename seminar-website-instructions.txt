# Selected Topics in LLM Post-training

A minimal, responsive academic seminar website for GitHub Pages. All page content and styling live in `index.html`. There are no dependencies, installation steps, build commands, or JavaScript requirements.

## Preview

Open `index.html` in a web browser. The page works directly from your computer, including its styling and section navigation. Paper links require an internet connection.

## What is included

- Seminar description
- Profiles for Zena Al Khalili, Dr. Abhilasha Ravichander, and Dr. Krishna Gummadi, with optional pictures and short biographies
- Presentation schedule with dates, linked paper titles, and student presenters
- Instructions for seminar participants
- Mobile layout, keyboard focus styles, a skip-to-content link, and print styling

The title, seminar description, and instructor names were supplied by the seminar organizer. The reading sequence and participant guidance are provisional. Dates, student presenters, instructor photographs, and biographies have not been supplied. The reading sequence is pedagogical rather than a strict publication timeline. The o1 reading is an official research announcement, not a conventional research paper.

## Publish on GitHub Pages

1. Open [Zena-AlKhalili/Post_training_Seminar](https://github.com/Zena-AlKhalili/Post_training_Seminar) while signed into an account with write access to that repository.
2. Upload `index.html` and `.nojekyll` to the root of its `main` branch. You may also include this `README.md`. Upload the extracted files, not the ZIP archive or its enclosing folder. `index.html` should appear directly in the repository’s top-level file list.
3. Open the repository’s **Settings → Pages**.
4. Under **Build and deployment → Source**, choose **Deploy from a branch**.
5. Select **main** and **/(root)**, then click **Save**.
6. Wait for GitHub’s deployment to finish. The Pages settings screen will show the published website address.

Once Pages is enabled and its first deployment succeeds, the website address will be:

```text
https://zena-alkhalili.github.io/Post_training_Seminar/
```

If the repository already contains another website, preserve it and use a separate repository for this seminar. If you deliberately publish from `/docs`, put both website files inside `/docs` and select that folder in Pages settings.

GitHub documentation: [Configure a publishing source](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site) and [GitHub Pages site types and addresses](https://docs.github.com/en/pages/getting-started-with-github-pages/what-is-github-pages).

## Update the content

Edit `index.html` locally, or open it in GitHub and choose the pencil icon. Search for `EDIT:` to find the main editing points. Save and commit the changes; GitHub Pages publishes updates from the selected branch and folder.

| Content | What to edit in `index.html` |
| --- | --- |
| Browser tab title and search description | `<title>` and `<meta name="description">` near the top |
| Seminar title | The wordmark, `<h1>`, and footer |
| Semester, meeting time, and room | The `<dl class="details">` block |
| Description | The section with `id="description"` |
| Instructor names, photos, and bios | The section with `id="instructors"`; see the photo instructions below |
| Papers, dates, and student presenters | The `<tbody>` inside the schedule section |
| Participant instructions | The section with `id="instructions"` |
| Colors and spacing | The `<style>` block; main colors are defined in `:root` |

Each `<tr>` inside `<tbody>` represents one session. Replace the text `To be announced` with a date and `Unassigned` with the student’s name. You can use a machine-readable date, for example:

```html
<td class="date"><time datetime="2026-10-12">12 Oct 2026</time></td>
```

To change a paper, edit both its title and its `href` URL. Duplicate or delete an entire session `<tr>...</tr>` block to add or remove a session, then update the week numbers. Use `&amp;` for a literal ampersand in HTML text.

Once the schedule and instructions are final, remove the provisional notices. No submission system is included: the instructions are informational and can link to your institution’s existing submission platform if needed.

## Add instructor photos and short biographies

Each instructor profile initially shows initials in the photo area. This avoids displaying a broken image before a photograph is available.

1. Upload a portrait into an `images` folder at the repository root. Suggested filenames are `zena-al-khalili.jpg`, `abhilasha-ravichander.jpg`, and `krishna-gummadi.jpg`.
2. In the corresponding instructor profile in `index.html`, delete the initials `<span>` and uncomment the `<img>` line by removing its surrounding `<!--` and `-->`. If the file uses another name or extension, adjust `src` to match it exactly.
3. Replace `Short biography to be added.` in that profile with the instructor’s short bio. You can add an affiliation, homepage, or email link if desired.

For example, Zena’s photo area becomes:

```html
<div class="instructor-photo">
  <img src="images/zena-al-khalili.jpg" alt="Zena Al Khalili"
       width="160" height="160" loading="lazy">
</div>
```

Photos are cropped to a consistent circle. Square portraits with the face near the center work best. Keep the `images/...` paths relative so they work under `/Post_training_Seminar/` on GitHub Pages. The `images` folder is only needed once you add photographs.

## Included files

```text
index.html   Website, with embedded CSS and favicon
.nojekyll    Tells GitHub Pages to serve the static files without Jekyll processing
README.md    Editing and publishing guide
```

All paper links point to primary sources. The site uses local system fonts and has no external scripts, font downloads, analytics, or tracking.
