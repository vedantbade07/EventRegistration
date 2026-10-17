# College Event Registration

A responsive college event registration webpage. Students can enter their personal and academic details, choose one or more technical, gaming, or sports events, and see a summary after submitting the registration request.

## Features

- Responsive registration interface for desktop and mobile screens.
- Student details: name, roll number, email, phone, branch, year, division, and optional gender.
- Multiple event selection across technical, gaming, and sports categories.
- Basic required-field and email-format validation.
- Registration request sent to a Google Apps Script web app configured in the page.
- Confirmation summary displayed after the browser submits the request.

## Technologies Used

- HTML5
- CSS3 (embedded in `index.html`)
- JavaScript (embedded in `index.html`)
- Google Apps Script web app (for the Google Sheets integration, if configured)
- Google Fonts (Poppins)

## Project Structure

```text
College-Event-Registration/
├── index.html       # Website, styles, form, and client-side JavaScript
├── README.md        # Project documentation
├── LICENSE          # MIT License
├── .gitignore       # Files Git should ignore
└── .gitattributes   # Consistent text-file line endings
```

## Run Locally

1. Download or clone this repository.
2. Open `index.html` in a modern browser.
3. For development, you can open the folder in Visual Studio Code and use the Live Server extension.

The page is static, so it does not require a build step or package installation.

## Google Sheets / Apps Script Setup

The page uses a Google Apps Script web-app endpoint configured by the `SHEET_URL` constant near the bottom of `index.html`.

1. Create or review the Google Apps Script project that receives the registration data.
2. Deploy it as a web app and configure access according to your institution's privacy and security requirements.
3. Put the deployed web-app URL in `SHEET_URL`.
4. Test a registration and confirm that the data reaches the intended spreadsheet.

**Important:** The URL is visible in the browser source. Do not put passwords, API keys, or other secrets in the HTML. The current client uses `mode: "no-cors"`, so the browser cannot read the server's response and cannot confirm that the server saved the record successfully. Treat the on-page success message as confirmation that the request was attempted, and verify the Apps Script / spreadsheet separately. Do not collect real student personal information until access controls, consent, data retention, and spreadsheet permissions have been checked.

## Deploy with GitHub Pages

1. Create a GitHub repository, for example `college-event-registration`.
2. Upload the files in this folder to the repository root. Make sure the main page is named exactly `index.html`.
3. Open **Settings → Pages** in the repository.
4. Under **Build and deployment**, select **Deploy from a branch**.
5. Select branch `main` and folder `/(root)`, then click **Save**.
6. Wait for GitHub Pages to publish the site. The URL will look like:

   `https://YOUR-USERNAME.github.io/college-event-registration/`

Replace `YOUR-USERNAME` with your GitHub username. The exact repository name determines the final URL.

## Limitations

- This repository contains the front end only; the Google Apps Script backend must be deployed and configured separately.
- The page cannot verify the Apps Script response while using `no-cors`.
- Google Fonts requires an internet connection; a system fallback can be added if offline use is needed.
- This demo should be tested with sample data before real student information is collected.

## License

Released under the MIT License. See [`LICENSE`](LICENSE).
