# How to Get Azure Static Web Apps Deployment Token

If you're seeing this error:
```
deployment_token was not provided.
The deployment_token is required for deploying content.
```

This means the `AZURE_STATIC_WEB_APPS_API_TOKEN` secret is missing from your GitHub repository.

## Quick Fix: Get Your Deployment Token

### Method 1: From Azure Portal (Easiest)

1. Go to [Azure Portal](https://portal.azure.com)
2. Navigate to your **Static Web App** resource
3. In the left sidebar, click **"Overview"** or find **"Manage deployment token"**
4. Look for **"Deployment token"** section
5. Click **"Copy"** or **"Show"** to reveal the token
6. Copy the entire token

### Method 2: From Static Web App Settings

1. Go to [Azure Portal](https://portal.azure.com)
2. Navigate to your **Static Web App**
3. Click **"Configuration"** in the left sidebar
4. Look for **"Deployment token"** or **"Deployment credentials"**
5. Copy the token

### Method 3: Using Azure CLI

```bash
# Login to Azure
az login

# Get the deployment token
az staticwebapp secrets list \
  --name <your-app-name> \
  --resource-group <your-resource-group> \
  --query "properties.apiKey" \
  -o tsv
```

## Add Token to GitHub Secrets

1. Go to your GitHub repository
2. Click **Settings** → **Secrets and variables** → **Actions**
3. Click **"New repository secret"**
4. Fill in:
   - **Name**: `AZURE_STATIC_WEB_APPS_API_TOKEN`
   - **Value**: Paste the deployment token you copied
5. Click **"Add secret"**

## Verify the Secret

1. Go to **Settings** → **Secrets and variables** → **Actions**
2. You should see `AZURE_STATIC_WEB_APPS_API_TOKEN` in the list
3. The next workflow run should use this token automatically

## If You Don't Have a Static Web App Yet

If you haven't created the Static Web App yet:

1. Follow the steps in [AZURE_DEPLOYMENT.md](AZURE_DEPLOYMENT.md)
2. When you create the Static Web App via Azure Portal and connect it to GitHub, Azure will **automatically** add the deployment token to your repository secrets
3. No manual steps needed!

## Troubleshooting

### "Token not found in Azure Portal"
- Make sure you're looking at the correct Static Web App resource
- Check that you have the right permissions (Contributor or Owner role)
- Try refreshing the Azure Portal page

### "Secret already exists but deployment fails"
- Delete the old secret and create a new one
- Make sure there are no extra spaces when copying
- Verify the token is from the correct Static Web App

### "Want to skip deployment if token is missing"
You can modify the workflow to skip deployment if the token is missing:

```yaml
skip_deploy_on_missing_secrets: true
```

However, this is not recommended - it's better to add the token so deployments work correctly.

## Security Notes

- ⚠️ **Never commit the deployment token** to your repository
- ✅ **Always use GitHub Secrets** for the token
- ✅ **The token is specific to your Static Web App** - don't share it
- ✅ **Tokens don't expire** but can be regenerated if needed

---

**Need Help?** Check the main [AZURE_DEPLOYMENT.md](AZURE_DEPLOYMENT.md) guide for complete deployment instructions.

