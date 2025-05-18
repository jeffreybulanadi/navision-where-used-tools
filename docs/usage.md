# GDT Tools Usage Documentation

## GDTWhereUsed.exe

GDTWhereUsed is the primary tool for analyzing Navision object references.

### Basic Usage:

1. **Launch the Application:**
   - Double-click on GDTWhereUsed.exe to start the application

2. **Import Navision Text Files:**
   - Click "Import" or use the File menu to import Navision text exports
   - Select the folder containing your .TXT files
   - The tool will process and index all objects found in these files

3. **Perform a Search:**
   - Use the search field to enter a field name, function name, or other element
   - Select the appropriate search type from the dropdown menu
   - Click "Search" to find all references

4. **View Results:**
   - The results panel will display all occurrences of the searched element
   - Results are organized by object type (Table, Form, Report, etc.)
   - Double-click on any result to see the context

5. **Export Results:**
   - Use the Export button to save search results as a text or Excel file

### Advanced Features:

- **Filtering:** Narrow down search results by object type, module, or other criteria
- **Regular Expressions:** Use regex patterns for complex searches
- **Batch Processing:** Analyze multiple elements at once using the batch mode

## GDTAnalyzer.exe

GDTAnalyzer performs deeper analysis on Navision objects.

### Basic Usage:

1. Launch GDTAnalyzer.exe
2. Import Navision objects (either directly or use previously imported data)
3. Select analysis type (dependency mapping, complexity analysis, etc.)
4. View and export analysis results

## GDTImport.exe

GDTImport is a dedicated tool for importing Navision exports into the GDT format.

### Basic Usage:

1. Launch GDTImport.exe
2. Select source folder containing Navision export files
3. Configure import options
4. Start import process
5. Verify import completion

## GDTUpdate.exe

GDTUpdate maintains and updates the GDT analysis database.

### Basic Usage:

1. Launch GDTUpdate.exe
2. Select the database to update
3. Choose update options
4. Apply updates

## Tips and Troubleshooting

### Common Issues:

1. **Import Errors:**
   - Ensure Navision exports are in standard text format
   - Check for file access permissions
   - Try importing files in smaller batches

2. **Search Performance:**
   - Large codebases may require more time for indexing
   - Consider using more specific search terms
   - Use filters to narrow down search scope

3. **Application Errors:**
   - Ensure your .NET Framework is up-to-date
   - Check for sufficient disk space
   - Close and restart the application if it becomes unresponsive

### Best Practices:

1. Organize Navision exports by module or functionality
2. Regularly update your analysis database
3. Export important search results for documentation
4. Use batch operations for repetitive tasks
