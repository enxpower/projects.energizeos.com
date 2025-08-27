# EnergizeOS™ Project Document Portal

This repository powers the public-facing project document portal hosted at  
👉 [https://projects.energizeos.com](https://projects.energizeos.com)

The portal automatically lists and serves project-related files directly from a shared Google Drive folder. It is built with **GitHub Pages + Google Drive API**, so there is no backend server required.

---

## ✨ Features

- **Three-Level Structure**
  - **Customer level** → Each customer has its own folder inside the root `projects/` folder.
  - **Project level** → Each customer folder may contain multiple project folders.
  - **File level** → Each project folder contains files, automatically categorized.

- **Automatic File Categorization**
  - Files are grouped by keywords in their names:
    - 📁 **Technical Proposals** → `spec`, `datasheet`, `technical`, `proposal`, `design`, `drawing`
    - 📁 **Legal & Commercial Documents** → `contract`, `agreement`, `terms`, `msa`, `quote`, `pricing`, `commercial`, `invoice`
    - 📁 **Other Attachments** → All files that do not match the above categories

- **Real-Time Synchronization**
  - Files are **fetched live** from Google Drive using the Drive API.
  - Any new folder or file added to the shared Drive (`projects/`) appears instantly after a page refresh.
  - No manual update or redeployment required.

- **Search & Filter**
  - 🔍 Search across customers, projects, and file names.
  - 📂 Filter files by category (Technical / Legal / Other).
  - Results update dynamically, showing only matching content.

- **Accordion UI**
  - Clean expandable/collapsible sections for customers and projects.
  - File links include size and last modified date.

- **Direct Downloads**
  - Non-Google files (`.pdf`, `.docx`, `.xlsx`, etc.) download directly from Drive.
  - Google Docs/Sheets/Slides are automatically exported as **PDF** (configurable to DOCX/XLSX/PPTX).

- **Responsive Design**
  - Dark theme optimized for desktop and mobile.
  - Simple toolbar with search and filter options.

- **Footer with Branding**
  - © 2025 Energize Solutions Inc.
  - Links to LinkedIn and GitHub.

---

## 🔧 Configuration

Edit `index.html` and update the following section:

```js
const CONFIG = {
  API_KEY: 'YOUR_GOOGLE_API_KEY',
  ROOT_FOLDER_ID: 'YOUR_PROJECTS_FOLDER_ID', // Google Drive folder ID of "projects/"
  PAGE_SIZE: 200,
  SORT_CUSTOMERS: "name",
  SORT_PROJECTS: "name",
  SORT_FILES: "modifiedTime desc",
  EXPORT_GOOGLE_DOCS_AS: "pdf" // pdf / docx / xlsx / pptx
};
