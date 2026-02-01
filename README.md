# Digital Gold Rate Monitor

A modern, real-time gold price monitoring dashboard built with React, TypeScript, and Supabase.

## Features

- 📊 Real-time gold price tracking (USD & INR)
- 📈 Interactive price charts with multiple timeframes
- 💰 Asset portfolio tracking with automatic growth calculation
- 🔐 Secure authentication with Supabase
- 📱 Responsive design for all devices
- ✨ Modern UI with smooth animations

## How can I edit this code?

There are several ways of editing your application.

**Use Lovable**

Simply visit the [Lovable Project](https://lovable.dev/projects/REPLACE_WITH_PROJECT_ID) and start prompting.

Changes made via Lovable will be committed automatically to this repo.

**Use your preferred IDE**

If you want to work locally using your own IDE, you can clone this repo and push changes. Pushed changes will also be reflected in Lovable.

The only requirement is having Node.js & npm installed - [install with nvm](https://github.com/nvm-sh/nvm#installing-and-updating)

Follow these steps:

```sh
# Step 1: Clone the repository using the project's Git URL.
git clone <YOUR_GIT_URL>

# Step 2: Navigate to the project directory.
cd <YOUR_PROJECT_NAME>

# Step 3: Install the necessary dependencies.
npm i

# Step 4: Copy the environment variables template
cp .env.example .env

# Step 5: Edit .env and add your Supabase credentials

# Step 6: Start the development server with auto-reloading and an instant preview.
npm run dev
```

**Edit a file directly in GitHub**

- Navigate to the desired file(s).
- Click the "Edit" button (pencil icon) at the top right of the file view.
- Make your changes and commit the changes.

**Use GitHub Codespaces**

- Navigate to the main page of your repository.
- Click on the "Code" button (green button) near the top right.
- Select the "Codespaces" tab.
- Click on "New codespace" to launch a new Codespace environment.
- Edit files directly within the Codespace and commit and push your changes once you're done.

## What technologies are used for this project?

This project is built with:

- **Vite** - Fast build tool and dev server
- **TypeScript** - Type-safe JavaScript
- **React** - UI library
- **shadcn-ui** - Beautiful, accessible components
- **Tailwind CSS** - Utility-first CSS framework
- **Supabase** - Backend as a service (Auth + Database)
- **Recharts** - Charting library
- **React Query** - Data fetching and caching

## How can I deploy this project?

### Deploy to Netlify

This project is optimized for Netlify deployment. See the [DEPLOYMENT.md](./DEPLOYMENT.md) guide for detailed instructions.

**Quick Deploy:**

1. Push your code to GitHub
2. Connect your repo to Netlify
3. Add environment variables in Netlify dashboard:
   - `VITE_SUPABASE_URL`
   - `VITE_SUPABASE_PUBLISHABLE_KEY`
   - `VITE_SUPABASE_PROJECT_ID`
4. Deploy!

Netlify will automatically detect the build settings from `netlify.toml`.

### Alternative Deployment

You can also deploy to:
- Vercel
- Railway
- Render
- Any platform that supports Vite/React apps

## Environment Variables

Create a `.env` file in the root directory with the following variables:

```env
VITE_SUPABASE_PROJECT_ID=your_project_id
VITE_SUPABASE_PUBLISHABLE_KEY=your_publishable_key
VITE_SUPABASE_URL=https://your-project-id.supabase.co
```

See `.env.example` for a template.

## Custom Domain

You can connect a custom domain through your Netlify dashboard:

1. Go to Site settings > Domain management
2. Click "Add custom domain"
3. Follow the DNS configuration instructions

## License

This project is open source and available under the MIT License.
