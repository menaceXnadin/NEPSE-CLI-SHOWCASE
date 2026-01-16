# 📈 Nepse CLI - Meroshare IPO Automation & Market Data

[![PyPI version](https://badge.fury.io/py/nepse-cli.svg?cacheSeconds=1)](https://badge.fury.io/py/nepse-cli)
[![Python Version](https://img.shields.io/pypi/pyversions/nepse-cli.svg)](https://pypi.org/project/nepse-cli/)

![Nepse CLI](nepse-cli-image.png)

A modern, interactive command-line tool to automate IPO applications on Meroshare for multiple family members and view real-time NEPSE market data.

**✨ Features:**
- 🤖 Automated IPO application for entire family
- 📊 Real-time market data and indices
- 💼 Portfolio tracking for multiple members
- 🖥️ Beautiful TUI with Rich tables and interactive menus
- 🔍 Fuzzy search and autocompletion
- 🚀 Headless automation (no browser window needed)

## Installation

### 📦 Install from PyPI (Recommended)

**⚠️ Important for Windows Users:** If you installed Python from **Microsoft Store**, please uninstall it and install Python from the [official Python website](https://www.python.org/downloads/) instead. Microsoft Store Python has PATH issues that prevent `nepse` command from working properly.

```bash
pip install nepse-cli
```

**Update to the latest version:**
```bash
pip install --upgrade nepse-cli
```

Then run:
```bash
nepse
```

**⚠️ Windows Users:** If you get `'nepse' is not recognized` error after installation:

**Quick Fix - Use this command instead:**
```bash
python -m nepse_cli
```

**Permanent Fix - Add Python Scripts to PATH:**

**Step 1: Find your Scripts path**
```bash
# Run this command to find where nepse.exe is installed:
python -c "import sys; import os; print(os.path.join(sys.prefix, 'Scripts'))"
```
Copy the output path (e.g., `C:\Users\YourName\AppData\Local\Packages\Python...\Scripts`)

**Step 2: Add to PATH**
- Press `Win + R`, type `sysdm.cpl`, press Enter
- Go to `Advanced` tab → `Environment Variables`
- Under `User variables`, select `Path` → Click `Edit`
- Click `New` → Paste the Scripts path from Step 1
- Click `OK` on all dialogs
- **Restart your terminal**

See more details in [Troubleshooting](#troubleshooting) section below.

---

### 🛠️ Other Installation Options

**Install from Source (For Development):**
```powershell
cd "Nepse CLI"
pip install -e .
```

**🚀 Easy Start (Windows - Source Code):**
If you have the source code folder:
1.  Double-click **`start_nepse.bat`**.
2.  That's it! It will check for Python, install dependencies, and launch the tool.

**Browser Setup:**
The CLI will automatically install Playwright browsers on first run if they're not already installed. If you prefer to install manually:
```powershell
playwright install chromium
```

## Usage

### Interactive Shell (Recommended)
Simply run `nepse` to enter the modern interactive shell:
```powershell
nepse
```
Once inside the shell, you **do not** need to type `nepse` again. Just type the command directly:
*   `stonk NABIL`
*   `ipo`
*   `apply`
*   `mktsum`

**Shell Features:**
*   **Command Palette**: Type `/` to search all available commands.
*   **Autocompletion**: Type commands and see suggestions.
*   **History**: Use Up/Down arrows to cycle through command history.
*   **Help**: Type `help` or `?` to see the command list.

### Direct Commands

#### Meroshare IPO Automation
```powershell
# Apply for IPO (headless by default - no browser window)
nepse apply

# Apply with browser window visible
nepse apply --gui

# Apply for ALL family members (multi-tab automation)
nepse apply-all

# Apply for all members with browser visible
nepse apply-all --gui

# Add or update a family member
nepse add-member

# List all family members
nepse list-members

# Get portfolio (headless by default)
nepse get-portfolio

# Get portfolio with browser window visible
nepse get-portfolio --gui

# Test login (headless by default)
nepse test-login

# Test login with browser window visible
nepse test-login --gui

# View available DP list
nepse dplist
```

#### Market Data Commands
```powershell
# View all open IPOs/FPOs
nepse ipo

# View NEPSE indices
nepse nepse

# View sub-index details (Banking, Hydropower, etc.)
nepse subidx BANKING
nepse subidx HYDROPOWER

# View market summary
nepse mktsum

# View top 10 gainers and losers
nepse topgl

# View stock details (information only - no charts)
nepse stonk NABIL
nepse stonk NICA
```

## Features

### 🖥️ Modern UI & UX
- **Rich TUI**: Beautiful tables, panels, and colored output for all commands.
- **Interactive Menus**: Select family members using arrow keys (no more typing IDs!).
- **Smart Shell**: Autocompletion, fuzzy search, and command history.
- **Progress Bars**: Visual feedback for all long-running operations.

### 🤖 Meroshare Automation
- ✅ **Multi-member Support**: Manage credentials for the whole family.
- ✅ **One-Command Apply**: `nepse apply-all` applies for everyone in sequence.
- ✅ **Interactive Selection**: Choose a specific member from a list using arrow keys.
- ✅ **Headless Mode**: Fast and silent operation by default.
- ✅ **Secure Storage**: Credentials stored locally in your user directory.

### 📈 Market Data
- ✅ **Live Indices**: NEPSE, Sensitive, Float, and Sub-indices.
- ✅ **Market Summary**: Turnover, volume, market cap, and active stocks.
- ✅ **Top Gainers/Losers**: Real-time lists of best and worst performers.
- ✅ **Stock Details**: Price, volume, sector, and changes for any listed company.
- ✅ **IPO Watch**: List of all open and upcoming IPOs/FPOs/Right Shares.

## Configuration

All credential data is stored in a **fixed location** to avoid path issues:

📁 **Data Directory**: `C:\Users\%USERNAME%\Documents\merosharedata\`

Files stored here:
- `family_members.json` - All family member credentials
- `ipo_config.json` - IPO application settings (if any)
- `nepse_cli_history.txt` - Command history for the interactive shell

This means the CLI works from **any directory** - your data is always in the same place!

Family member data structure:

```json
{
  "members": [
    {
      "name": "Dad",
      "dp_value": "139",
      "username": "your_username",
      "password": "your_password",
      "transaction_pin": "1234",
      "applied_kitta": 10,
      "crn_number": "YOUR_CRN"
    }
  ]
}
```

## 👨‍👩‍👧‍👦 Family IPO Management

### Adding Family Members

Add multiple family members to apply for IPOs on their behalf:

```bash
nepse add-member
```

Provide for each member:
- **Name**: e.g., "Dad", "Mom", "Me"
- **DP Value**: Your DP number (e.g., 139)
- **Username**: Meroshare username
- **Password**: Meroshare password
- **Transaction PIN**: 4-digit PIN for submissions
- **Applied Kitta**: Number of shares to apply (e.g., 10, 20)
- **CRN Number**: Customer Reference Number

### Applying for Multiple Members

```bash
# Apply for one member (interactive selection)
nepse apply

# Apply for ALL family members automatically
nepse apply-all

# Apply with browser visible (for debugging)
nepse apply --gui
nepse apply-all --gui
```

### Managing Members

```bash
# List all configured members
nepse list-members

# Update member details
nepse add-member
# (Select existing member to update)

# Test login for a member
nepse test-login

# Get portfolio for a member
nepse get-portfolio
```

## 📊 Quick Reference

### Market Data Commands
```bash
nepse ipo                    # View open IPOs/FPOs
nepse nepse                  # View NEPSE indices
nepse subidx BANKING         # View Banking sector
nepse subidx HYDROPOWER      # View Hydropower sector
nepse mktsum                 # Market summary
nepse topgl                  # Top gainers/losers
nepse stonk NABIL            # Stock details
```

### Available Sub-Indices
`BANKING`, `DEVBANK`, `FINANCE`, `HOTELS AND TOURISM`, `HYDROPOWER`, `INVESTMENT`, `LIFE INSURANCE`, `MANUFACTURING AND PROCESSING`, `MICROFINANCE`, `MUTUAL FUND`, `NONLIFE INSURANCE`, `OTHERS`, `TRADING`

### IPO Automation Commands
```bash
nepse apply                  # Apply for one member
nepse apply-all              # Apply for all members
nepse add-member             # Add/update member
nepse list-members           # List all members
nepse get-portfolio          # Get portfolio
nepse test-login             # Test login
nepse dplist                 # View available DPs
```

## 🔒 Security

- ✅ Credentials stored locally in JSON format
- ✅ File permissions set to 600 on Unix systems
- ✅ Data stored in user's Documents folder
- ⚠️ Never commit `family_members.json` to version control
- ⚠️ Keep credentials file secure and private

## Troubleshooting

**'nepse' is not recognized (Windows):**

If you get `'nepse' is not recognized as an internal or external command` after installation:

**⚠️ Most Common Issue - Microsoft Store Python:**
If you installed Python from Microsoft Store, this is likely your problem. The Microsoft Store version of Python has PATH configuration issues.

**Solution:**
1. Uninstall Python from Microsoft Store (Settings → Apps → Python → Uninstall)
2. Download and install Python from [python.org](https://www.python.org/downloads/)
3. **Important:** Check "Add Python to PATH" during installation
4. Reinstall nepse-cli: `pip install nepse-cli`
5. The `nepse` command should now work without any extra configuration!

**Other Options if you want to keep Microsoft Store Python:**

**Option 1: Use Python module syntax (Quick Fix)**
```bash
python -m nepse_cli
```

**Option 2: Find and run nepse.exe directly**
```bash
# First, find where nepse.exe is installed:
python -c "import sys; import os; print(os.path.join(sys.prefix, 'Scripts', 'nepse.exe'))"

# Then run the output path, for example:
C:\Users\YourUsername\AppData\Local\Packages\PythonSoftwareFoundation.Python.3.13_xxx\LocalCache\local-packages\Python313\Scripts\nepse.exe
```

**Option 3: Add Scripts folder to PATH (Permanent Fix)**

**Step 1 - Find your Scripts path:**
```bash
python -c "import sys; import os; print(os.path.join(sys.prefix, 'Scripts'))"
```
Copy the output path.

**Step 2 - Add to PATH:**
1. Press `Win + R`, type `sysdm.cpl`, press Enter
2. Go to `Advanced` tab → `Environment Variables`
3. Under `User variables`, select `Path` → Click `Edit`
4. Click `New` → Paste the Scripts path from Step 1
5. Click `OK` on all dialogs
6. **Close ALL terminal windows completely** (including VS Code terminal)
7. Open a NEW terminal window
8. Now `nepse` command should work

**Still not working after adding to PATH?**
- Verify the path was added correctly: Run `echo %PATH%` in cmd and check if your Scripts path is there
- Try logging out and back into Windows (or restart your computer)
- Check if nepse.exe exists: Run the command from Step 1 above and verify the file exists at that location
- If file doesn't exist, reinstall: `pip uninstall nepse-cli` then `pip install nepse-cli`
- As a last resort, use `python -m nepse_cli` instead of `nepse`

**Option 4: Reinstall with --user flag**
```bash
pip uninstall nepse-cli
pip install --user nepse-cli
# Then add: %APPDATA%\Python\Python313\Scripts to PATH
```

**Command not found (Linux/Mac):**
- Make sure `~/.local/bin` is in your PATH
- Or install with: `pip install --user nepse-cli`
- Restart your terminal after installation

**Browser not installed:**
```bash
playwright install chromium
# Or use: python -m playwright install chromium
```

**Login fails:**
- Test with: `nepse test-login`
- Verify credentials with: `nepse list-members`
- Update credentials with: `nepse add-member`

