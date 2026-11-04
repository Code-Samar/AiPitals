# AiPitals — AI Patient Operations Website

Aipitals is a multi-page website for an AI-enabled patient operations platform designed for clinics and diagnostic centres. The platform presents ways healthcare teams can streamline patient communication, appointment coordination, diagnostic workflows and patient follow-ups.

This repository contains the Vue-based frontend website and an interactive chatbot demonstration.

## Overview

The website introduces Aipitals and its healthcare technology offering through dedicated pages covering solutions, products, implementation workflows, resources, FAQs and contact information.

## Features

- **Modern Homepage:** Introduces the Aipitals platform and its value proposition.
- **Solutions:** Explains healthcare workflow solutions.
- **Product Pages:** Dedicated product information and navigation.
- **How It Works:** Presents the platform workflow and implementation approach.
- **Interactive Chatbot:** Reusable Vue chatbot with quick replies, free-text messages, typing indicators and guided interactions.
- **Product Navigation:** Chat interactions can direct visitors towards product and demo-request pages.
- **FAQ Section:** Provides answers to frequently asked questions.
- **Resources:** Supporting information for visitors.
- **Contact & Demo Enquiries:** Contact interface for prospective customers.
- **Responsive Design:** Custom styling for different screen sizes.
- **SEO Support:** Metadata, Open Graph information, favicon, robots.txt and sitemap.

## Tech Stack

| Technology | Purpose |
|---|---|
| Vue 3 | Frontend framework |
| Vue Router | Client-side routing |
| Vite | Development and build tooling |
| JavaScript | Application logic |
| Bootstrap 5 | UI utilities |
| Bootstrap Icons | Interface icons |
| HTML5 | Application structure |
| CSS3 | Custom styling and responsive layouts |

## Project Structure

```text
AiPitals/
├── public/
│   ├── assets/
│   │   ├── aipitals-logo.png
│   │   ├── aipitals-mark.svg
│   │   └── doctor-hero.jpg
│   ├── favicon.svg
│   ├── robots.txt
│   └── sitemap.xml
│
├── src/
│   ├── components/
│   │   ├── CTASection.vue
│   │   ├── ChatWidget.vue
│   │   ├── ConversationDemo.vue
│   │   ├── FAQAccordion.vue
│   │   ├── Footer.vue
│   │   ├── Navbar.vue
│   │   ├── ProductCard.vue
│   │   └── WorkflowDiagram.vue
│   │
│   ├── data/
│   │   └── products.js
│   │
│   ├── router/
│   │   └── index.js
│   │
│   ├── views/
│   │   ├── About.vue
│   │   ├── Contact.vue
│   │   ├── FAQ.vue
│   │   ├── Home.vue
│   │   ├── HowItWorks.vue
│   │   ├── Legal.vue
│   │   ├── NotFound.vue
│   │   ├── ProductDetail.vue
│   │   ├── Products.vue
│   │   ├── Resources.vue
│   │   └── Solution.vue
│   │
│   ├── App.vue
│   ├── main.js
│   └── style.css
│
├── index.html
├── package.json
├── package-lock.json
└── vite.config.js
```

## Getting Started

### Prerequisites

- Node.js (LTS recommended)
- npm
- Git

### 1. Clone the Repository

```bash
git clone https://github.com/Code-Samar/AiPitals.git
```

### 2. Navigate to the Project

```bash
cd AiPitals
```

### 3. Install Dependencies

```bash
npm install
```

### 4. Start the Development Server

```bash
npm run dev
```

Open the local URL displayed in your terminal. The default Vite address is generally:

```text
http://localhost:5173
```

## Available Scripts

| Command | Description |
|---|---|
| `npm run dev` | Start development server |
| `npm run build` | Generate optimized production build |
| `npm run preview` | Preview the production build |

## Application Customization

| File / Directory | Purpose |
|---|---|
| `src/views/` | Website page content |
| `src/components/` | Reusable Vue components |
| `src/components/ChatWidget.vue` | Interactive chatbot |
| `src/data/products.js` | Product information |
| `src/router/index.js` | Application routing |
| `src/style.css` | Global styling |
| `public/assets/` | Images and branding assets |

## Chatbot Implementation

The project includes an interactive Vue-based chatbot component.

Its frontend demonstration supports:
- Quick reply options.
- Free-text messages.
- Typing indicators.
- Guided appointment-style interactions.
- Product navigation.
- Demo-request navigation.

**Implementation note:** The chatbot is currently a frontend interaction demo. It is not connected to an external AI model, production clinic scheduling backend or live patient records. Connecting a real AI conversational service requires a secure backend/API integration.

## Production Build & Deployment

Generate an optimized production build:

```bash
npm run build
```

The generated application files are available in:

```text
dist/
```

Deploy the `dist/` directory to your preferred static hosting provider.

For client-side routing, configure the hosting platform to serve `index.html` as a fallback for application routes. Configure Vite's base path when deploying under a subdirectory.

## Security Considerations

- Never expose API keys or credentials in frontend code.
- Keep sensitive information on secured backend services.
- Do not store patient health records in frontend source files.
- Review privacy, security and applicable regulatory requirements before introducing real healthcare-data integrations.

## Repository

**GitHub:** https://github.com/Code-Samar/AiPitals

---

*Frontend website developed for Aipitals, showcasing an AI-enabled patient operations platform for healthcare providers.*
