# GitHub Actions Deployment Setup

This guide will help you set up automated deployment for your Gymcyclopedia project using GitHub Actions.

## 🚀 Features of This GitHub Actions Setup

- ✅ **Automated Deployment**: Deploys on every push to main branch
- ✅ **Manual Triggering**: Can trigger deployments manually
- ✅ **Pull Request Previews**: Creates preview deployments for PRs
- ✅ **HTML Validation**: Checks HTML structure before deployment
- ✅ **Configuration Validation**: Ensures Supabase config is proper
- ✅ **Multi-platform Support**: Supports both Netlify and GitHub Pages
- ✅ **Health Checks**: Post-deployment verification

## 🔧 Step-by-Step Setup

### Step 1: Get Your Netlify Credentials

1. **Log in to Netlify**: Go to [netlify.com](https://netlify.com)
2. **Get Site ID**:
   - Go to your site dashboard
   - Navigate to Site Settings > General
   - Copy the **Site ID** (under Site information)
3. **Get Auth Token**:
   - Go to User Settings > Applications
   - Click "New access token"
   - Name it "GitHub Actions"
   - Copy the generated token

### Step 2: Configure GitHub Repository Secrets

1. **Go to your GitHub repository**
2. **Navigate to Settings > Secrets and variables > Actions**
3. **Add these Repository Secrets**:

   ```
   NETLIFY_AUTH_TOKEN = your_netlify_auth_token_here
   NETLIFY_SITE_ID = your_netlify_site_id_here
   ```

4. **Optional - Add Supabase secrets** (if you want environment-based config):
   ```
   SUPABASE_URL = https://stojhqobywrvkjaabcvq.supabase.co
   SUPABASE_ANON_KEY = your_supabase_anon_key_here
   ```

### Step 3: Enable GitHub Actions

1. **Go to your repository's Actions tab**
2. **Enable workflows** if prompted
3. **The workflow will automatically run** on the next push to main

## 🎯 How It Works

### Trigger Events
- **Push to main**: Automatic production deployment
- **Pull Request**: Creates preview deployment
- **Manual**: Can be triggered from Actions tab

### Deployment Process
1. **Code Checkout**: Downloads your latest code
2. **Validation**: Checks HTML structure and Supabase config
3. **Environment Setup**: Prepares Node.js environment
4. **Deployment**: Deploys to Netlify (or GitHub Pages)
5. **Health Check**: Verifies deployment success

### Build Steps
```yaml
✅ Checkout code
✅ Setup Node.js environment
✅ Cache dependencies
✅ Install dependencies (if needed)
✅ Validate HTML files
✅ Check Supabase configuration
✅ Replace environment variables
✅ Build project (if needed)
✅ Deploy to platform
✅ Run health checks
```

## 🔄 Alternative Deployment Options

### Option 1: Netlify (Default - Recommended)
- ✅ **Best for**: Static sites with forms and functions
- ✅ **Features**: Preview deployments, form handling, edge functions
- ✅ **Setup**: Configure `NETLIFY_AUTH_TOKEN` and `NETLIFY_SITE_ID`

### Option 2: GitHub Pages
- ✅ **Best for**: Simple static sites
- ✅ **Features**: Free hosting, custom domains
- ✅ **Setup**: Change `if: false` to `if: true` in deploy.yml

## 📊 Monitoring Your Deployments

### GitHub Actions Dashboard
1. Go to **Actions** tab in your repository
2. View deployment history and logs
3. Check for any failed deployments

### Netlify Dashboard
1. Monitor live deployments
2. View deployment logs
3. Manage domain settings

## 🛠 Customization Options

### Adding Build Steps
If you need custom build steps, modify the workflow:

```yaml
- name: Custom build step
  run: |
    # Add your custom commands here
    echo "Running custom build..."
```

### Environment Variables
Add more secrets in GitHub for different environments:

```yaml
env:
  CUSTOM_VAR: ${{ secrets.CUSTOM_VAR }}
```

### Notification Integration
Add Slack/Discord notifications:

```yaml
- name: Notify deployment
  uses: 8398a7/action-slack@v3
  with:
    status: ${{ job.status }}
    webhook_url: ${{ secrets.SLACK_WEBHOOK }}
```

## 🚨 Troubleshooting

### Common Issues

1. **"NETLIFY_AUTH_TOKEN not found"**
   - Ensure you've added the secret in GitHub repository settings
   - Check spelling of secret names

2. **"HTML validation failed"**
   - Check your HTML files for proper DOCTYPE and closing tags
   - Ensure all HTML files are well-formed

3. **"Supabase configuration issues"**
   - Verify your Supabase URLs and keys are correct
   - Ensure no placeholder values remain

4. **"Deployment failed"**
   - Check the Actions logs for specific error messages
   - Verify Netlify site ID is correct

### Debug Mode
Enable debug logging by adding this to your workflow:

```yaml
env:
  ACTIONS_RUNNER_DEBUG: true
  ACTIONS_STEP_DEBUG: true
```

## 🎉 Success Indicators

When everything is working correctly, you'll see:

- ✅ Green checkmarks in the Actions tab
- ✅ Automatic deployments on push to main
- ✅ Preview URLs for pull requests
- ✅ Deployment notifications in commits

## 📞 Support

If you encounter issues:
1. Check the Actions logs for detailed error messages
2. Verify all secrets are properly configured
3. Test locally first using `http://localhost:8080`
4. Check Netlify dashboard for deployment status

Your Gymcyclopedia project will now have professional CI/CD capabilities! 🚀 