# 🚨 URGENT: Security Fix Required

GitGuardian detected your MongoDB credentials were exposed. Follow these steps immediately:

## Step 1: Change MongoDB Password (Do this NOW!)

1. Go to https://cloud.mongodb.com/
2. Login to your account
3. Select your cluster "CapsPro"
4. Go to "Database Access"
5. Find user `sumant`
6. Click "Edit" → "Edit Password"
7. Generate a new strong password (or use this): `${Math.random().toString(36).slice(-12)}Aa1!`
8. Click "Update User"

## Step 2: Update Your Local .env File

Update `server/.env` with the new password:
```
MONGODB_URI=mongodb+srv://sumant:YOUR_NEW_PASSWORD@capspro.ot4sxmk.mongodb.net/attendance_system?retryWrites=true&w=majority&appName=CapsPro
```

## Step 3: Generate New Secrets

Run this command to generate new secrets:
```bash
node -e "console.log('JWT_ACCESS_SECRET=' + require('crypto').randomBytes(64).toString('hex'))"
node -e "console.log('JWT_REFRESH_SECRET=' + require('crypto').randomBytes(64).toString('hex'))"
node -e "console.log('QR_SECRET=' + require('crypto').randomBytes(64).toString('hex'))"
```

Update these in your `server/.env` file.

## Step 4: Verify .env is Not Tracked

The `.env` file should NOT be in git. It's already in `.gitignore`, so you're safe going forward.

## Why This Happened

Your `.env` file was likely committed before `.gitignore` was set up, or the credentials were shown in documentation files.

## What We Fixed

✅ Added SECURITY.md with security guidelines
✅ Kept demo credentials in README (these are for local testing only)
✅ `.env` is properly ignored by git

## Next Steps

After changing your MongoDB password and updating `.env`:
1. Test your application locally
2. The exposed credentials will be useless once you change them
3. Delete this file after completing the steps
