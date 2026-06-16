# Bitwarden Backup Code Converter 🔐

Convert your Bitwarden JSON exports into clean **PDF tables** and **Canva-ready CSV** files with numbered backup codes (1-10).

![Screenshot](screenshot.png) <!-- Add a screenshot later -->

## ✨ Features

- **📄 PDF Export** - Clean table format with auto-sizing columns, perfect for printing
- **📊 CSV Export** - Canva-ready format with multi-line backup codes in each cell
- **🔐 Backup Code Detection** - Detects ALL formats: spaced numbers (3126 6674), hyphenated (AAAA-1111), plain numbers, alphanumeric
- **📁 Folder Mapping** - Correctly maps folderId to folder name from the JSON's folders array
- **📋 Sorted Output** - Entries sorted alphabetically by folder name
- **🧹 Clean Text** - Automatically removes emojis and strange characters
- **🖨️ Print-Ready PDF** - Compact layout with page numbers and total code count

## 📥 How to Use

### 1. Export from Bitwarden
1. Open Bitwarden
2. Go to **Settings** → **Export Vault**
3. Choose **JSON** format
4. Save the file

### 2. Use the Converter
1. Open the HTML file in your browser
2. Drag & drop or click to upload your JSON file
3. Click **"Convert JSON"**
4. Preview your data
5. Download as **PDF** (print-ready table) or **CSV** (for Canva/Sheets)

### 3. Import to Canva (for CSV)
1. Download the CSV file
2. Open Canva → Add a **Table** element
3. Click **"Import data"** (top right of the table)
4. Upload your CSV file
5. Enable **"Wrap Text"** to see each backup code on its own line

## 📊 CSV Format

| Column | Description |
|--------|-------------|
| Folder | The folder name from Bitwarden |
| Username | The login username |
| Password | The account password |
| Backup Codes | All codes numbered 1-10, each on a new line |

## 📄 PDF Format

- Clean table with 4 columns
- Auto-sizing columns for long text (email addresses, etc.)
- Each account on its own row
- Backup codes listed vertically
- Page numbers and total code count

## 🛠️ Technical Details

- **Pure HTML/CSS/JavaScript** - No server required, runs entirely in your browser
- **No data uploads** - Your data stays local, never leaves your computer
- **jsPDF** - Used for PDF generation
- **jspdf-autotable** - For clean table formatting

## 📂 Example Input

```json
{
  "folders": [
    { "id": "folder1", "name": "Gaming" },
    { "id": "folder2", "name": "Social" }
  ],
  "items": [
    {
      "type": 1,
      "folderId": "folder1",
      "login": { "username": "ali7", "password": "12345" },
      "notes": "1. 3126 6674\n2. 8151 5915"
    }
```
## 📂 Example CSV Output:

Folder,Username,Password,Backup Codes
Gaming,ali7,12345,"1. 3126 6674
2. 8151 5915"
Social,alice123,TwitterPass456,"1. AAAA-1111-BBBB-2222
2. CCCC-3333-DDDD-4444"
  ]
}
