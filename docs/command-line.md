# Command Line Usage Guide

This document details how to use the GDT tools from the command line for automation and batch processing.

## GDTWhereUsed.exe Command Line Options

```
GDTWhereUsed.exe [options] [search term]
```

### Options:

- `/import:"path"` - Import Navision text files from the specified path
- `/export:"path"` - Export results to the specified path
- `/type:[field|function|variable|table|form]` - Specify search type
- `/format:[txt|csv|excel]` - Export format
- `/silent` - Run without showing UI
- `/help` - Display help information

### Examples:

```powershell
# Import files and perform a search for "Customer No." field
GDTWhereUsed.exe /import:"C:\NavisionExport" /type:field "Customer No."

# Export all usages of the PostSalesDoc function to CSV
GDTWhereUsed.exe /type:function /export:"C:\Results\usage.csv" /format:csv "PostSalesDoc"

# Run in silent mode for automated scripts
GDTWhereUsed.exe /silent /import:"C:\DailyExport" /type:field /export:"C:\Results\daily_report.xlsx" /format:excel "Amount"
```

## GDTAnalyzer.exe Command Line Options

```
GDTAnalyzer.exe [options]
```

### Options:

- `/db:"path"` - Specify database path
- `/analyze:[dependencies|complexity|usage]` - Analysis type
- `/object:"name"` - Object to analyze
- `/export:"path"` - Export results path
- `/silent` - Run without UI

### Examples:

```powershell
# Analyze dependencies for the Sales module
GDTAnalyzer.exe /db:"C:\NavDB" /analyze:dependencies /object:"Sales*" /export:"C:\Results\dependencies.xlsx"
```

## GDTImport.exe Command Line Options

```
GDTImport.exe [options]
```

### Options:

- `/source:"path"` - Source folder with Navision exports
- `/target:"path"` - Target database path
- `/filter:"pattern"` - File filter pattern
- `/overwrite` - Overwrite existing entries
- `/silent` - Run without UI

### Examples:

```powershell
# Import all text files from the source folder
GDTImport.exe /source:"C:\NavExport" /target:"C:\NavDB" /filter:"*.txt" /overwrite /silent
```

## GDTUpdate.exe Command Line Options

```
GDTUpdate.exe [options]
```

### Options:

- `/db:"path"` - Database path to update
- `/source:"path"` - Source for updates
- `/type:[full|incremental]` - Update type
- `/silent` - Run without UI

### Examples:

```powershell
# Perform an incremental update
GDTUpdate.exe /db:"C:\NavDB" /source:"C:\NewExports" /type:incremental /silent
```

## Automation Examples

### PowerShell Script for Daily Analysis:

```powershell
# Daily analysis automation script
$date = Get-Date -Format "yyyy-MM-dd"
$exportPath = "C:\Reports\$date"

# Create export directory
New-Item -ItemType Directory -Path $exportPath -Force

# Import today's exports
& "C:\GDTTools\GDTImport.exe" /source:"C:\DailyExports" /target:"C:\NavDB" /overwrite /silent

# Run analysis for key fields
$fields = @("Amount", "Quantity", "Customer No.", "Item No.")
foreach ($field in $fields) {
    $output = "$exportPath\$($field.Replace(' ', '_')).xlsx"
    & "C:\GDTTools\GDTWhereUsed.exe" /silent /type:field /export:$output /format:excel $field
}

# Generate summary report
& "C:\GDTTools\GDTAnalyzer.exe" /db:"C:\NavDB" /analyze:usage /export:"$exportPath\summary.xlsx" /silent
```

## Exit Codes

All GDT tools use the following exit codes:

- `0` - Success
- `1` - General error
- `2` - Import/Export error
- `3` - File not found
- `4` - Invalid parameters
- `5` - Database error

You can check these in your scripts:

```powershell
& "C:\GDTTools\GDTWhereUsed.exe" /silent /type:field /export:"results.csv" /format:csv "Amount"
if ($LASTEXITCODE -eq 0) {
    Write-Host "Search completed successfully"
} else {
    Write-Host "Error occurred, code: $LASTEXITCODE"
}
```

## Note on Command Line Usage

This documentation assumes command line features are implemented in the GDT tools. If these features are not yet implemented, this document serves as a specification for future development.
