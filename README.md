# Grocify 🛒📱

Grocify is a full-stack, cross-platform mobile application designed to simplify grocery shopping and meal planning. Built on top of **React Native** and **Expo**, the app delivers an optimized mobile interface backed by a modern, type-safe cloud data layer.

## 🚀 Core Features

* **User Authentication:** Secure sign-in and session management powered by **Clerk Architecture**.
* **Global State Architecture:** Clean, predictable data rendering managed through **Redux Toolkit**.
* **Relational Database:** Real-time grocery management powered by a serverless **Neon PostgreSQL** backend.
* **Type-Safe ORM:** High-performance database operations executed through **Drizzle ORM** with local schema migrations.
* **File-Based Routing:** Seamless mobile layout transitions via **Expo Router** navigation stacks.
* **Serverless API Endpoints:** Integrated full-stack API request handlers routing data securely down to database schemas.

## 📁 Project Architecture

```text
Grocify/
├── src/
│   ├── app/               # Expo Router pages, tabs, and Serverless API routes (+api.ts)
│   ├── components/        # Reusable presentation layout UI blocks
│   ├── lib/
│   │   └── server/
│   │       └── db/        # Drizzle ORM configuration and database schema files
│   ├── store/             # Redux/Zustand global data states (grocery-store.ts)
│   └── styles/            # Unified design system and layout stylesheets
├── scripts/               # Custom database seed engines (seed-grocery.cjs)
├── drizzle.config.ts      # Drizzle migration and connection orchestrator
├── eas.json               # Expo Application Services configuration profiles
└── tsconfig.json          # Strict type-checking rules configuration
```

## 🛠️ Tech Stack & Tooling

* **Frontend Framework:** React Native (Expo SDK 57)
* **Language Layer:** TypeScript (Strict compiler validation)
* **Database Driver:** `@neondatabase/serverless` (PostgreSQL)
* **Object Relational Mapper:** Drizzle ORM / Drizzle-Kit
* **State Operations:** Redux Toolkit / Client Side Store Handlers

## 🏃‍♂️ Local Installation and Setup

Follow these steps to run the development environment locally:

### 1. Clone the Repository
```bash
git clone https://github.com
cd Grocify
```

### 2. Install Development Packages
```bash
npm install
```

### 3. Establish Your Local Environment Variables
Create a `.env` file in your root folder and map out your development keys:
```env
DATABASE_URL=your_neon_postgres_string
EXPO_PUBLIC_CLERK_PUBLISHABLE_KEY=your_clerk_key
```

### 4. Setup the Database Schema and Seed Data
Sync your tables with Neon and seed the database using Drizzle-Kit and `cross-env`:
```bash
npx drizzle-kit push
npx cross-env DATABASE_URL="YOUR_NEON_STRING" node ./scripts/seed-grocery.cjs
```

### 5. Launch the Bundle Server
Launch the Metro Bundler on your machine:
```bash
npx expo start
```
*Press `a` to run on an Android device emulator, or use the Expo Go app to test over your local network connection.*

## 📄 License
This project is open-source and available under the [MIT License](LICENSE).
