# Security Notice

## Important: Change Default Credentials

⚠️ **The credentials shown in README.md are for demo/development purposes only.**

### Before deploying to production:

1. **Change MongoDB Password:**
   - Go to MongoDB Atlas
   - Change the password for user `sumant`
   - Update `MONGODB_URI` in your `.env` file

2. **Generate New Secrets:**
   ```bash
   # Generate random secrets for production
   node -e "console.log(require('crypto').randomBytes(64).toString('hex'))"
   ```
   - Update `JWT_ACCESS_SECRET`
   - Update `JWT_REFRESH_SECRET`
   - Update `QR_SECRET`

3. **Change Admin Password:**
   - Set `ADMIN_PASSWORD` in `.env` to a strong password
   - Run the seed script to create admin with new password

4. **Never commit `.env` files:**
   - `.env` is already in `.gitignore`
   - Only commit `.env.example` with placeholder values

## Current Security Measures

- JWT-based authentication
- Password hashing with bcrypt (10 rounds)
- HMAC-SHA256 signed QR codes
- Rate limiting on API endpoints
- Helmet.js for security headers
- CORS configuration
- Geofencing validation

## Reporting Security Issues

If you find a security vulnerability, please email: sumant@college.edu
