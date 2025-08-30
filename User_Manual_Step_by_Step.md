# CONFIRM - Confusion Matrix Framework - User Manual
## Step-by-Step Guide

### Table of Contents
1. [Getting Started](#getting-started)
2. [Single Sheet Analysis](#single-sheet-analysis)
3. [Multi-Sheet Analysis](#multi-sheet-analysis)
4. [Understanding Results](#understanding-results)
5. [Exporting Data](#exporting-data)
6. [Project Management](#project-management)
7. [Troubleshooting](#troubleshooting)

---

## Getting Started

### Prerequisites
- Windows 10/11 operating system
- Python 3.7 or higher installed
- Required Python packages installed (see main documentation)

### Launching the Application
1. **Open Command Prompt or PowerShell**
   - Press `Windows + R`, type `cmd`, press Enter
   - Or search for "PowerShell" in Start menu

2. **Navigate to Application Directory**
   ```bash
   cd "C:\Users\[YourUsername]\ZZZZ\YYYY\XXXX\multisheetcontingencysquareSOM.py"
   ```

3. **Run the Application**
   ```bash
   python multisheetcontingencysquares2.py
   ```

### First Launch Setup
1. **License Agreement**
   - Review the TraceSeis Commercial License Agreement
   - Click "I Accept" to proceed
   - Click "I Decline" to exit (application will close)

2. **Application Window**
   - Main window opens with dimensions 1500x800 pixels
   - Window is automatically centered on screen
   - Status bar shows "Ready - Select an Excel file to begin"

---

## Single Sheet Analysis

### Step 1: Load Excel File
1. **Click "Browse" Button**
   - Located in the top section under "Data Input"
   - Opens file selection dialog

2. **Select Excel File**
   - Navigate to your Excel file (.xlsx or .xls format)
   - Click "Open"
   - File path appears in the entry field

3. **Alternative: Drag and Drop**
   - Drag Excel file from File Explorer
   - Drop onto the file entry field
   - File path automatically populates

### Step 2: Select Sheet
1. **Sheet Dropdown Populates**
   - All available sheets in the Excel file appear
   - Select the specific sheet you want to analyze
   - Sheet selection is required before analysis

### Step 3: Configure Options
1. **Matrix Normalization (Optional)**
   - Check "Normalize confusion matrices" if desired
   - Converts counts to percentages (each row sums to 100%)
   - Improves chart readability

### Step 4: Run Analysis
1. **Click "Single Sheet" Button**
   - Located in the analysis buttons row
   - Button text changes to indicate processing

2. **Processing Overlay Appears**
   - Full-screen overlay shows "ANALYSIS IN PROGRESS"
   - Animated spinner and progress messages
   - Progress bar indicates processing status

3. **Monitor Progress**
   - Status updates show current processing stage
   - Timeout warnings appear after 30 seconds
   - Critical timeout warning after 2 minutes

### Step 5: View Results
1. **Statistical Analysis Panel (Left)**
   - Chi-square test results
   - Effect size calculations (Cramér's V)
   - Data completeness percentage
   - Sample size information

2. **Confusion Matrix (Bottom)**
   - Interactive tree view display
   - Raw counts or percentages (based on normalization setting)
   - Scrollable content for large matrices

3. **Status Updates**
   - Status bar shows completion message
   - Progress bar reaches 100%
   - Processing overlay disappears

---

## Multi-Sheet Analysis

### Step 1: Load Multi-Sheet Excel File
1. **Follow Same File Loading Process**
   - Use Browse button or drag and drop
   - Ensure file contains multiple sheets

### Step 2: Launch Multi-Sheet Analysis
1. **Click "Multi-Sheet Analysis" Button**
   - Larger button labeled "Multi-Sheet Analysis"
   - Starts batch processing workflow

### Step 3: Sheet Selection Dialog
1. **Review Available Sheets**
   - All sheets in the file are listed
   - Preview shows first 5 rows of each sheet
   - Sheet information includes row/column counts

2. **Select Sheets to Analyze**
   - Check boxes for sheets you want to analyze
   - Use "Select All" for complete analysis
   - Use "Select Valid Only" to auto-select valid sheets

3. **Confirm Selection**
   - Click "Analyze Selected Sheets"
   - Dialog closes and processing begins

### Step 4: Batch Processing
1. **Processing Overlay Shows Progress**
   - Message: "Starting analysis of X sheet(s)..."
   - Individual sheet progress updates
   - Overall progress from 10% to 80%

2. **Sheet-by-Sheet Processing**
   - Each sheet is processed individually
   - Progress shows current sheet and count
   - Failed sheets are skipped with error logging

3. **Comparison Summary Creation**
   - Progress: "Creating comparison summary..."
   - Multi-sheet analysis results compiled
   - Quality control metrics calculated

### Step 5: Review Batch Results
1. **QC Results Panel (Right)**
   - **Batch Summary**: Overview of all processed sheets
   - **Sheet Details**: Individual sheet quality metrics
   - **Quality Groups**: High/Medium/Low quality classifications

2. **Quality Control Metrics**
   - **Data Completeness**: Percentage of non-missing values
   - **QC Grade**: A, B, C, or F based on quality
   - **Accuracy Score**: Statistical validity measure
   - **Warnings**: Data quality issues identified

3. **Comparison Readiness**
   - **High Quality**: A and B grade sheets
   - **Medium Quality**: C grade sheets
   - **Low Quality**: F grade sheets

---

## Understanding Results

### Statistical Analysis Results
1. **Chi-Square Test**
   - **Chi-Square Value**: Test statistic for independence
   - **P-Value**: Probability of observed results by chance
   - **Degrees of Freedom**: Number of independent variables

2. **Effect Size Measures**
   - **Cramér's V**: Measure of association strength (0-1)
   - **Interpretation**:
     - 0.1: Small effect
     - 0.3: Medium effect
     - 0.5: Large effect

3. **Data Quality Metrics**
   - **Completeness**: Percentage of non-missing data
   - **Sample Size**: Total number of observations
   - **Valid Cases**: Cases with complete data

### Quality Control Grades
1. **Grade A (Excellent)**
   - 90%+ data completeness
   - Valid statistical results
   - No critical warnings

2. **Grade B (Good)**
   - 75-89% data completeness
   - Valid statistical results
   - Minor warnings acceptable

3. **Grade C (Fair)**
   - 60-74% data completeness
   - Valid statistical results
   - Some data quality issues

4. **Grade F (Poor)**
   - <60% data completeness
   - Invalid statistical results
   - Critical data quality issues

### Confusion Matrix Interpretation
1. **Row vs Column Structure**
   - Rows represent actual/predicted values
   - Columns represent predicted/actual values
   - Diagonal shows correct classifications

2. **Count vs Percentage View**
   - Raw counts show absolute numbers
   - Normalized percentages show relative proportions
   - Each row sums to 100% when normalized

---

## Exporting Data

### Export Analysis Results
1. **Click "Export Results" Button**
   - Located in the export controls section
   - Opens file save dialog

2. **Choose Export Format**
   - **CSV**: Comma-separated values
   - **Excel**: .xlsx format with formatting
   - **Text**: Tab-delimited text file

3. **Select Save Location**
   - Navigate to desired directory
   - Enter filename
   - Click "Save"

4. **Export Content Includes**
   - Sheet names and status
   - QC grades and metrics
   - Statistical test results
   - Data completeness information
   - Warnings and error messages

### Export Visualization Charts
1. **Open Visualization Window**
   - Click "Open Viz Window" button
   - Separate window opens with multiple tabs

2. **Navigate Chart Tabs**
   - Summary Dashboard
   - Performance Comparison
   - Individual Sheet Details
   - Radar Analysis
   - Pie Chart Analysis

3. **Export Individual Charts**
   - Right-click on any chart
   - Select export options
   - Choose format and resolution

4. **Export All Charts**
   - Click "Export All Charts" button
   - All visualizations saved simultaneously
   - High-resolution output files

### Export Comparison Reports
1. **Click "Export Comparison" Button**
   - Available after multi-sheet analysis
   - Generates comprehensive comparison report

2. **Report Content**
   - Multi-sheet summary statistics
   - Quality rankings across sheets
   - Performance comparisons
   - Statistical significance testing

### Export QC Report
1. **Click "Export QC Report" Button**
   - Available in QC Results panel
   - Generates detailed quality control report

2. **QC Report Includes**
   - Individual sheet quality metrics
   - Quality grade assignments
   - Data completeness analysis
   - Warning and error summaries

---

## Project Management

### Save Current Project
1. **Click "Save Project" Button**
   - Located in data management section
   - Opens project save dialog

2. **Project Information**
   - **Name**: Descriptive project name
   - **Location**: Directory for project files
   - **Description**: Optional project notes

3. **What Gets Saved**
   - Analysis results and parameters
   - Visualization settings
   - Quality control metrics
   - User preferences and configurations

### Load Previous Project
1. **Click "Load Project" Button**
   - Opens project selection dialog
   - Shows list of saved projects

2. **Select Project**
   - Browse available project files
   - Select desired project
   - Click "Open"

3. **Project Restoration**
   - All analysis results restored
   - Visualization settings applied
   - User interface returns to previous state
   - Data ready for continued analysis

### Project Backup Management
1. **Automatic Backups**
   - Backups created automatically
   - Stored in TraceSeis_Projects/Backups directory
   - Maximum 10 backup files maintained

2. **Backup Locations**
   - **Projects**: `%USERPROFILE%\TraceSeis_Projects`
   - **Backups**: `%USERPROFILE%\TraceSeis_Projects\Backups`
   - **Settings**: `%USERPROFILE%\TraceSeis_Projects\settings.json`

---

## Troubleshooting

### Common Error Messages

#### "No File Selected"
- **Cause**: No Excel file loaded
- **Solution**: Click "Browse" and select an Excel file

#### "No Sheet Selected"
- **Cause**: File loaded but no sheet chosen
- **Solution**: Select a sheet from the dropdown menu

#### "Failed to load file"
- **Cause**: File format not supported or corrupted
- **Solution**: Ensure file is valid Excel format (.xlsx or .xls)

#### "Processing timeout"
- **Cause**: Analysis taking longer than expected
- **Solution**: Wait for completion or cancel and retry with smaller dataset

### Performance Issues

#### Slow Processing
1. **Check File Size**
   - Large files (>1 million cells) may be slow
   - Consider splitting into smaller files

2. **Memory Usage**
   - Close other applications
   - Ensure 512MB+ RAM available
   - Restart application if needed

3. **Sheet Complexity**
   - Many columns/rows increase processing time
   - Complex data structures require more computation

#### Application Freezing
1. **Wait for Processing**
   - Processing overlay indicates active work
   - Don't interrupt during analysis

2. **Use Cancel Button**
   - Click "Cancel" if processing hangs
   - Restart application if necessary

3. **Check System Resources**
   - Monitor CPU and memory usage
   - Close unnecessary applications

### Data Quality Issues

#### Low QC Grades
1. **Check Data Completeness**
   - Look for missing values
   - Ensure consistent data structure
   - Verify column/row alignment

2. **Statistical Validity**
   - Check sample size adequacy
   - Verify data type consistency
   - Look for extreme outliers

3. **Data Structure**
   - Ensure proper contingency table format
   - Check for categorical variables
   - Verify numerical data where expected

### Export Problems

#### Export Fails
1. **Check File Permissions**
   - Ensure write access to target directory
   - Check available disk space

2. **File Format Issues**
   - Try different export formats
   - Check if target file is open in another application

3. **Data Availability**
   - Ensure analysis has completed
   - Check if results are available for export

### Getting Help

#### Technical Support
- **Email**: support@traceseis.com
- **Include**: Error messages, file types, system information

#### Documentation
- **User Manual**: This document
- **Main Documentation**: CONFIRM_Documentation.md
- **Online Resources**: https://www.traceseis.com

#### Application Information
- **Version**: 1.0.0
- **License**: TraceSeis Commercial License
- **Support**: Licensed users only

---

## Quick Reference

### Keyboard Shortcuts
- **Ctrl+O**: Browse for file
- **Ctrl+S**: Save project
- **Ctrl+L**: Load project
- **Escape**: Cancel operations

### Status Indicators
- **Green**: Ready/Complete
- **Orange**: Processing
- **Red**: Error/Failed
- **Gray**: No data

### Progress Messages
- "Analyzing data structure..."
- "Processing SOM neurons..."
- "Calculating statistics..."
- "Generating visualizations..."
- "Creating comparison charts..."
- "Finalizing results..."

### File Formats Supported
- **Input**: .xlsx, .xls
- **Output**: .csv, .xlsx, .txt
- **Charts**: .png, .jpg, .pdf
- **Projects**: .json

### Quality Control Thresholds
- **Grade A**: 90%+ completeness
- **Grade B**: 75-89% completeness  
- **Grade C**: 60-74% completeness
- **Grade F**: <60% completeness

---

*This user manual is part of the CONFIRM (Confusion Matrix Framework) documentation. For technical support or licensing inquiries, contact TraceSeis, Inc.*
