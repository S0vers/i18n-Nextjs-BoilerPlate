# Next.js Boilerplate with i18n and Shadcn UI

This is a boilerplate project for Next.js applications that includes basic internationalization (i18n) support, shadcn UI components, and functionality to toggle between light and dark themes and different languages. It also includes an `OmitRTL` utility function to help control elements that should be omitted from RTL (right-to-left) rendering.

## Features

- **Next.js**: The boilerplate is built on the [Next.js](https://nextjs.org/) React framework.
- **i18n**: Basic internationalization support using the [next-intl](https://next-intl-docs.vercel.app/) library.
- **Shadcn UI**: Includes the [shadcn UI](https://ui.shadcn.com/) component library for a modern and accessible UI.
- **Theme Toggling**: Ability to toggle between light and dark themes.
- **Language Switching**: Allows users to switch between different languages (e.g., English and Arabic).
- **OmitRTL Function**: A utility function to omit specific elements from RTL rendering, ensuring they always display in LTR (left-to-right) mode.

## Getting Started

1. Clone the repository:

```bash
git clone https://github.com/S0vers/i18n-Nextjs-BoilerPlate.git
```

Install dependencies:
bashCopy codecd next-boilerplate
npm install

Start the development server:
bashCopy codenpm run dev

Open http://localhost:3000 in your browser to see the boilerplate in action.

Usage
The boilerplate provides a basic structure and components to get you started with your Next.js project. You can customize the code and add your own components and functionality as needed.
i18n
The i18n functionality is handled by the next-intl library. You can add new languages and translations by modifying the locales directory and the next-intl.config.js file.
Shadcn UI
The shadcn UI components are imported and used throughout the codebase. You can explore the available components and their usage in the shadcn UI documentation.
Theme Toggling
The ThemeToggle component in components/ThemeToggle.tsx provides a dropdown menu to switch between light, dark, and system themes.
Language Switching
The LocaleSwitcher component in components/LocaleSwitcher.tsx allows users to switch between different languages by selecting from a dropdown menu.
OmitRTL Function
The OmitRTL component in components/OmitRTL.tsx is a utility function that can be used to wrap elements that should be omitted from RTL rendering. This ensures that those elements always display in LTR mode, regardless of the website's direction.
jsxCopy codeimport OmitRTL from './OmitRTL';

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
Contributing
If you'd like to contribute to this boilerplate, please follow these steps:

Fork the repository
Create a new branch (git checkout -b feature/your-feature)
Commit your changes (git commit -am 'Add some feature')
Push to the branch (git push origin feature/your-feature)
Create a new Pull Request

License
This project is licensed under the MIT License.

```

```
