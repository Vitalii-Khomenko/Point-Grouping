# Geolocation Points Grouping and Export Tool

This web application allows you to import, group, deduplicate, and export geolocation points from multiple text files. It is designed for maximum flexibility and supports a wide variety of point name formats, advanced grouping logic, and user-friendly export options.

## Features

- **Import Multiple Files:**
  - Supports importing any number of `.txt` files at once.
  - Each file is processed independently, and you can add more files at any time.

- **Automatic Grouping:**
  - Points are grouped automatically based on their names using advanced rules:
    - **4-digit numbers** (e.g., `1053`, `8999`): grouped as `1xxx`, `8xxx`, etc.
    - **Names starting with `P` and digits** (e.g., `P91`, `P9123`): grouped as `Pxx`.
    - **Names like `FP.N1.169.2`, `FP.U1.100.1`**: grouped by the first two parts (e.g., `FP.N1`, `FP.U1`).
    - **All other names**: grouped by the first part up to the first dot or dash (e.g., `N1.169.1` → `N1`, `NAME-1234.1` → `NAME`).
  - Handles names of any length, including long alphanumeric names and names with dashes or dots as separators.

- **Per-File Group Selection:**
  - For each imported file, you can select which groups to include in the export.
  - All groups are selected by default, but you can uncheck any group as needed.

- **Deduplication:**
  - Only unique point names are exported, even if they appear in multiple files or groups.

- **Consistent Formatting:**
  - Exported data is aligned in columns for readability.
  - Handles both space and semicolon as coordinate separators.

- **Mobile-Friendly Interface:**
  - The app is fully responsive and works on both desktop and mobile browsers.

- **No Installation Required:**
  - Works entirely in your browser. No server, installation, or plugins needed.

## Supported Point Name Formats
- Names can be any combination of letters, digits, dashes, and dots.
- Examples:
  - `N1.169.1`, `FP.N1.185.1`, `1053`, `P9123`, `ABCDE-12345`, `X1-Y2.3456`, `ABCDEFGHIJ.1234`, `1234567890`, `A1B2C3D4E5`, etc.
- Dashes (`-`) and dots (`.`) are both treated as separators for grouping.

## How to Use
1. Open `group_points.html` in your browser (no server required).
2. Click the **Add files** button and select one or more `.txt` files with your data.
3. For each file, review and select the groups you want to export (all are selected by default).
4. Click **Export selected groups** to download a single file with all selected, deduplicated points.

## Example Input
```
N1.169.1        127205.2918; 6555500.9387; 29.9638
FP.N1.185.1     127164.8080; 6555452.2852; 31.6907
1053           127244.7726; 6555574.3683; 31.3746
P9123          127000.0000; 6555000.0000; 30.0000
ABCDE-12345    127111.1111; 6555111.1111; 31.1111
```

## Grouping Logic Details
- **4-digit numbers:** grouped as `1xxx`, `8xxx`, `9xxx`, etc.
- **P followed by digits:** grouped as `Pxx`.
- **FP.N1.169.2, FP.U1.100.1, etc.:** grouped as `FP.N1`, `FP.U1`, etc.
- **All others:** grouped by the first part up to the first dot or dash.
- Dashes and dots are both treated as separators for grouping.

## Requirements
- Modern web browser (Chrome, Firefox, Edge, Safari).
- No installation or server required.

## License
MIT
