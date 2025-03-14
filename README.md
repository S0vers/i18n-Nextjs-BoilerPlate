# Next.js 15 Template with i18n and Shadcn UI

A modern, SEO-optimized template for Next.js 15 applications featuring server components, internationalization support, shadcn UI components, and theme switching capabilities. Perfect for building performant, accessible, and multilingual web applications.

## ✨ Features

- **Next.js 15**: Built on the latest [Next.js 15](https://nextjs.org/) React framework with App Router and Server Components for optimal performance
- **SEO Optimization**: Includes metadata API, structured data, and optimized page loading strategies
- **Internationalization**: Full i18n support using middleware-based routing with [next-intl](https://next-intl-docs.vercel.app/)
- **Shadcn UI**: Pre-configured [shadcn UI](https://ui.shadcn.com/) components using the new React Server Components pattern
- **Theme System**: CSS Variables-based theme system with light/dark mode toggle and system preference detection
- **Language Switching**: Seamless switching between languages (including RTL support for Arabic and other RTL languages)
- **OmitRTL Utility**: Helper component to control elements that should maintain LTR (left-to-right) rendering in RTL contexts
- **TypeScript**: Type-safe codebase with TypeScript configuration optimized for Next.js 15
- **Metadata API**: Built-in SEO metadata management using Next.js 15's metadata API

## 🚀 Getting Started

Clone the repository:

```bash
git clone https://github.com/S0vers/i18n-Nextjs-BoilerPlate.git
```

Install dependencies:

```bash
npm install
# or
yarn
# or
pnpm install
# or
bun install
```

Start the development server:

```bash
npm run dev
# or
yarn dev
# or
pnpm dev
# or
bun dev
```

Open [http://localhost:3000](http://localhost:3000) in your browser to see the result.

## 📋 Project Structure

The project follows Next.js 15's recommended App Router structure with additions for internationalization:

```
├── .next                                 # Next.js build output
├── messages                              # i18n translation files
│   ├── ar.json                           # Arabic translations
│   └── en.json                           # English translations
├── node_modules                          # Dependencies
├── public                                # Static assets
├── src                                   # Source code
│   ├── app                               # Next.js App Router 
│   │   ├── [locale]                      # Dynamic locale routing
│   │   │   ├── layout.tsx                # Root layout with direction handling
│   │   │   ├── page.tsx                  # Home page
│   │   │   ├── error.tsx                 # Error handling
│   │   │   ├── favicon.ico               # Favicon
│   │   │   ├── globals.css               # Global styles
│   │   │   ├── not-found.tsx             # 404 page
│   │   │   ├── robots.txt                # SEO robots file
│   │   │   └── sitemap.ts                # Dynamic sitemap generation
│   │   └── components                    # Application components
│   │       ├── ui                        # shadcn UI components
│   │       ├── LanguageSwitcher.tsx      # Language toggle component
│   │       ├── ModeToggle.tsx            # Theme toggle component
│   │       ├── OmitRTL.tsx               # RTL handling utility
│   │       └── theme-provider.tsx        # Theme context provider
│   ├── i18n                              # Internationalization utilities
│   │   ├── navigation.ts                 # Localized navigation helpers
│   │   ├── requests.ts                   # i18n-aware API request helpers
│   │   └── routing.ts                    # Locale routing utilities
│   ├── lib                               # Utility functions and shared code
│   │   └── middleware.ts                 # i18n middleware for route handling
│   └── components.json                   # shadcn UI component configuration
├── .eslintrc.json                        # ESLint configuration
├── global.d.ts                           # Global TypeScript declarations
├── LICENSE                               # Project license
├── next-env.d.ts                         # Next.js TypeScript declarations
├── next.config.js                        # Next.js configuration
├── package.json                          # Project dependencies and scripts
├── package-lock.json                     # Dependency lock file
├── pnpm-lock.yaml                        # PNPM lock file
├── postcss.config.js                     # PostCSS configuration
├── README.md                             # Project documentation
└── tsconfig.json                         # TypeScript configuration
```

## 🌐 Internationalization

This template uses middleware-based i18n routing with Next.js 15. Language files are stored in the `messages/` directory.

### Adding a New Language

1. Create a new JSON file in the `messages/` directory (e.g., `fr.json`)
2. Add the language to the supported locales in `middleware.ts` and `lib/i18n.ts`
3. Add language option to the `LanguageSwitcher` component

## 🎨 Shadcn UI Components

Shadcn UI components are configured to work with Next.js 15 Server Components. Import them from the `components/ui/` directory:

```jsx
import { Button } from "@/components/ui/button";

export default function Home() {
  return <Button>Click me</Button>;
}
```

## 🔄 OmitRTL Utility

The `OmitRTL` utility helps you control which elements should maintain LTR direction even when the site is in RTL mode.

### How to use the function:

```jsx
import { OmitRTL } from "@/components/OmitRTL";

function MyComponent() {
  return (
    <div>
      <p>This text will follow the website's direction.</p>
      <OmitRTL omitRTL={true}>
        <img src="/logo.png" alt="Logo" />
        <div>
          <h2>This heading and content will always be LTR</h2>
          <p>Regardless of the website's direction.</p>
        </div>
      </OmitRTL>
    </div>
  );
}
```

### NPM Package

If you just need the OmitRTL function, it's also available as an npm package:

```bash
npm i react-omit-rtl
```

```jsx
import React from "react";
import OmitRTL from "react-omit-rtl";

function App() {
  return (
    <OmitRTL omitRTL={true}>
      <p>This text will not have RTL direction.</p>
    </OmitRTL>
  );
}
export default App;
```

## 🔍 SEO Optimization

Next.js 15 provides powerful SEO capabilities through the Metadata API. This template includes:

```jsx
// In app/[locale]/layout.tsx
export async function generateMetadata({ params }): Metadata {
  const { locale } = params;
  
  return {
    title: {
      template: '%s | My App',
      default: 'My Multilingual Next.js 15 App',
    },
    description: 'A modern web application built with Next.js 15, i18n, and shadcn UI',
    alternates: {
      canonical: '/',
      languages: {
        'en-US': '/en',
        'ar-SA': '/ar',
      },
    },
    // More metadata options...
  };
}
```

## 🤝 Contributing

We welcome contributions to improve this template! Here's how you can help:

1. Fork the repository
2. Create a new branch (`git checkout -b feature/your-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin feature/your-feature`)
5. Create a new Pull Request

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.
