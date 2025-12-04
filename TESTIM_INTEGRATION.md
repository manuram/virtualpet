# Testim Test Automation Integration Guide

## Overview

This project has been integrated with **Testim** test automation platform to enable automated testing, recording, and execution of test cases. Testim provides AI-powered test automation that can record user interactions and create maintainable test suites.

## Integration Details

### Script Integration

Both HTML files (`index.html` and `sprint-kpis-dragons.html`) include the Testim recorder script in their `<head>` sections:

```html
<!-- Testim Test Automation Integration -->
<script src="https://cdn.testim.io/js/testim-recorder.js"></script>
```

**Note**: The primary way to use Testim is through their browser extension. The script tag is optional and can be used for advanced recording capabilities. If you prefer extension-only usage, you can remove this script tag.

The Testim integration enables:
- **Test Recording**: Record user interactions directly in the browser
- **Test Execution**: Run automated tests through Testim's platform
- **AI-Powered Element Detection**: Automatically detect and interact with UI elements

### Test IDs (data-testid Attributes)

To improve test reliability and maintainability, key interactive elements have been tagged with `data-testid` attributes. These provide stable selectors for test automation that won't break when CSS classes or IDs change.

#### PixelPaw Virtual Pet App (index.html)

**Navigation & Settings:**
- `data-testid="pet-name-input"` - Pet name input field
- `data-testid="set-name-button"` - Set name button
- `data-testid="settings-button"` - Settings button
- `data-testid="analytics-button"` - Analytics button
- `data-testid="help-button"` - Help & Tutorial button
- `data-testid="close-settings-button"` - Close settings modal
- `data-testid="close-help-button"` - Close help modal
- `data-testid="close-analytics-button"` - Close analytics modal
- `data-testid="reset-button"` - Reset all progress button

**Pet Interactions:**
- `data-testid="pet-emoji"` - Main pet emoji (clickable)

**Action Buttons:**
- `data-testid="feed-button"` - Feed action
- `data-testid="play-button"` - Play action
- `data-testid="sleep-button"` - Rest/Sleep action
- `data-testid="heal-button"` - Heal action
- `data-testid="bath-button"` - Clean/Bath action
- `data-testid="train-button"` - Train action
- `data-testid="vet-button"` - Vet visit action
- `data-testid="chore-button"` - Chore action
- `data-testid="toy-button"` - Buy toy action
- `data-testid="trick-button"` - Perform trick action

**Tabs:**
- `data-testid="pet-stats-tab"` - Pet Stats tab
- `data-testid="money-savings-tab"` - Money & Savings tab
- `data-testid="activity-badges-tab"` - Activity & Badges tab

#### Sprint KPIs Dashboard (sprint-kpis-dragons.html)

**Navigation:**
- `data-testid="download-pdf-button"` - Download PDF button
- `data-testid="sprint-1-tab"` - Sprint 1 tab
- `data-testid="sprint-2-tab"` - Sprint 2 tab

**Content Sections:**
- `data-testid="sprint-1-content"` - Sprint 1 content area
- `data-testid="sprint-2-content"` - Sprint 2 content area

**Charts:**
- `data-testid="burndown-chart-1"` - Sprint 1 burndown chart
- `data-testid="velocity-chart-1"` - Sprint 1 velocity chart
- `data-testid="category-chart-1"` - Sprint 1 category chart
- `data-testid="burndown-chart-2"` - Sprint 2 burndown chart
- `data-testid="velocity-chart-2"` - Sprint 2 velocity chart
- `data-testid="category-chart-2"` - Sprint 2 category chart
- `data-testid="comparison-chart"` - Sprint comparison chart

## Getting Started with Testim

### 1. Create a Testim Account

