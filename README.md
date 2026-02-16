# Enterprise Data Client (React 19 + Vite)

![React](https://img.shields.io/badge/React-19.0-blue?logo=react)
![TypeScript](https://img.shields.io/badge/TypeScript-5.9-blue?logo=typescript)
![Vite](https://img.shields.io/badge/Vite-7.0-purple?logo=vite)
![Playwright](https://img.shields.io/badge/Testing-Playwright-green?logo=playwright)
![License](https://img.shields.io/badge/License-MIT-gray)

**The high-performance frontend client for the Enterprise Data Visualization Platform.**

This repository hosts the client-side application architecture, focusing on **accessibility**, **component modularity**, and **rendering performance**. It serves as the consumption layer for the Python Asset Service, providing a seamless, responsive UI for financial analytics.

## 🏗 Architecture & Tech Stack

This project is built on a **modern, type-safe foundation** designed for scale.

### Core Framework
* **Runtime:** [React 19](https://react.dev/) - Leveraging the latest concurrent features for high-frequency updates.
* **Build Tool:** [Vite 7](https://vitejs.dev/) - Ensuring instant HMR (Hot Module Replacement) and optimized production builds.
* **Language:** [TypeScript 5.9](https://www.typescriptlang.org/) - Strict type safety for all components and API responses.

### UI & Design System (Headless Architecture)
Unlike traditional UI kits, this project uses a **Headless UI** approach for maximum customization and accessibility.
* **Primitives:** [@radix-ui](https://www.radix-ui.com/) - Unstyled, accessible components (Tabs, ScrollArea, Dialogs) that handle ARIA roles and keyboard navigation out of the box.
* **Styling:** [Tailwind CSS 4](https://tailwindcss.com/) - Utility-first CSS for rapid styling.
* **Composition:** [class-variance-authority (CVA)](https://cva.style/) - Creating type-safe, variant-driven components (e.g., `Button` variants).
* **Icons:** [Lucide React](https://lucide.dev/) - Lightweight, tree-shakeable icons.

### State Management
* **[Zustand](https://github.com/pmndrs/zustand):** A small, fast, and scalable bearbones state-management solution. Used for global UI state (theme, sidebar, user preferences) to avoid React Context re-rendering issues.

### Quality Assurance
* **End-to-End Testing:** [Playwright](https://playwright.dev/) - Automated browser testing to ensure critical user flows (Login, Dashboard Load, Filtering) work across Chrome, Firefox, and Safari.
* **Linting:** ESLint 9 + Prettier - Enforcing strict code style and preventing functional errors.

## ⚡ Performance Optimization

* **Zero-Runtime Styles:** Tailwind CSS generates CSS at build time, resulting in minimal bundle overhead compared to CSS-in-JS libraries.
* **Radix Primitives:** Components like `ScrollArea` and `Tabs` are optimized for DOM footprint, ensuring the dashboard remains responsive even with complex layouts.

## 🛠 Local Development

### Prerequisites
* Node.js 18+
* pnpm (recommended) or npm

### Installation

```bash
# Clone the repository
git clone [https://github.com/Enterprise-Data-Visualisation/react-client.git](https://github.com/Enterprise-Data-Visualisation/react-client.git)

# Install dependencies
npm install
