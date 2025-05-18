# Quick Start Guide

This guide provides a quick introduction to using the GDT tools for analyzing Navision code.

## Getting Started with GDTWhereUsed

### Step 1: Export Navision Objects
1. Open your Navision development environment
2. Select the objects you want to analyze
3. Export the objects as text files (.txt)
4. Save these files in a folder on your computer

### Step 2: Import Objects into GDTWhereUsed
1. Launch GDTWhereUsed.exe
2. Click on "File" → "Import" or use the Import button
3. Browse to the folder containing your exported Navision text files
4. Select the files and click "Open"
5. Wait for the import process to complete (this may take a few minutes for large codebases)

### Step 3: Search for References
1. In the search field, type the name of a field, function, variable, or other element
2. Select the type of search from the dropdown menu (Field, Function, Variable, etc.)
3. Click "Search" or press Enter
4. View the results in the results pane

### Step 4: Analyzing Results
1. Results are grouped by object type
2. Click on any result to see it in context
3. Use the filter options to narrow down results if needed
4. Export results using "File" → "Export Results" if you need to save them

## Example Use Cases

### Finding All References to a Field
1. Import your object files
2. Enter the field name (e.g., "Customer No.")
3. Set search type to "Field"
4. Click "Search"
5. Review all places where this field is used

### Checking Function Usage
1. Import your object files
2. Enter the function name
3. Set search type to "Function"
4. Click "Search"
5. See all places where this function is called and defined

## Tips for Effective Searching

- Use partial names with wildcards for broader searches
- Use the exact name for precise results
- Try alternative spellings if you don't get expected results
- Use filters to focus on specific object types
- For large codebases, be as specific as possible to improve performance

## Next Steps

For more detailed instructions, please refer to the full [Usage Documentation](./docs/usage.md).
