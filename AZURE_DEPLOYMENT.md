# Azure Deployment Guide

This guide will help you deploy the PixelPaw Virtual Pet App and Sprint KPIs Dashboard to Azure Static Web Apps.

## Prerequisites

- An Azure account ([Create one for free](https://azure.microsoft.com/free/))
- Azure CLI installed ([Install Azure CLI](https://docs.microsoft.com/cli/azure/install-azure-cli))
- Git installed
- Your project code in a Git repository (GitHub, Azure DevOps, or Bitbucket)

## Deployment Options

### Option 1: Deploy via Azure Portal (Recommended for Beginners)

#### Step 1: Create Azure Static Web App

1. Go to [Azure Portal](https://portal.azure.com)
2. Click **"Create a resource"**
3. Search for **"Static Web App"**
4. Click **"Create"**

#### Step 2: Configure Basic Settings

Fill in the following information:

- **Subscription**: Select your Azure subscription
- **Resource Group**: Create new or select existing
- **Name**: Enter a unique name (e.g., `pixelpaw-app`)
- **Plan type**: Choose **Free** (for testing) or **Standard** (for production)
- **Region**: Select the closest region to your users
- **Source**: Choose your Git provider (GitHub, Azure DevOps, or Bitbucket)

#### Step 3: Configure Deployment Details

**For GitHub:**
- Sign in to GitHub if prompted
- Select your **Organization** and **Repository**
- Select **Branch**: `main`
- **Build Presets**: Select **Custom**
- **App location**: `/` (root directory)
- **Api location**: Leave empty
- **Output location**: Leave empty (static files are in root)

**For Azure DevOps:**
- Select your **Organization** and **Project**
- Select your **Repository**
- Select **Branch**: `main`
- Configure build settings as above

#### Step 4: Review and Create

1. Review your settings
2. Click **"Review + create"**
3. Click **"Create"**

Azure will automatically:
- Create the Static Web App
- Set up GitHub Actions (if using GitHub)
- **Automatically add the deployment token** to your GitHub repository secrets as `AZURE_STATIC_WEB_APPS_API_TOKEN`
- Deploy your application
- Provide you with a URL (e.g., `https://pixelpaw-app.azurestaticapps.net`)

**Important**: If you created the Static Web App manually or the secret wasn't added automatically:

1. Go to your Static Web App in Azure Portal
2. Navigate to **"Manage deployment token"**
3. Copy the deployment token
4. Go to your GitHub repository → **Settings** → **Secrets and variables** → **Actions**
5. Click **"New repository secret"**
6. Name: `AZURE_STATIC_WEB_APPS_API_TOKEN`
7. Value: Paste the deployment token
8. Click **"Add secret"**

### Option 2: Deploy via Azure CLI

#### Step 1: Login to Azure

```bash
az login
```

#### Step 2: Create Resource Group

```bash
az group create --name pixelpaw-rg --location eastus
```

#### Step 3: Create Static Web App

```bash
az staticwebapp create \
  --name pixelpaw-app \
  --resource-group pixelpaw-rg \
  --location eastus \
  --sku Free
```

#### Step 4: Deploy from Local Directory

```bash
# Navigate to your project directory
cd C:\Projects\PetApp

# Deploy using Azure Static Web Apps CLI
az staticwebapp deploy \
  --name pixelpaw-app \
  --resource-group pixelpaw-rg \
  --app-location "/" \
  --output-location ""
```

### Option 3: Deploy via GitHub Actions (Automatic)

If you've already set up the Static Web App via Azure Portal, GitHub Actions will automatically deploy on every push to `main`.

#### Step 1: Get Deployment Token

1. Go to your Static Web App in Azure Portal
2. Navigate to **"Manage deployment token"**
3. Copy the deployment token

#### Step 2: Add Secret to GitHub

1. Go to your GitHub repository
2. Navigate to **Settings** → **Secrets** → **Actions**
3. Click **"New repository secret"**
4. Name: `AZURE_STATIC_WEB_APPS_API_TOKEN`
5. Value: Paste the deployment token
6. Click **"Add secret"**

#### Step 3: Push to GitHub

The workflow file (`.github/workflows/azure-static-web-apps.yml`) is already configured. Just push your code:

```bash
git add .
git commit -m "Add Azure deployment configuration"
git push origin main
```

GitHub Actions will automatically build and deploy your app.

## Configuration Files

### staticwebapp.config.json

This file configures routing and behavior for Azure Static Web Apps:

- **navigationFallback**: Routes all requests to `index.html` except specific files
- **routes**: Defines custom routes for specific pages
- **responseOverrides**: Handles 404 errors by serving `index.html`
- **globalHeaders**: Sets security headers including Content Security Policy
- **mimeTypes**: Defines MIME types for various file formats

### GitHub Actions Workflow

The `.github/workflows/azure-static-web-apps.yml` file:
- Triggers on pushes to `main` branch
- Triggers on pull requests
- Builds and deploys automatically
- Handles PR preview deployments

## Post-Deployment

### Access Your Application

After deployment, your app will be available at:
```
https://<your-app-name>.azurestaticapps.net
```

### Custom Domain (Optional)

1. Go to your Static Web App in Azure Portal
2. Navigate to **"Custom domains"**
3. Click **"Add"**
4. Follow the instructions to add your domain

### Environment Variables (If Needed)

If you need environment variables:

1. Go to your Static Web App in Azure Portal
2. Navigate to **"Configuration"**
3. Add application settings
4. These will be available as environment variables

## File Structure for Deployment

Your project structure should be:

```
PetApp/
├── index.html                    # Main application
├── sprint-kpis-dragons.html     # Sprint KPIs dashboard
├── script.js                     # JavaScript code
├── styles.css                    # CSS styles
├── staticwebapp.config.json      # Azure configuration
├── .github/
│   └── workflows/
│       └── azure-static-web-apps.yml  # CI/CD workflow
└── sounds/                       # Sound files (optional)
    ├── pets/
    └── ui/
```

## Troubleshooting

### Deployment Fails

**Issue**: GitHub Actions workflow fails

**Solutions**:
1. Check that `AZURE_STATIC_WEB_APPS_API_TOKEN` secret is set correctly
2. Verify the workflow file is in `.github/workflows/`
3. Check Azure Portal for deployment logs
4. Ensure your branch is named `main` (or update workflow)

### 404 Errors on Routes

**Issue**: Getting 404 when navigating to routes

**Solutions**:
1. Verify `staticwebapp.config.json` exists in root
2. Check `navigationFallback` configuration
3. Ensure routes are properly defined
4. Clear browser cache

### Assets Not Loading

**Issue**: CSS, JS, or images not loading

**Solutions**:
1. Check file paths are relative (not absolute)
2. Verify `mimeTypes` in `staticwebapp.config.json`
3. Check browser console for errors
4. Ensure files are committed to repository

### CORS Issues

**Issue**: Cross-origin resource sharing errors

**Solutions**:
1. Check `globalHeaders` in `staticwebapp.config.json`
2. Verify Content Security Policy allows required domains
3. Update CSP to include Testim CDN if needed

## Manual Deployment (Alternative)

If you prefer not to use Git integration:

### Using Azure CLI

```bash
# Install Azure Static Web Apps CLI extension
az extension add --name staticwebapp

# Login
az login

# Deploy
az staticwebapp deploy \
  --name pixelpaw-app \
  --resource-group pixelpaw-rg \
  --app-location "/" \
  --output-location ""
```

### Using SWA CLI

```bash
# Install SWA CLI
npm install -g @azure/static-web-apps-cli

# Login
swa login

# Deploy
swa deploy ./ --deployment-token <your-token>
```

## Monitoring and Analytics

### Application Insights (Optional)

1. Go to your Static Web App in Azure Portal
2. Navigate to **"Application Insights"**
3. Enable Application Insights
4. View analytics and performance metrics

### Logs

View deployment and runtime logs:

1. Go to your Static Web App in Azure Portal
2. Navigate to **"Deployment history"** for deployment logs
3. Navigate to **"Log stream"** for runtime logs

## Cost Estimation

### Free Tier
- **Free**: 100 GB bandwidth/month
- **Free**: 100 builds/month
- **Free**: Custom domains
- **Free**: SSL certificates
- **Free**: Staging environments

### Standard Tier
- **Starting at**: ~$9/month
- **Includes**: Higher limits, custom authentication, private endpoints

For most projects, the Free tier is sufficient.

## Security Best Practices

1. **Content Security Policy**: Already configured in `staticwebapp.config.json`
2. **HTTPS**: Automatically enabled on all Azure Static Web Apps
3. **Custom Domains**: Use HTTPS with automatic certificate management
4. **Environment Variables**: Store sensitive data in Azure Portal configuration

## Updating Your Application

### Automatic Updates (GitHub Actions)

Simply push to your `main` branch:
```bash
git add .
git commit -m "Update application"
git push origin main
```

Deployment happens automatically.

### Manual Updates

Use Azure CLI or SWA CLI to redeploy after making changes.

## Additional Resources

- [Azure Static Web Apps Documentation](https://docs.microsoft.com/azure/static-web-apps/)
- [Azure Static Web Apps CLI](https://github.com/Azure/static-web-apps-cli)
- [Azure Portal](https://portal.azure.com)
- [Azure Pricing Calculator](https://azure.microsoft.com/pricing/calculator/)

## Support

For issues with:
- **Azure Deployment**: Check Azure Portal logs or Azure support
- **Application Issues**: Review browser console and network tabs
- **Configuration**: Verify `staticwebapp.config.json` settings

---

**Last Updated**: Azure deployment configuration ready for Static Web Apps.

