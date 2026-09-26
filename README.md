# Vivek Motte — Static GitHub Pages Demo

## Project Overview
`vivek` is a single-page static web demo for a fictional "Vivek Motte / Vivek Egg" direct-to-consumer storefront. It is implemented with one `index.html` file, local assets, and a GitHub Pages deployment workflow.

## Executive Summary
This repository provides a polished front-end demo experience (hero section, feature blocks, product details, cart drawer, and demo checkout) with no backend services and no build step. Data shown on the page (nutrition, price, reviews) is explicitly demo/fictional.

## Problem Statement
The project needs a presentable, responsive storefront demo that can be hosted on GitHub Pages with minimal setup.

## Background and Motivation
The current implementation focuses on visual storytelling and interaction design (section navigation, cart behavior, checkout flow) for demonstration purposes rather than real commerce processing.

## Proposed Solution
Use a static HTML/CSS/JavaScript architecture with local assets and browser `localStorage` to model cart and quantity state. Deploy automatically via GitHub Actions to GitHub Pages.

## Project Objectives
- Deliver a responsive static landing/storefront page.
- Support lightweight product/cart interactions in-browser.
- Enable simple deployment through GitHub Pages.

## Project Scope
### In Scope
- Static UI/UX for a fictional product.
- In-page navigation and cart drawer.
- Demo checkout confirmation with generated local order ID.
- GitHub Pages CI/CD workflow.

### Out of Scope
- Real authentication/authorization.
- Real payments, shipping, or order fulfillment.
- Backend APIs or persistent server-side database.

### Future Scope
- Replace demo values/reviews with verified data.
- Add a backend for real inventory/orders/payments.

## Target Users
- Portfolio reviewers and demo stakeholders.
- Front-end learners exploring static e-commerce UI patterns.

## Real-World Use Cases
- Demonstrating static commerce-like UX patterns.
- Rapid design prototype deployment via GitHub Pages.

## Key Features
- Responsive single-page layout.
- Hotspot navigation in hero section.
- Quantity controls and cart drawer.
- Cart persistence with `localStorage`.
- Demo checkout modal and generated order ID.

## Functional Requirements (Implemented)
- Add/remove product quantity.
- Add items to cart and update subtotal/total.
- Open/close cart and checkout modal.
- Persist cart/quantity across refresh using browser storage.
- Render section-based navigation through smooth scroll.

## Non-Functional Requirements (Observed)
- No framework/build dependency.
- Works as static hosting artifact.
- Mobile-responsive styles via CSS media queries.

## User Roles and Permissions
Not applicable. No user account system or role model is implemented.

## System Workflow
1. User opens page.
2. User navigates sections via hotspots/buttons.
3. User adjusts quantity and adds product to cart.
4. Cart persists in browser storage.
5. User submits demo checkout form.
6. UI shows local success message and generated demo order ID.

## Technology Stack
- **Frontend:** HTML5, CSS3, vanilla JavaScript (inline in `index.html`)
- **Backend:** Not applicable
- **Database:** Not applicable (browser `localStorage` only)
- **APIs:** Not applicable
- **Authentication:** Not applicable
- **Infrastructure/Hosting:** GitHub Pages
- **DevOps/CI:** GitHub Actions (`.github/workflows/pages.yml`)
- **Testing tools:** No repository test framework present
- **Monitoring tools:** Not configured in this repository

## System Architecture
Static client-side architecture:
- `index.html` contains markup, styles, and behavior.
- `assets/` contains image resources.
- GitHub Actions uploads repository content as Pages artifact and deploys.

## Application Flow
UI events (`onclick`) trigger JS functions (`addToCart`, `renderCart`, `checkout`, `placeOrder`) that mutate in-memory values and `localStorage`, then re-render cart totals in the DOM.

## Data Flow
- Inputs: quantity selection and checkout form fields.
- Temporary state: JS variables (`qty`, `cart`).
- Persistent browser state: `localStorage` keys `vivek-qty`, `vivek-cart`.
- Output: DOM updates and demo order confirmation text.

## Project Structure
```text
.
├── .github/workflows/pages.yml
├── .nojekyll
├── README.md
├── index.html
└── assets/
    ├── close-camera.jpg
    ├── landing-reference.webp
    ├── pointing-cutout.webp
    ├── reference-hero.webp
    ├── vivek-hero.webp
    └── wide-profile.webp
```

