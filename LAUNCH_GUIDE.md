# Launch guide (do these in order)

## A. Tally forms (free) - tally.so
Create one account, then make 6 forms. For each: Settings > "Email me when someone submits" > your recruitment email. Settings > Redirect or thank-you message: write a short thank-you.
1. **Job Application** (key: apply): Full name, Email, Phone, Location, Experience, Qualifications, Right to work (dropdown), Availability, Message (optional), CV (File upload, required), checkbox "I have read the privacy notice". Type /hidden and add two hidden fields: `job_id` and `job_title`.
2. **Candidate Registration** (reg): same as above without hidden fields, plus Preferred roles and Sector.
3. **Request Staff** (staff): Organisation, Organisation type, Contact name, Job title, Email, Phone, Location, Website, Type of staff, Number, Contract type, Start date, Additional info.
4. **Leave a Review** (review): Name, Organisation or role, Client/Candidate, Rating, Review, consent checkbox "3Lance may publish my review".
5. **Refer a Friend** (refer): Your name/email, friend's name and contact, consent checkbox.
6. **CV Drop-off** (cv): Name, Email, Phone, CV upload, privacy checkbox. (Optional: reuse for Careers.)
For each form press Publish > Share > copy the link.
Then open index.html in a text editor and paste each link between the quotes in `const TALLY={apply:"",reg:"",...}`. Any slot left empty falls back to opening an email.
Check Tally's current file-size limit and privacy/retention terms before launch.

## B. Jobs Google Sheet (free)
1. sheets.google.com > Blank spreadsheet > name it "3Lance Jobs". Rename the tab "Jobs".
2. Paste the headings from jobs-sheet-template.csv into row 1 (File > Import also works).
3. Status column: Insert > Dropdown: Open, Closed. Job Type: Temporary, Fixed-term, Permanent.
4. In Responsibilities/Requirements/Benefits put one point per line (Ctrl+Enter).
5. File > Share > Publish to web > choose the Jobs tab and "Comma-separated values (.csv)" > Publish > copy link.
6. Paste it into `const SHEET_CSV=""` in index.html.
7. The Sheet must contain job details only. Never put candidate data in it. Apply Form column: leave blank to use the main Application form, or paste a Tally link for one job.
Closing a job: change Status to Closed. It disappears within a few minutes.

## C. Fill the content (before publishing)
- Search index.html for NEEDS CONFIRMATION: Privacy, Cookies, Terms, FAQ, Registration documents. Complete them (have a professional check the policies).
- Add real reviews to `REVIEWS` (copy the format in the comment). Only approved reviews.
- Fill Training and Careers placeholders (search "Replace with").
- Confirm the REC membership line (remove it if not current).
- Replace the example vacancies by setting up the Sheet (step B).

## D. Email
Business email is alia@3-lance.co.uk for now. If you move to info@3lancerecruitment.uk, search and replace the address in index.html.

## E. GitHub
1. github.com > sign up > New repository > name `3lance-recruitment-website` > Private > Create.
2. "uploading an existing file" > drag in every file from this folder > Commit changes.

## F. Cloudflare Pages
1. dash.cloudflare.com > sign up > Workers & Pages > Create > Pages > Connect to Git > authorise GitHub > choose the repo.
2. Framework: None. Build command: leave empty. Output directory: `/` (or leave blank). Save and Deploy.
3. Open the temporary *.pages.dev address and test (section G).
(If the screens look different, look for "Create application > Pages".)

## G. Domain
1. In Cloudflare: Domain Registration > Register domain > 3lancerecruitment.uk (small yearly fee).
2. Your Pages project > Custom domains > Set up a domain > 3lancerecruitment.uk > confirm. Add www.3lancerecruitment.uk too; Cloudflare can redirect www to the main address.
3. Wait for HTTPS (usually minutes). Check the padlock.

## H. Private CV storage (simple manual process for launch)
Candidates' CVs are stored in Tally (private to your account) and emailed to you. In SharePoint/OneDrive create: 3Lance Candidate Documents > Applications, Registered Candidates, CVs, Archived, Client Documents. Share only with named staff. Move CVs there manually and delete from Tally when no longer needed. Tally to SharePoint automation would need a paid tool; decide later.

## I. Launch test checklist (use dummy data only)
- Every menu and footer link; mobile and desktop.
- Search by keyword, location, job type; Clear.
- Mark a job Closed in the Sheet: it disappears.
- Job Details page and Apply: correct job in the Tally entry (job_id and job_title filled).
- Submit each form with dummy data; check the notification email and the thank-you message.
- CV upload works on a phone.
- Delete all test submissions afterwards.
- View page source: no candidate data, no secrets.
- HTTPS padlock; title and description show in a browser tab.
- Search Google Search Console later: add the site and submit sitemap.xml.

## Known limitations
- The site is a single page (/ with # sections). Individual jobs cannot be indexed separately by Google. A later upgrade could create separate job pages.
- Tally free forms: check current limits. The acknowledgement email to candidates may not be available on the free plan; test it.
- Policies are drafts, not legal advice.
