# Testim Automated Testing Setup

This guide explains how to set up automatic Testim test execution when code is pushed to your repository.

## ✅ Quick Setup (3 Steps)

### Step 1: Get Your Testim Credentials

1. **Get Project ID:**
   - Log in to [Testim Dashboard](https://app.testim.io)
   - Check the URL: `https://app.testim.io/#/project/YOUR_PROJECT_ID/tests`
   - Copy the `YOUR_PROJECT_ID` part

2. **Get API Token:**
   - Go to **Settings** → **API & Integrations** → **API Tokens**
   - Click **"Create Token"**
   - Name it "GitHub Actions CI/CD"
   - Set permissions: "Read" and "Execute"
   - **Copy the token immediately** (you won't see it again!)

### Step 2: Add GitHub Secrets

1. Go to your GitHub repository
2. Click **Settings** → **Secrets and variables** → **Actions**
3. Click **"New repository secret"**
4. Add these two secrets:

   | Secret Name | Value |
   |------------|-------|
   | `TESTIM_PROJECT_ID` | Your Testim Project ID |
   | `TESTIM_API_TOKEN` | Your Testim API Token |

### Step 3: Push Your Code

The workflow is already configured! Just push to `main` branch:

```bash
git add .
git commit -m "Add Testim automation"
git push origin main
```

Tests will run automatically! 🎉

## 📋 What Happens When You Push

1. **GitHub Actions triggers** the workflow
2. **Installs** Testim CLI
3. **Runs** all tests in your Testim project
4. **Uploads** test results as artifacts
5. **Posts** summary in PR comments (if it's a PR)
6. **Shows** status in workflow summary

## 🔍 Viewing Test Results

### In GitHub Actions

1. Go to **Actions** tab in your repository
2. Click on the workflow run
3. Click on **"Run Testim Tests"** job
4. View logs and download artifacts

### Test Artifacts

- Test results are saved as artifacts
- Available for 30 days
- Download from the workflow run page
- Includes XML, JSON, and screenshot files

### PR Comments

If you create a pull request, the workflow will automatically:
- Run tests
- Post a comment with test results
- Show pass/fail status

## ⚙️ Workflow Configuration

The workflow file is located at: `.github/workflows/testim-tests.yml`

### Current Settings

- **Triggers**: Push to `main`, Pull Requests, Manual
- **OS**: Ubuntu Latest
- **Node.js**: Version 18
- **Parallel Tests**: 3 concurrent
- **Timeout**: 10 minutes per test
- **Retries**: 1 retry on failure
- **Artifact Retention**: 30 days

### Customizing the Workflow

You can modify `.github/workflows/testim-tests.yml` to:

**Run specific tests:**
```yaml
testim run \
  --project "$TESTIM_PROJECT_ID" \
  --token "$TESTIM_API_TOKEN" \
  --test "test-id-1" \
  --test "test-id-2"
```

**Run tests on a schedule:**
```yaml
on:
  schedule:
    - cron: '0 2 * * *'  # Daily at 2 AM UTC
```

**Change parallel execution:**
```yaml
--parallel 5  # Run 5 tests concurrently
```

**Increase timeout:**
```yaml
--timeout 1200  # 20 minutes
```

## 🚨 Troubleshooting

### Tests Not Running

**Check:**
1. ✅ Secrets are added correctly
2. ✅ Project ID is correct
3. ✅ API Token has "Execute" permission
4. ✅ Workflow file is in `.github/workflows/`
5. ✅ You're pushing to `main` branch (or PR to `main`)

### "Project ID not found" Error

- Verify Project ID in Testim Dashboard
- Check the URL method: `https://app.testim.io/#/project/YOUR_ID/tests`
- Ensure you're using the correct project

### "API Token invalid" Error

- Create a new token in Testim
- Make sure it has "Execute" permission
- Update the secret in GitHub

### Tests Timing Out

- Increase timeout in workflow: `--timeout 1800` (30 minutes)
- Check if tests are too complex
- Review Testim dashboard for test duration

### No Test Results

- Check if tests exist in your Testim project
- Verify tests are enabled/active
- Check workflow logs for errors

## 📊 Monitoring Test Runs

### GitHub Actions Dashboard

- View all workflow runs
- See pass/fail status
- Download artifacts
- View detailed logs

### Testim Dashboard

- See test execution history
- View detailed test reports
- Analyze test performance
- Debug failed tests

## 🔄 Workflow Triggers

The workflow runs automatically on:

1. **Push to `main`** - Every code push
2. **Pull Requests** - When PR is opened/updated
3. **Manual Trigger** - From Actions tab → "Run workflow"

## 💡 Best Practices

1. **Keep tests fast** - Aim for < 5 minutes total
2. **Use parallel execution** - Run multiple tests simultaneously
3. **Set appropriate timeouts** - Prevent hanging tests
4. **Review failed tests** - Fix flaky tests quickly
5. **Monitor test trends** - Track pass rates over time
6. **Use test tags** - Organize tests by feature/priority

## 📚 Additional Resources

- [Testim CLI Documentation](https://help.testim.io/docs/testim-cli)
- [GitHub Actions Documentation](https://docs.github.com/en/actions)
- [Testim API Reference](https://help.testim.io/docs/testim-api)

---

**Need Help?** Check the main [TESTIM_INTEGRATION.md](TESTIM_INTEGRATION.md) file for more details.

