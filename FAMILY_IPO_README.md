# 👨‍👩‍👧‍👦 Family IPO Automation - User Guide

## 🎯 Overview
This updated system allows you to manage and apply for IPOs for multiple family members from a single interface!

## 📋 Features
- ✅ **Multi-member support** - Add Dad, Mom, siblings, etc.
- ✅ **Individual credentials** - Each member has their own login details
- ✅ **Separate IPO settings** - Different Kitta amounts and CRN per member
- ✅ **Interactive Selection** - Use arrow keys to choose who to apply for
- ✅ **Portfolio tracking** - Check holdings for each family member
- ✅ **Auto-migration** - Old single-member config automatically converts

## 🚀 Quick Start

### 1️⃣ First Time Setup
Run the program and choose option **2** to add family members:
```bash
nepse add-member
```

### 2️⃣ Add Each Family Member
For each person (Dad, Mom, Brother, etc.), provide:
- **Name**: e.g., "Dad", "Mom", "Me", "Brother"
- **DP Value**: Your DP number (e.g., 139)
- **Username**: Meroshare username
- **Password**: Meroshare password
- **Transaction PIN**: 4-digit PIN for submissions
- **Applied Kitta**: How many shares to apply for (e.g., 10, 20)
- **CRN Number**: Customer Reference Number

### 3️⃣ Apply for IPO
Run the apply command and select which family member to apply for:
```bash
nepse apply
# Use Up/Down arrows to select member and press Enter
```

## 📁 File Structure

### `family_members.json` (Auto-created)
Stores all family member credentials:
```json
{
  "members": [
    {
      "name": "Dad",
      "dp_value": "139",
      "username": "dad_username",
      "password": "dad_password",
      "transaction_pin": "1234",
      "applied_kitta": 10,
      "crn_number": "DAD_CRN_NUMBER"
    },
    ...
  ]
}
```

### `family_members_example.json`
Template file showing the structure for 4 family members.

## 🎮 Menu Options

### **1. Apply for IPO**
- Shows interactive list of all family members
- Select who to apply for using arrow keys
- Automatically fills their details
- Complete automation from login to submission

### **2. Add/Update Family Member**
- Add a new family member
- Update existing member's details
- Each member stores their own IPO settings

### **3. List All Family Members**
- View all configured members
- See their usernames, DP, Kitta, and CRN
- Quick overview of who's set up

### **4. Get Portfolio**
- Select a family member
- Fetch their current holdings
- See all shares they own

### **5. Login (Test)**
- Test login for a specific member
- Verify credentials are working
- Useful for debugging

### **6. View DP List**
- See all available Depository Participants
- Find your DP value

### **7. Exit**
- Close the program

## 🔄 Migration from Old Format

If you have an existing `meroshare_config.json`, the system will:
1. Detect it automatically
2. Ask for a member name (e.g., "Me")
3. Convert it to the new multi-member format
4. Backup the old file as `meroshare_config.json.backup`

## 🔒 Security Notes

- ✅ Keep `family_members.json` secure
- ✅ Set file permissions (auto-set on Linux/Mac)
- ✅ Don't share this file or commit it to Git
- ✅ Each member's password is stored (encrypted storage coming soon)

## 💡 Example Workflow

**Scenario**: Apply for IPO for entire family

```bash
# Step 1: Add all 4 members (one-time setup)
nepse add-member
> Enter details for Dad
> Run again for Mom, Me, Brother

# Step 2: Apply for Dad
nepse apply
> Select: Dad (Use arrow keys)
> Automation runs for Dad

# Step 3: Apply for Mom
nepse apply
> Select: Mom (Use arrow keys)
> Automation runs for Mom

# OR Apply for everyone at once!
nepse apply-all
```

## 🛠️ Troubleshooting

### "No family members found"
- Run `nepse add-member` to add members first

### "CRN number is required"
- Make sure you entered CRN during member setup
- Use `nepse add-member` to update the member

### "Login failed"
- Verify credentials using `nepse test-login`
- Check DP value is correct
- Ensure username/password are valid

## 📞 Support

For issues or questions:
1. Check this README
2. Review the example JSON file
3. Test login for the member having issues

## 🎉 Happy IPO Applying!

Now you can apply for IPOs for your entire family with just a few clicks! 🚀
