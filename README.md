# Home Rental Dapp (RentRight)

## Documentation

---

## Table of Contents
- [Project Overview (What)](#project-overview-what)
- [Purpose & Motivation (Why)](#purpose--motivation-why)
- [How It Works (How)](#how-it-works-how)
- [Civic Auth Integration](#civic-auth-integration)
  - [How Civic Auth is Implemented](#how-civic-auth-is-implemented)
  - [Benefits of Civic Auth](#benefits-of-civic-auth)
- [Project Structure](#project-structure)
- [Languages & Technologies Used](#languages--technologies-used)
- [Summary](#summary)

---

## Project Overview (What)

**RentRight** is a decentralized web application (Dapp) designed to streamline the rental and listing process for properties. It provides a transparent, secure, and user-friendly platform for tenants and landlords to interact, verify identities, and manage rental agreements.

---

## Purpose & Motivation (Why)

- **Trust & Security:** Traditional rental platforms often lack robust identity verification, leading to scams and mistrust. RentRight leverages Civic Auth for decentralized, privacy-preserving identity verification.
- **Transparency:** By using blockchain and decentralized authentication, the platform ensures that all interactions and agreements are transparent and tamper-proof.
- **User Experience:** The app is designed to be intuitive for both tenants and landlords, with role-based dashboards and seamless onboarding.

---

## How It Works (How)

1. **User Onboarding:** New users authenticate using Civic Auth, choosing their role as either tenant or landlord.
2. **Role Selection:** After verification, users are redirected to their respective dashboards (tenant or landlord).
3. **Property Listing & Browsing:** Landlords can list properties, while tenants can browse and apply for rentals.
4. **Application & Communication:** Tenants apply for properties, and landlords review applications and communicate securely.
5. **Privacy & Security:** All sensitive operations, including identity verification, are handled securely via Civic Auth and encrypted storage.

---

## Civic Auth Integration

### How Civic Auth is Implemented

- **Library Usage:** The project uses [`@civic/auth`](https://www.npmjs.com/package/@civic/auth) and [`@civic/auth-web3`](https://www.npmjs.com/package/@civic/auth-web3) for authentication and identity verification.
- **Component:** The [`CivicAuthButton`](./src/components/CivicAuthButton.tsx) component manages the entire Civic authentication flow, including sign-in, role selection, and redirection to the appropriate dashboard.
- **Provider:** The app is wrapped in a `CivicAuthProvider` (see [`App.tsx`](./src/App.tsx)), ensuring Civic Auth context is available throughout the app.
- **Role Storage:** Upon successful authentication, the user’s role (tenant or landlord) is stored locally and used for personalized redirection and dashboard rendering.
- **UX:** The onboarding flow is smooth—users see clear status indicators (e.g., “Signing in with Civic...”, “Redirecting...”), and are prompted to select their role after authentication.

### Benefits of Civic Auth

- **Decentralized Identity:** Users control their own identity, reducing the risk of centralized data breaches.
- **Privacy:** Only necessary information is shared, and users can prove their identity without exposing sensitive data.
- **Trust:** Both tenants and landlords can trust that the other party has been verified, reducing fraud and increasing confidence.
- **Seamless Experience:** Civic Auth provides a frictionless, single-click verification experience, improving user onboarding.

---

## Project Structure

```text
Home_Rental_Dapp/
│
├── .env                    # Environment variables
├── .gitignore
├── README.md               # Project documentation
├── bun.lockb / package-lock.json / package.json  # Dependency management
├── public/                 # Static assets (images, etc.)
├── src/                    # Main source code
│   ├── App.tsx             # Main React App component
│   ├── main.tsx            # Entry point
│   ├── firebase.ts         # Firebase integration (if used)
│   ├── components/         # Reusable UI and logic components
│   │   ├── CivicAuthButton.tsx   # Civic Auth integration
│   │   ├── Dashboard.tsx         # Main dashboard UI
│   │   ├── ...                   # Other UI components (Hero, Header, etc.)
│   ├── pages/              # Page-level components (TenantDashboard, LandlordDashboard, etc.)
│   ├── hooks/              # Custom React hooks
│   ├── lib/                # Utility libraries
│   ├── config/             # Configuration files
│   ├── types/              # TypeScript types/interfaces
│   ├── utils/              # Utility/helper functions
│   └── index.css, App.css, fonts.css  # Styling
├── tailwind.config.ts      # Tailwind CSS configuration
├── vite.config.ts          # Vite build configuration
├── tsconfig*.json          # TypeScript configuration
└── ...
```

---

## Languages & Technologies Used

### Languages
- **TypeScript:** Main language for all React components and logic.
- **JavaScript:** For build/configuration scripts.
- **CSS:** (Tailwind CSS) for styling.

### Frameworks & Libraries
- **React:** UI library for building interactive interfaces.
- **Vite:** Fast build tool for modern web projects.
- **Tailwind CSS:** Utility-first CSS framework.
- **Civic Auth (`@civic/auth`, `@civic/auth-web3`):** Decentralized identity and authentication.
- **React Router:** For client-side routing.
- **Radix UI:** Accessible, unstyled UI primitives.
- **Lucide React:** Icon library.
- **Firebase:** (If used, for backend/database/storage).
- **Zod:** Schema validation.
- **TanStack React Query:** Data fetching and caching.
- **Wagmi, WalletConnect, Solana Wallet Adapter:** For potential blockchain/wallet integrations.

---

## Summary

**RentRight** is a modern, decentralized rental platform that puts user trust, privacy, and experience first. By leveraging Civic Auth, it ensures that all users are securely verified in a privacy-preserving manner, fostering a safer rental ecosystem for both tenants and landlords. The project is built with a robust, scalable structure using industry-standard technologies and best practices in web development.

---
Component: The 
CivicAuthButton
 component manages the entire Civic authentication flow, including sign-in, role selection, and redirection to the appropriate dashboard.
Provider: The app is wrapped in a CivicAuthProvider (see 
App.tsx
), ensuring Civic Auth context is available throughout the app.
Role Storage: Upon successful authentication, the user’s role (tenant or landlord) is stored locally and used for personalized redirection and dashboard rendering.
UX: The onboarding flow is smooth—users see clear status indicators (e.g., “Signing in with Civic...”, “Redirecting...”), and are prompted to select their role after authentication.
Benefits of Civic Auth
Decentralized Identity: Users control their own identity, reducing the risk of centralized data breaches.
Privacy: Only necessary information is shared, and users can prove their identity without exposing sensitive data.
Trust: Both tenants and landlords can trust that the other party has been verified, reducing fraud and increasing confidence.
Seamless Experience: Civic Auth provides a frictionless, single-click verification experience, improving user onboarding.
Project Structure
Home_Rental_Dapp/
│
├── .env                    # Environment variables
├── .gitignore
├── README.md               # Project documentation
├── bun.lockb / package-lock.json / package.json  # Dependency management
├── public/                 # Static assets (images, etc.)
├── src/                    # Main source code
│   ├── App.tsx             # Main React App component
│   ├── main.tsx            # Entry point
│   ├── firebase.ts         # Firebase integration (if used)
│   ├── components/         # Reusable UI and logic components
│   │   ├── CivicAuthButton.tsx   # Civic Auth integration
│   │   ├── Dashboard.tsx         # Main dashboard UI
│   │   ├── ...                   # Other UI components (Hero, Header, etc.)
│   ├── pages/              # Page-level components (TenantDashboard, LandlordDashboard, etc.)
│   ├── hooks/              # Custom React hooks
│   ├── lib/                # Utility libraries
│   ├── config/             # Configuration files
│   ├── types/              # TypeScript types/interfaces
│   ├── utils/              # Utility/helper functions
│   └── index.css, App.css, fonts.css  # Styling
├── tailwind.config.ts      # Tailwind CSS configuration
├── vite.config.ts          # Vite build configuration
├── tsconfig*.json          # TypeScript configuration
└── ...
Languages & Technologies Used
Languages
TypeScript: Main language for all React components and logic.
JavaScript: For build/configuration scripts.
CSS: (Tailwind CSS) for styling.
Frameworks & Libraries
React: UI library for building interactive interfaces.
Vite: Fast build tool for modern web projects.
Tailwind CSS: Utility-first CSS framework.
Civic Auth (@civic/auth, @civic/auth-web3): Decentralized identity and authentication.
React Router: For client-side routing.
Radix UI: Accessible, unstyled UI primitives.
Lucide React: Icon library.
Firebase: (If used, for backend/database/storage).
Zod: Schema validation.
TanStack React Query: Data fetching and caching.
Wagmi, WalletConnect, Solana Wallet Adapter: For potential blockchain/wallet integrations.
Summary
RentRight is a modern, decentralized rental platform that puts user trust, privacy, and experience first. By leveraging Civic Auth, it ensures that all users are securely verified in a privacy-preserving manner, fostering a safer rental ecosystem for both tenants and landlords. The project is built with a robust, scalable structure using industry-standard technologies and best practices in web development.