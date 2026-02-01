# Setup Notes - Chandru's Environment

## Current Configuration

This project is now configured for Chandru's Supabase account:

- **Email**: chandru29450@gmail.com
- **Supabase Project**: ouvmorkswjfqgbmcopvb
- **Project URL**: https://ouvmorkswjfqgbmcopvb.supabase.co

## Next Steps

### 1. Ensure User Account Exists

In your Supabase dashboard (https://supabase.com/dashboard):

1. Select project: `ouvmorkswjfqgbmcopvb`
2. Go to **Authentication** → **Users**
3. Verify user exists:
   - Email: `chandru29450@gmail.com`
   - Password: `Chandru29450`
   
If not created yet:
- Click **"Add user"** → **"Create new user"**
- Enter the email and password above
- ✅ Check "Auto Confirm User"
- Click **"Create user"**

### 2. Run Database Migrations

If you haven't already run the database migration:

1. Go to your Supabase project → **SQL Editor**
2. Click **"New Query"**
3. Copy and paste the contents from:
   ```
   supabase/migrations/20260129151934_5d664c82-301d-4545-b99f-2a3bdab3bfd6.sql
   ```
4. Click **"Run"**

This creates the `profiles` table and necessary triggers.

### 3. Start Development

```bash
npm install
npm run dev
```

The app will run on http://localhost:5173

### 4. Login

Use the credentials:
- Email: `chandru29450@gmail.com`
- Password: `Chandru29450`

## Files Configured

- ✅ `.env` - Updated with Chandru's Supabase credentials
- ✅ `.env.example` - Updated template
- ✅ `supabase/config.toml` - Project ID updated
- ✅ `.gitignore` - Environment files protected

## Security Reminder

🔒 The `.env` file contains your Supabase credentials and is excluded from git. Never commit sensitive credentials to your repository.
