# Benjamin AI - Development Setup Guide

This guide will help you set up the development environment for Benjamin AI Assistant.

## Prerequisites

Before you begin, ensure you have the following installed:

- **Node.js** >= 18.0.0 ([Download](https://nodejs.org/))
- **npm** >= 9.0.0 (comes with Node.js)
- **Git** ([Download](https://git-scm.com/))
- **VS Code** (recommended) or your preferred IDE

## Project Structure

```
benjamin-ai/
├── docs/                  # Documentation
├── paraflow/             # Design resources (DO NOT MODIFY)
│   ├── Archive/          # Legacy draft documents
│   ├── Feature Plan/     # Product specifications
│   ├── Global Context/   # Strategy & personas
│   ├── Screen & Prototype/ # 22 HTML UI components
│   └── Style Guide/      # Design system
├── src/                  # Source code (to be created)
│   ├── app/             # Next.js 14 app router
│   ├── components/      # React components
│   ├── lib/             # Utilities
│   └── styles/          # Global styles
├── public/              # Static assets
├── package.json         # Dependencies
├── tsconfig.json        # TypeScript config
└── .env.local           # Environment variables (create from .env.example)
```

## Step 1: Clone Repository

```bash
git clone <your-repository-url>
cd paraflow-project-ee336066
```

## Step 2: Install Dependencies

```bash
npm install
```

This will install:
- Next.js 14 (React framework)
- TypeScript (type safety)
- Tailwind CSS (styling)
- Supabase SDK (backend)
- Anthropic SDK (Claude AI)

## Step 3: Set Up Environment Variables

1. Copy the example environment file:
```bash
cp .env.example .env.local
```

2. Edit `.env.local` and fill in your credentials:

### Required for Development:
```env
# Supabase (see Step 4)
NEXT_PUBLIC_SUPABASE_URL=https://your-project.supabase.co
NEXT_PUBLIC_SUPABASE_ANON_KEY=your-anon-key

# Anthropic Claude AI (see Step 5)
ANTHROPIC_API_KEY=sk-ant-api03-your-key
```

### Optional (for production):
- Azure AD credentials (for SSO)
- PubMed API key
- Monitoring tools (Sentry, Analytics)

## Step 4: Set Up Supabase Backend

### 4.1 Create Supabase Project

1. Go to [supabase.com](https://supabase.com)
2. Click "New Project"
3. Choose **Frankfurt** region (EU GDPR compliance)
4. Note your project URL and anon key

### 4.2 Run Database Migrations

Execute the SQL from `paraflow/Feature Plan/supabase_technical_specification.md`:

1. Open Supabase SQL Editor
2. Copy the schema from the technical spec (lines 200-400)
3. Run the SQL to create tables:
   - `profiles`
   - `ai_queries`
   - `epicrisis_generations`
   - `knowledge_base`
   - `audit_logs`

### 4.3 Set Up Row Level Security (RLS)

Copy and run the RLS policies from the technical specification to ensure GDPR compliance.

### 4.4 Deploy Edge Functions

```bash
# Install Supabase CLI
npm install -g supabase

# Login to Supabase
supabase login

# Link your project
supabase link --project-ref your-project-id

# Deploy functions (from technical spec)
supabase functions deploy benjamin-query
supabase functions deploy epicrisis-generate
supabase functions deploy translator
```

## Step 5: Get Anthropic API Key

1. Go to [console.anthropic.com](https://console.anthropic.com/)
2. Create an account or sign in
3. Navigate to API Keys
4. Create a new key
5. Add to `.env.local` as `ANTHROPIC_API_KEY`

**Note:** Claude Sonnet 4.5 is recommended for production.

## Step 6: Initialize Next.js Project Structure

Create the basic folder structure:

```bash
mkdir -p src/app src/components src/lib src/styles public
```

### 6.1 Create Root Layout

Create `src/app/layout.tsx`:
```typescript
import type { Metadata } from 'next'
import './globals.css'

export const metadata: Metadata = {
  title: 'Benjamin AI - Klinický Asistent',
  description: 'AI asistent pro české lékaře',
}

export default function RootLayout({
  children,
}: {
  children: React.ReactNode
}) {
  return (
    <html lang="cs">
      <body>{children}</body>
    </html>
  )
}
```

### 6.2 Create Home Page

Create `src/app/page.tsx`:
```typescript
export default function Home() {
  return (
    <main className="min-h-screen p-8">
      <h1 className="text-3xl font-bold text-green-600">
        Benjamin AI
      </h1>
      <p className="mt-4">Klinický AI Asistent pro české lékaře</p>
    </main>
  )
}
```

### 6.3 Create Tailwind Config

Create `tailwind.config.ts`:
```typescript
import type { Config } from 'tailwindcss'

const config: Config = {
  content: [
    './src/**/*.{js,ts,jsx,tsx,mdx}',
  ],
  theme: {
    extend: {
      colors: {
        'benjamin-green': '#5CB85C',
      },
    },
  },
  plugins: [],
}
export default config
```

### 6.4 Create Global Styles

Create `src/app/globals.css`:
```css
@tailwind base;
@tailwind components;
@tailwind utilities;

:root {
  --benjamin-primary: #5CB85C;
}
```

## Step 7: Start Development Server

```bash
npm run dev
```

Open [http://localhost:3000](http://localhost:3000) in your browser.

## Step 8: Convert HTML Components to React

The `paraflow/Screen & Prototype/` directory contains 22 HTML components. Convert them to React:

### Example: Converting Chat Component

1. Study `paraflow/Screen & Prototype/benjamin_chat_green.html`
2. Create `src/components/Chat.tsx`
3. Extract Tailwind classes from HTML
4. Create React component with TypeScript

Reference the **Design System** in `paraflow/Style Guide/benjamin_green_healthcare.style-guide.md` for:
- Color palette
- Typography
- Spacing
- Component specifications

## Development Workflow

### Daily Development
```bash
# Start dev server
npm run dev

# Type checking
npm run type-check

# Linting
npm run lint

# Format code
npm run format
```

### Before Committing
```bash
npm run type-check && npm run lint
```

## Next Steps

1. ✅ Environment setup complete
2. 📖 Read `paraflow/Feature Plan/prd_mvp.md` for product requirements
3. 🎨 Review `paraflow/Style Guide/` for design system
4. 🧩 Start converting HTML components to React
5. 🔌 Integrate Supabase client
6. 🤖 Implement Claude AI integration
7. 📝 Build Chat interface
8. 📄 Build Epicrisis generator
9. 🌍 Build Translator feature

## Troubleshooting

### Port 3000 already in use
```bash
# Use different port
npm run dev -- -p 3001
```

### TypeScript errors
```bash
# Clear Next.js cache
rm -rf .next
npm run dev
```

### Supabase connection issues
- Check `.env.local` variables
- Verify Supabase project is running
- Check network/firewall settings

## Resources

- **Product Requirements:** `paraflow/Feature Plan/prd_mvp.md`
- **Technical Spec:** `paraflow/Feature Plan/supabase_technical_specification.md`
- **Design System:** `paraflow/Style Guide/benjamin_green_healthcare.style-guide.md`
- **Component Docs:** `paraflow/Feature Plan/benjamin_component_documentation.md`
- **User Flows:** `paraflow/Feature Plan/user_flow.md`

## Support

For questions or issues:
1. Check documentation in `paraflow/Feature Plan/`
2. Review technical specifications
3. Consult design system guide

---

**Ready to start building!** 🚀
