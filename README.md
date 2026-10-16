# 3Lance Recruitment Solutions website

**People. Purpose. Possibilities.**
Specialist recruitment for education, health and social care across the UK.
Live domain: 3lancerecruitment.uk

## What's in this folder

| Item | What it is |
|---|---|
| `index.html` | The whole website (all pages, styles and code are in this one file) |
| `img/` | Photos, logo, site icon and the social-sharing image (`share.jpg`) |
| `vid/` | Short looping videos and their preview images |
| `robots.txt`, `sitemap.xml` | Help search engines find the site |

## How to update things

Open `index.html` in a text editor and search (Ctrl+F) for these labels:

| Search for | What it controls |
|---|---|
| `SHEET_CSV` | Vacancies: paste your Google Sheet "Publish to web" CSV link |
| `TALLY LINKS` | Forms: paste each Tally form link |
| `REVIEWS` | Testimonials: add approved quotes with `type:"Client"` or `type:"Candidate"`. The homepage shows up to 3 of each. Until there are any, it shows a "Leave a review" invitation. |
| `CLIENTS` | "Organisations we've worked with" on the homepage. Check each organisation is happy to be named. |
| `ACCREDITATIONS` | Accreditations on the homepage. Put logo files in `img/` and type the file name in `logo`. |
| `COMPANY DETAILS` | Registered company name, number and office. UK law requires these on a company website, and they appear in the footer. |
| `FAQS` | FAQ page |
| `POLICIES` | Privacy, Cookie and Terms pages |

Keep `SHOW_REVIEW_TEMPLATES` set to `false`. It only shows template cards for previewing the layout.

## Publishing

This is a static site, so it needs no build step. On Cloudflare Pages, connect this GitHub repository, leave the build command empty and set the output directory to `/`.

## Photos and videos

Free stock images from Pexels (https://www.pexels.com/license/). They show models, not 3Lance staff, clients or candidates.