1. Visit [https://www.testim.io](https://www.testim.io)
2. Sign up for a free account or log in
3. Create a new project for your application

### 2. Install Testim Browser Extension

1. Install the Testim browser extension from the Chrome Web Store or Firefox Add-ons
2. The extension is the primary method for test recording and execution
3. The extension works with or without the script tag in the HTML

### 3. Record Your First Test

**For PixelPaw App:**
1. Open `index.html` in your browser
2. Click the Testim extension icon
3. Click "Record Test"
4. Perform actions like:
   - Enter a pet name
   - Click action buttons (Feed, Play, etc.)
   - Open settings modal
   - Navigate between tabs
5. Stop recording when done
6. Testim will generate test steps automatically

**For Sprint KPIs Dashboard:**
1. Open `sprint-kpis-dragons.html` in your browser
2. Click the Testim extension icon
3. Click "Record Test"
4. Perform actions like:
   - Switch between sprint tabs
   - Download PDF
   - Verify chart rendering
5. Stop recording when done

### 4. Using Test IDs in Tests

When creating tests, you can use the `data-testid` attributes for more reliable element selection:

**Example Test Steps:**
```
1. Click element with data-testid="settings-button"
2. Wait for modal to appear
3. Click element with data-testid="close-settings-button"
4. Click element with data-testid="feed-button"
5. Verify pet stats updated
```

### 5. Running Tests

1. In Testim dashboard, select your test
2. Click "Run Test"
3. Choose browser and environment
4. View results and screenshots

## Best Practices

### 1. Use Test IDs for Critical Elements

Always use `data-testid` attributes when available for:
- Buttons and interactive elements
- Form inputs
- Navigation elements
- Modal triggers

### 2. Wait for Dynamic Content

For elements that load dynamically (like charts), add wait steps:
- Wait for chart canvas to be visible
- Wait for data to load
- Wait for animations to complete

### 3. Verify State Changes

After actions, verify expected outcomes:
- After feeding: Check hunger stat increased
- After playing: Check happiness stat increased
- After leveling up: Verify level number changed

### 4. Test Different Scenarios

Create test suites for:
- **Happy Path**: Normal user interactions
- **Edge Cases**: Low stats, critical conditions
- **Settings**: Theme changes, sound toggles
- **Navigation**: Tab switching, modal interactions

## Example Test Scenarios

### PixelPaw App Test Scenarios

**Scenario 1: Basic Pet Care**
```
1. Open application
2. Enter pet name: "TestPet"
3. Click "Set Name" button
4. Click "Feed" button
5. Click "Play" button
6. Click "Rest" button
7. Verify all stats are above 50%
```

**Scenario 2: Settings Configuration**
```
1. Click Settings button
2. Change pet type to "Cat"
3. Toggle sound effects
4. Change theme to "Ocean Blue"
5. Close settings
6. Verify changes applied
```

**Scenario 3: Level Progression**
```
1. Click pet multiple times (gain XP)
2. Click "Train" button repeatedly
3. Perform "Trick" (if level 3+)
4. Verify level increased
5. Verify growth stage changed
```

### Sprint KPIs Dashboard Test Scenarios

**Scenario 1: Sprint Navigation**
```
1. Open dashboard
2. Click "Sprint 1" tab
3. Verify Sprint 1 content displayed
4. Click "Sprint 2" tab
5. Verify Sprint 2 content displayed
```

**Scenario 2: PDF Export**
```
1. Click "Download PDF" button
2. Wait for PDF generation
3. Verify download started
```

**Scenario 3: Chart Verification**
```
1. Navigate to Sprint 1
2. Verify burndown chart rendered
3. Verify velocity chart rendered
4. Verify category chart rendered
5. Switch to Sprint 2
6. Verify all charts rendered
```

## CI/CD Integration

Testim can be integrated into your CI/CD pipeline:

### Getting Your Testim Project ID and API Token

To use Testim in CI/CD pipelines, you'll need:
1. **Project ID** - Identifies your Testim project
2. **API Token** - Authenticates API requests

#### Step 1: Get Your Project ID

1. Log in to [Testim Dashboard](https://app.testim.io)
2. Select your project from the project dropdown (top left)
3. Go to **Settings** → **General** (or **Project Settings**)
4. Look for **Project ID** - it will be displayed as a UUID or alphanumeric string
   - Example format: `abc123def456` or `12345678-1234-1234-1234-123456789abc`
5. Copy the Project ID

**Alternative Method:**
- The Project ID is also visible in the URL when viewing your project
- Format: `https://app.testim.io/#/project/<PROJECT_ID>/...`
- The `<PROJECT_ID>` part is what you need

#### Step 2: Get Your API Token

1. In Testim Dashboard, go to **Settings** → **API & Integrations**
2. Navigate to **API Tokens** section
3. Click **"Create Token"** or **"Generate New Token"**
4. Give it a descriptive name (e.g., "CI/CD Pipeline")
5. Set appropriate permissions (typically "Read" and "Execute" for running tests)
6. Click **"Create"** or **"Generate"**
7. **IMPORTANT**: Copy the token immediately - it won't be shown again!
8. Store it securely (you'll add it to GitHub Secrets)

**Note**: If you can't find API Tokens in Settings:
- Some Testim plans may have API access in different locations
- Check **Account Settings** → **API Keys**
- Or contact Testim support for assistance

#### Step 3: Add to GitHub Secrets

1. Go to your GitHub repository
2. Navigate to **Settings** → **Secrets and variables** → **Actions**
3. Click **"New repository secret"**
4. Add two secrets:

   **Secret 1:**
   - Name: `TESTIM_PROJECT_ID`
   - Value: Paste your Project ID
   - Click **"Add secret"**

   **Secret 2:**
   - Name: `TESTIM_API_TOKEN`
   - Value: Paste your API Token
   - Click **"Add secret"**

### Using Testim CLI

1. Install Testim CLI:
```bash
npm install -g @testim/testim-cli
```

2. Authenticate:
```bash
testim login
```

3. Run tests:
```bash
testim run --project <project-id>
```

Or use environment variables:
```bash
export TESTIM_PROJECT_ID="your-project-id"
export TESTIM_API_TOKEN="your-api-token"
testim run --project $TESTIM_PROJECT_ID
```

### GitHub Actions Workflow (Already Configured!)

A GitHub Actions workflow has been created at `.github/workflows/testim-tests.yml` that will automatically:

✅ **Run tests on every push to `main` branch**  
✅ **Run tests on pull requests**  
✅ **Allow manual triggering from GitHub UI**  
✅ **Upload test results as artifacts**  
✅ **Post test results summary in PR comments**

**The workflow is ready to use!** You just need to:

1. **Add GitHub Secrets** (if not already done):
   - Go to your repository → **Settings** → **Secrets and variables** → **Actions**
   - Add `TESTIM_PROJECT_ID` with your Project ID
   - Add `TESTIM_API_TOKEN` with your API Token

2. **Push your code** - Tests will run automatically!

**Workflow Features:**
- Runs on Ubuntu latest
- Uses Node.js 18
- Installs Testim CLI automatically
- Runs tests in parallel (3 concurrent)
- 10-minute timeout per test
- Retries failed tests once
- Uploads results as artifacts (kept for 30 days)
- Posts summary in PR comments
- Shows test status in workflow summary

**To manually trigger tests:**
1. Go to **Actions** tab in GitHub
2. Select **"Run Testim Tests"** workflow
3. Click **"Run workflow"** button
4. Select branch and click **"Run workflow"**

## Troubleshooting

### Tests Failing to Find Elements

**Issue**: Test can't find element with `data-testid`

**Solutions**:
1. Verify element has `data-testid` attribute
2. Check if element is visible (not hidden by CSS)
3. Add wait step before interaction
4. Use Testim's AI locator as fallback

### Dynamic Content Not Loading

**Issue**: Charts or dynamic content not ready when test runs

**Solutions**:
1. Add explicit wait for element visibility
2. Wait for specific text/content to appear
3. Increase wait timeout if needed
4. Check browser console for errors

### Modal Interactions

**Issue**: Can't interact with modal elements

**Solutions**:
1. Wait for modal to fully appear
2. Use `data-testid` for modal buttons
3. Check z-index and overlay issues
4. Try clicking backdrop to close

## Quick Reference: Finding Your Testim Credentials

### Project ID Location
- **Dashboard**: Settings → General → Project ID
- **URL**: `https://app.testim.io/#/project/<PROJECT_ID>/...`
- **CLI**: Run `testim projects list` after logging in

### API Token Location
- **Dashboard**: Settings → API & Integrations → API Tokens
- **Create New**: Click "Create Token" → Name it → Copy immediately
- **Security**: Store in GitHub Secrets, never commit to code

### Environment Variables
```bash
# For local development
export TESTIM_PROJECT_ID="your-project-id-here"
export TESTIM_API_TOKEN="your-api-token-here"

# For GitHub Actions
TESTIM_PROJECT_ID: ${{ secrets.TESTIM_PROJECT_ID }}
TESTIM_API_TOKEN: ${{ secrets.TESTIM_API_TOKEN }}
```

## Additional Resources

- [Testim Documentation](https://help.testim.io/)
- [Testim Best Practices](https://help.testim.io/docs/best-practices)
- [Testim CLI Documentation](https://help.testim.io/docs/testim-cli)
- [Testim CI/CD Integration](https://help.testim.io/docs/integrate-testim-to-your-ci)
- [Testim API Documentation](https://help.testim.io/docs/testim-api)

## Support

For issues with:
- **Testim Platform**: Contact Testim support or check their documentation
- **Application Integration**: Review this guide and check `data-testid` attributes
- **Test Creation**: Use Testim's recording feature and AI suggestions

## Notes

- The Testim script loads from their CDN and requires internet connection
- Test IDs are stable and won't change unless explicitly modified
- All interactive elements are testable through Testim's AI locator even without test IDs
- Test IDs improve test reliability and maintainability

---

**Last Updated**: Integration completed with Testim recorder script and comprehensive test ID coverage.