## Database Design
Not applicable. No server-side database schema/tables are defined.

## API Documentation
Not applicable. No HTTP API endpoints are implemented.

## Authentication and Authorization
Not applicable. No login/session/permission system is implemented.

## Security Notes
- This is a static demo; no secret keys are required by the app runtime.
- Checkout is explicitly demo-only and does not process real payments.

## Installation and Setup
### Prerequisites
- Modern web browser.
- Optional: Python or any static file server for local hosting.

### Clone Repository
```bash
git clone https://github.com/paladuguganeshnaidu/vivek.git
cd vivek
```

## Local Development
Because there is no build step, open `index.html` directly or host the directory with a static server.

Example using Python:
```bash
python3 -m http.server 8000
```
Then open `http://localhost:8000`.

## Running and Deployment
- **Local:** open/serve `index.html`.
- **Deployment:** GitHub Actions workflow `Deploy Vivek Motte to GitHub Pages` deploys on pushes to `main`.
- **Repository setting required:** GitHub Pages must be configured for **GitHub Actions** source.

## User Guide
- Use top hero hotspots to jump to sections.
- Use `+/-` quantity controls and **Add to cart**.
- Open cart from hero/product section.
- Use **Proceed to checkout** and submit the demo form.

## Demo Assets
No dedicated screenshot documentation is maintained. Visual assets used by the page are available in `/assets`.

## Testing Strategy and Actual Validation Results
### Strategy
This repository currently has no built-in unit/integration/e2e test framework or lint/build scripts.

### Results Observed During Documentation Refactor
- Repository inspection found no `package.json`, `pyproject.toml`, `requirements*.txt`, `go.mod`, `Cargo.toml`, `Makefile`, or test spec files.
- CI evidence from GitHub Actions:
  - Successful Pages deploy run observed: `36224227507` (`conclusion: success`).
  - Earlier failed deploy run observed: `36223280930`, failure reason from logs: Pages site not enabled/configured at that time (`actions/configure-pages` “Get Pages site failed. Not Found”).

## Performance
No formal performance benchmarks or latency measurements are defined in this repository.

## Limitations
- Single-product demo only.
- Fictional data and sample reviews.
- No backend persistence beyond local browser storage.

## Known Issues
- If browser storage is cleared, cart state is reset.
- Demo order ID is randomly generated client-side and not traceable to a backend.

## Troubleshooting
- **Page not deploying:** ensure GitHub Pages source is set to **GitHub Actions**.
- **Cart not persisting:** verify browser allows `localStorage` for the site.

## Logging and Monitoring
Application-level logging/metrics/tracing/alerts are not configured.

## CI/CD Pipeline
Workflow file: `.github/workflows/pages.yml`
- Triggers: `push` on `main`, `workflow_dispatch`.
- Jobs: checkout → configure pages → upload artifact → deploy pages.

## Dependencies and Integrations
- Runtime dependencies: none beyond browser platform APIs.
- External integration: GitHub Pages + GitHub Actions.

## Versioning and Releases
No formal release/versioning strategy is documented in this repository.

## Roadmap
Planned improvements are inferred from current limitations:
- Replace fictional data with verified content.
- Add backend/API for real checkout lifecycle.
- Add automated test/lint checks.

## Contribution and Development Guidelines
- Keep the project static-first unless backend scope is intentionally added.
- Preserve explicit labeling of demo/fictional content.
- Validate GitHub Pages workflow after deployment-related changes.

## License
This project is licensed under the MIT License. See [`LICENSE`](./LICENSE).

## Authors and Contributors
- **Author (repository owner):** Paladugu Ganesh Naidu
- Additional contributors can be viewed in GitHub repository insights.

## References
- Source files in this repository: `index.html`, `.github/workflows/pages.yml`, `assets/*`
- GitHub Actions run history for this repository

## FAQ
### Is this a real e-commerce application?
No. It is a fictional demo and does not process real payments or fulfillment.

### Does this project provide APIs or a backend?
No. All behavior is client-side in `index.html`.

### Is there an automated test suite?
Not currently. No test framework or test scripts are present in the repository.
