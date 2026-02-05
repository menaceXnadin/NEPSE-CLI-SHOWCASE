# Nepse CLI - Meroshare IPO Automation & Market Data

[![PyPI version](https://badge.fury.io/py/nepse-cli.svg?cacheSeconds=1)](https://badge.fury.io/py/nepse-cli)
[![Python Version](https://img.shields.io/pypi/pyversions/nepse-cli.svg)](https://pypi.org/project/nepse-cli/)

![Nepse CLI](https://res.cloudinary.com/dzbc5mlm9/image/upload/v1768644603/nepse-cli-image_tcx7tx.png)

A professional command-line tool for NEPSE market analysis and automated Meroshare IPO applications.

> **Note:** This is a showcase repository. The source code is private.

## Installation

Install directly from PyPI:

```bash
pip install nepse-cli
```

Run the tool:

```bash
nepse
```

## Overview

Nepse CLI is a comprehensive command-line tool designed for Nepal Stock Exchange (NEPSE) investors and traders. It combines automated IPO application capabilities with extensive market analysis features.

### Key Features

**IPO Automation**
- Automated application for IPO, FPO, and Rights offerings
- Multi-member family support for batch applications
- Browser-based (Playwright) and API-based (fast) modes
- Headless and GUI operation modes
- Automatic share calculation and validation
- Result checking and status tracking

**Market Analysis**
- Real-time NEPSE indices (Main, Sensitive, Float, Sector-wise)
- Comprehensive stock information and live prices
- Fundamental analysis and company profiles
- Market depth and order book visualization
- Trading signals and price alerts
- Floor sheet with live trade data
- 52-week performance tracking
- Broker rankings and analysis

**Portfolio Management**
- Multi-member portfolio tracking
- Real-time profit/loss calculation with WACC
- Secure local credential storage
- Interactive member management
- Portfolio visualization and reporting

**User Experience**
- Interactive shell with command palette
- Autocompletion and command history
- Modern terminal UI with Rich formatting
- Progress indicators for operations
- Color-coded output and tables

## Requirements

- Python 3.8 or higher
- Windows, Linux, or macOS
- Internet connection
- Meroshare account (for IPO features)

## Available Commands

### Market Data
- `nepse` - Display NEPSE indices
- `subidx <name>` - Show sub-index details
- `mktsum` - Display market summary
- `topgl` - Show top gainers and losers
- `stonk <symbol>` - Show stock details
- `52week` - Stocks at 52-week high/low
- `near52` - Stocks near 52-week high/low
- `floor [--date YYYY-MM-DD] [--buyer ID] [--seller ID] [--page N]` - View floorsheet (live or historical)
- `holidays` - Show market holidays

### Stock Analysis
- `profile <symbol>` - Company profile & info
- `fundamental <symbol>` - Stock fundamentals (EPS, P/E)
- `depth <symbol>` - Market depth (order book)

### Trading Info
- `signals` - Strong buy/sell signals
- `announce` - Market announcements
- `brokers` - List all brokers
- `sectors` - List all sectors

### IPO Management
- `ipo` - List all open IPOs
- `apply [member_name]` - Apply for IPO (use --gui for browser)
- `apply-all` - Apply IPO for all members using browser automation (slower)
- `apply-fast` - ⚡ Fast API-based IPO application (recommended - single member)
- `apply-all-fast` - ⚡ Fast API-based IPO for all members (recommended)
- `result [--all]` - Check IPO allotment results

> **Note:** `apply` and `apply-all` use Playwright browser automation and are slower. For faster applications, use `apply-fast` or `apply-all-fast` which use direct API calls.

### Configuration
- `add` - Add new family member
- `list` - List all family members
- `edit` - Edit existing family member
- `delete` - Delete family member
- `manage` - Member management menu
- `login` - Test login for member
- `portfolio` - Get real-time portfolio with P/L
- `dp-list` - Search and list available DPs

### Interactive Tools
- `help` - Show help information
- `clear` - Clear the screen (cls/clear)
- `exit` - Exit the CLI

## Links

- **PyPI Package:** [https://pypi.org/project/nepse-cli/](https://pypi.org/project/nepse-cli/)
- **Report Issues:** [GitHub Issues](../../issues)

## License

MIT License

## Disclaimer

This tool is for educational and personal use only. Users are responsible for complying with Meroshare's terms of service and applicable regulations. The developers are not liable for any misuse or issues arising from the use of this tool.

## Acknowledgments

- Data sources: NEPSE, ShareSansar, ShareHubNepal
- Built with: Rich, Playwright, Click, Prompt Toolkit
- Community contributions and feedback

---

**Support:** For questions or issues, please open an issue on GitHub
