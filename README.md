# GDT Navision Analysis Tools

## Overview
This repository contains a set of executable tools designed to analyze and process Navision (Microsoft Dynamics NAV) text exports. These tools allow users to import TXT files from Navision and find all references and usages of fields, functions, and other elements within the Navision codebase.

## Tools Included

### GDTWhereUsed.exe
This is the main tool that allows you to import TXT files from Navision and find all references and usages of any single field, function, or other elements in your Navision application.

### GDTAnalyzer.exe
Analyzes Navision exports for structural patterns and dependencies.

### GDTImport.exe
Facilitates the import of Navision TXT files into the GDT analysis format.

### GDTUpdate.exe
Updates and maintains the GDT analysis database.

## Installation
The application is provided as standalone executables. No installation is required beyond copying the files to your desired location.

## Usage Instructions

### Using GDTWhereUsed:
1. Export your Navision objects as TXT files
2. Launch GDTWhereUsed.exe
3. Import the TXT files through the interface
4. Search for any field, function, or element
5. Review the results showing all references and usages

### Using Other Tools:
Refer to the [documentation](./docs/usage.md) for detailed instructions on using GDTAnalyzer, GDTImport, and GDTUpdate.

## System Requirements
- Windows operating system
- .NET Framework (version required: specify version)
- Sufficient disk space for analysis of large Navision exports

## License
This software is distributed under the terms of the included LICENSE file.

## Support
For support or questions, please open an issue in this repository or contact (your contact information).

## Contributing
Contributions are welcome! Please feel free to submit a Pull Request.

## Acknowledgements
Developed by GDT IT Consult GmbH
