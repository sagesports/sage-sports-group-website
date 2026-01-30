# Sage Sports Group Website - Deployment Instructions

## What You'll Need
1. GitHub account (free)
2. Netlify account (free)
3. Access to your Squarespace domain settings

## Step 1: Prepare Your Files

You should have these files:
- `sage-sports-group.html` (your website)
- `sage-logo-white.png` (logo)
- `colin-montague.jpg` (Colin's photo)
- `paul-sabin.png` (Paul's photo)
- `netlify.toml` (configuration file)

**IMPORTANT**: Rename `sage-sports-group.html` to `index.html` before uploading.

## Step 2: Create a GitHub Repository

1. Go to https://github.com and sign in (or create account)
2. Click the "+" icon in top right → "New repository"
3. Name it: `sage-sports-group-website`
4. Make it **Public** (required for free Netlify)
5. Don't check any boxes yet
6. Click "Create repository"

### Upload Your Files to GitHub:

**Option A - Upload via web interface (easier):**
1. On your new repo page, click "uploading an existing file"
2. Drag and drop ALL your files:
   - index.html (the renamed sage-sports-group.html)
   - sage-logo-white.png
   - colin-montague.jpg
   - paul-sabin.png
   - netlify.toml
3. Click "Commit changes"

**Option B - Use GitHub Desktop (if you prefer):**
1. Download GitHub Desktop
2. Clone your repository
3. Copy all files into the folder
4. Commit and push

## Step 3: Deploy to Netlify

1. Go to https://www.netlify.com and sign up (use "Sign up with GitHub")
2. Click "Add new site" → "Import an existing project"
3. Choose "Deploy with GitHub"
4. Authorize Netlify to access your GitHub
5. Select your `sage-sports-group-website` repository
6. **Build settings:**
   - Build command: (leave empty)
   - Publish directory: `.` (just a period)
7. Click "Deploy site"

Wait 1-2 minutes for deployment to complete!

## Step 4: Configure Form Notifications

1. In Netlify, go to your site dashboard
2. Click "Site settings" → "Forms"
3. Your "contact" form should appear
4. Click on it → "Form notifications"
5. Click "Add notification" → "Email notification"
6. Add email: **info@sagesportsgroup.com**
7. Save

Now when someone submits the form, you'll get an email at info@sagesportsgroup.com!

## Step 5: Connect Your Custom Domain

### In Netlify:
1. Go to "Domain settings" in your site dashboard
2. Click "Add custom domain"
3. Enter: `sagesportsgroup.com`
4. Click "Verify"
5. Netlify will show you DNS records to add

### In Squarespace:
1. Log into Squarespace
2. Go to Settings → Domains
3. Click on `sagesportsgroup.com`
4. Click "DNS Settings" or "Advanced DNS Settings"
5. **Add these DNS records** (Netlify will show you the exact values):
   - **A Record**: `@` → (Netlify's IP, usually `75.2.60.5`)
   - **CNAME**: `www` → (your Netlify subdomain, like `sage-sports-group.netlify.app`)

**Note**: DNS changes can take 24-48 hours to propagate, but usually it's within a few hours.

### Alternative - Point Entire Domain:
In Squarespace DNS settings, you can also:
1. Remove existing A records
2. Add Netlify's A record: `75.2.60.5`
3. Update CNAME for www subdomain

## Step 6: Enable HTTPS (Free SSL)

1. Back in Netlify, go to "Domain settings"
2. Scroll to "HTTPS" section
3. Click "Verify DNS configuration"
4. Once verified, click "Provision certificate"
5. Wait a few minutes for SSL to activate

Your site will now be secure with HTTPS!

## BONUS: View Form Submissions

Two ways to see form submissions:

### Option 1 - In Netlify Dashboard (Free):
1. Go to your site → "Forms" tab
2. Click on your contact form
3. See all submissions with timestamps

### Option 2 - Send to Google Sheets (Free with Zapier):
1. Sign up at https://zapier.com (free tier works)
2. Create a new Zap:
   - Trigger: "Netlify" → "New Form Submission"
   - Action: "Google Sheets" → "Create Spreadsheet Row"
3. Connect your Netlify account
4. Select your form
5. Connect Google Sheets and map the fields

Now submissions go to both email AND a Google Sheet!

## Troubleshooting

**Form not working?**
- Make sure you renamed the HTML file to `index.html`
- Check that `data-netlify="true"` is in the form tag
- Verify the hidden `form-name` input exists

**Domain not connecting?**
- Wait 24-48 hours for DNS propagation
- Use https://www.whatsmydns.net to check DNS propagation
- Make sure you removed conflicting DNS records in Squarespace

**Site not updating?**
- Push changes to GitHub
- Netlify auto-deploys on every push (takes 1-2 minutes)
- Check the "Deploys" tab in Netlify for status

## Cost Breakdown

- GitHub: **FREE**
- Netlify hosting: **FREE**
- Netlify forms (100/month): **FREE**
- SSL certificate: **FREE**
- Bandwidth (100GB/month): **FREE**

Only cost is your existing domain registration fee at Squarespace!

## Need Help?

Contact Netlify support (they're very responsive) or check:
- https://docs.netlify.com
- https://answers.netlify.com

---

**Quick checklist before deploying:**
- [ ] Renamed HTML file to `index.html`
- [ ] All image files are in the same folder
- [ ] Files uploaded to GitHub
- [ ] Connected to Netlify
- [ ] Form email notifications configured
- [ ] Domain DNS updated in Squarespace
- [ ] SSL certificate enabled
