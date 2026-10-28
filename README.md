# Kidisto Inventory & Billing — GST test build (v6)

A browser-based prototype for one shop computer. It uses HTML, CSS and JavaScript; no paid software or installation is required to test it.

## Run locally
1. Download and extract `Kidisto_Inventory_GST_v6.zip`.
2. Open the extracted folder and double-click `index.html` in Chrome or Edge.
3. Add a test product. Enter a unique SKU/barcode, HSN if known, and the GST rate confirmed for that product.
4. Add sample products if you want to test, or enter your own test data.
5. Create a test bill and check inclusive/exclusive GST, Kerala CGST/SGST, other-state IGST, discount, stock reduction, and printing.
6. Use **Export backup (JSON)** after entering test data. Keep backups somewhere safe.

## GST calculation behaviour
- Each product has a GST rate field. Available choices are 0%, 3%, 5%, 12%, 18%, 28%, and 40% for configuration/testing; this is not a statement that every rate applies to kidswear.
- The bill defaults to prices **including GST**. Untick the box to treat entered selling prices as before-GST prices.
- Place of supply defaults to Kerala (CGST + SGST); select other state to show IGST.
- Discounts are allocated proportionally across cart lines for the displayed taxable/tax calculation.
- HSN is optional in this test build, but should be completed when required.

## Publish online for free (static hosting)
This version can be hosted as a static site on GitHub Pages at no hosting cost, subject to GitHub's current terms and availability:
1. Create/sign in to a GitHub account at https://github.com/.
2. Create a new repository named `kidisto-inventory` (a public repository is the simplest route for GitHub Pages on a free account; do not put private customer data in the source repository).
3. Upload `index.html`, `styles.css`, `app.js`, and `README.md` to the repository root.
4. Open repository **Settings → Pages**.
5. Under build/deployment, choose **Deploy from a branch**, select `main` and `/ (root)`, then Save.
6. Wait for GitHub Pages to publish and open the URL shown in that Pages section.
7. Bookmark it on the shop computer. Camera barcode access generally requires HTTPS; GitHub Pages provides HTTPS.

Official guide: https://docs.github.com/en/pages/getting-started-with-github-pages/creating-a-github-pages-site

## Critical limitation: online website, local data
GitHub Pages only hosts the files. **This build still saves products, bills, and stock in this browser's local storage on this computer.** It does not sync to a cloud database and does not include login. It is not safe for shared use across devices or as the only copy of business records. Export backups regularly. The next backend stage needs a database and authentication (for example, a free-tier database service) and must be configured with your own account credentials; those credentials cannot be generated for you automatically here.

## Before real billing
- The GSTIN supplied for the receipt (`32CDZPB2771ZI`) appears to be shorter than the standard 15-character GSTIN. It is printed with a verification warning. Confirm the correct GSTIN before using invoices.
- Confirm GST rates and HSN codes for each product with your accountant/tax professional. Rates vary by classification and applicable rules.
- Have an accountant verify invoice fields, place-of-supply logic, tax rounding, discounts, invoice numbering, and registration requirements before issuing official tax invoices.
- Bill numbering is basic and there is no void/credit-note workflow, audit log, secure login, supplier purchase ledger, return/exchange workflow, expenses, or cloud backup yet.
- Test with sample data first. Do not treat this prototype as certified GST/accounting software.