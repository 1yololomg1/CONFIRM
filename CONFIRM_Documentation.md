# CONFIRM - Confusion Matrix Framework v1.0

## Overview

CONFIRM (Confusion Matrix Framework) is a proprietary software application developed by TraceSeis, Inc. for professional data analysis. This tool performs contingency analysis on Excel data using Self-Organizing Maps (SOM) and provides comprehensive statistical analysis, quality control assessment, and visualization capabilities.

## Copyright and Licensing

**Copyright (C) 2025 TraceSeis, Inc. All rights reserved.**

This proprietary software is part of the TraceSeis Professional Suite. Unauthorized copying, distribution, or modification is strictly prohibited.

**Licensed under TraceSeis Commercial License Agreement.**

For licensing inquiries, contact: info@traceseis.com

## System Requirements

### Dependencies
The tool requires the following Python packages with minimum versions:

- **numpy**: 1.24.0 or higher
- **pandas**: 2.0.0 or higher  
- **scipy**: 1.10.0 or higher
- **matplotlib**: 3.7.0 or higher
- **seaborn**: 0.12.0 or higher
- **openpyxl**: 3.1.0 or higher
- **adjustText**: 1.3.0 or higher

### System Specifications
- **Operating System**: Windows 10/11
- **Memory**: Minimum 512MB available RAM
- **Display**: Minimum resolution 1200x800 pixels
- **Storage**: Sufficient space for project files and temporary data

## Installation

1. Ensure Python 3.7+ is installed on your system
2. Install required dependencies using pip:
   ```bash
   pip install numpy pandas scipy matplotlib seaborn openpyxl adjustText
   ```
3. Run the application:
   ```bash
   python multisheetcontingencysquares2.py
   ```

## Application Architecture

### Main Classes

#### GeophysicsAnalyzer
The primary application class that manages the main user interface and coordinates all analysis operations for the CONFIRM framework.

**Key Responsibilities:**
- User interface management
- File loading and validation
- Data processing coordination
- Results management and export
- Project management

#### VisualizationWindow
A separate window class for displaying comprehensive visualizations and analysis charts.

**Key Features:**
- Multi-tab visualization interface
- Professional chart generation
- Export capabilities for all charts
- Responsive design with scrollable content

#### ProfessionalVisualizationDesigner
Handles the creation of professional-quality charts and visualizations.

**Features:**
- Standardized chart dimensions and styling
- Professional color palettes
- Consistent font settings and margins
- Performance-based color mapping

#### SheetSelectionConfig
Manages configuration for sheet selection dialogs and data preview.

### Core Functionality

#### Data Input
- **Excel File Support**: Loads and processes Excel files (.xlsx, .xls)
- **Sheet Selection**: Automatic detection and selection of available sheets
- **Drag and Drop**: File input via drag and drop functionality
- **Data Validation**: Comprehensive validation of input data structure

#### Analysis Modes

##### Single Sheet Analysis
- Detailed analysis of individual Excel sheets
- Comprehensive statistical calculations
- Quality control assessment
- Detailed results display

##### Multi-Sheet Analysis
- Batch processing of multiple sheets
- Comparative analysis across sheets
- Quality ranking and grouping
- Summary dashboard generation

#### Statistical Analysis
- **Contingency Analysis**: Chi-square tests and contingency tables
- **Effect Size Calculation**: Cramér's V and other effect size measures
- **Data Completeness Assessment**: Missing data analysis
- **Quality Control Metrics**: Automated QC grading system

#### Visualization Features
- **Confusion Matrix Heatmaps**: Interactive confusion matrix displays
- **Distribution Charts**: Data distribution analysis
- **Performance Comparison**: Multi-sheet performance visualization
- **Radar Charts**: Multi-dimensional performance analysis
- **Pie Charts**: Categorical data breakdown
- **Summary Dashboards**: Comprehensive overview displays

## User Interface

### Main Window Layout

#### Top Section - Data Input
- File selection controls
- Sheet selection dropdown
- Analysis mode selection buttons
- Export and control buttons
- Matrix normalization options

#### Middle Section - Analysis Results
- **Left Panel**: Statistical analysis results (fixed height)
- **Right Panel**: QC Results & Sheet Comparison (expandable)

#### Bottom Section - Data Preview
- Confusion matrix display
- Interactive tree view
- Scrollable data representation

#### Status Bar
- Progress indicators
- Processing status
- Activity monitoring

### Control Buttons

#### Analysis Controls
- **Single Sheet**: Process individual sheet analysis
- **Multi-Sheet Analysis**: Batch process multiple sheets
- **Cancel**: Stop ongoing operations

#### Export Controls
- **Export Results**: Export analysis data to CSV/Excel
- **Export Charts**: Export visualization charts
- **Export Comparison**: Export comparison reports
- **Export QC Report**: Export quality control reports

#### Data Management
- **Save Project**: Save current analysis as project
- **Load Project**: Load previously saved projects
- **Open Viz Window**: Launch visualization window

### Processing Overlay
- Real-time processing status display
- Progress indicators and animations
- Timeout monitoring and warnings
- Cancel operation functionality

## How to Use

### Getting Started

1. **Launch Application**: Run the Python script to start the application
2. **Accept Terms**: Review and accept the software license terms
3. **Load Data**: Use Browse button or drag-and-drop to select Excel file
4. **Select Sheet**: Choose the specific sheet to analyze from dropdown
5. **Choose Analysis Mode**: Select Single Sheet or Multi-Sheet Analysis

### Single Sheet Analysis

1. **Select File and Sheet**: Choose Excel file and specific sheet
2. **Click "Single Sheet"**: Start single sheet analysis
3. **Monitor Progress**: Watch processing overlay for status updates
4. **Review Results**: Examine statistical analysis in left panel
5. **View Confusion Matrix**: Check bottom panel for matrix display
6. **Open Visualizations**: Click "Open Viz Window" for detailed charts

### Multi-Sheet Analysis

1. **Load Excel File**: Select file with multiple sheets
2. **Click "Multi-Sheet Analysis"**: Start batch processing
3. **Sheet Selection**: Choose which sheets to analyze
4. **Batch Processing**: Monitor progress across all selected sheets
5. **Comparison Results**: View QC panel for sheet comparisons
6. **Quality Grouping**: Review high/medium/low quality classifications
7. **Export Results**: Save comprehensive analysis reports

### Data Export

#### Results Export
- **Format Options**: CSV, Excel, or text files
- **Content**: Statistical metrics, QC grades, warnings
- **Location**: User-selected save directory

#### Chart Export
- **Chart Types**: All generated visualizations
- **Formats**: High-resolution image files
- **Batch Export**: Export all charts simultaneously

#### Comparison Export
- **Multi-sheet Summary**: Comparative analysis results
- **Quality Rankings**: Performance across sheets
- **Statistical Comparison**: Detailed metrics comparison

### Project Management

#### Save Project
- **Data Preservation**: Save current analysis state
- **Metadata Storage**: Store analysis parameters and results
- **Backup Creation**: Automatic backup management

#### Load Project
- **State Restoration**: Restore previous analysis state
- **Data Recovery**: Recover analysis results and settings
- **Continuity**: Resume work from previous session

## Quality Control System

### QC Metrics
- **Data Completeness**: Percentage of non-missing values
- **Statistical Validity**: Chi-square test results and p-values
- **Effect Size**: Cramér's V and other effect measures
- **Sample Size**: Adequacy of data for analysis

### QC Grading
- **A Grade**: Excellent data quality (90%+ completeness, valid statistics)
- **B Grade**: Good data quality (75-89% completeness)
- **C Grade**: Fair data quality (60-74% completeness)
- **F Grade**: Poor data quality (<60% completeness or invalid statistics)

### Quality Grouping
- **High Quality**: A and B grade sheets
- **Medium Quality**: C grade sheets
- **Low Quality**: F grade sheets

## Advanced Features

### Matrix Normalization
- **Count Conversion**: Convert raw counts to percentages
- **Row Normalization**: Each row sums to 100%
- **Visual Enhancement**: Improved chart readability

### Batch Processing
- **Parallel Processing**: Multi-threaded analysis execution
- **Progress Monitoring**: Real-time progress tracking
- **Error Handling**: Graceful failure handling for individual sheets
- **Resource Management**: Memory and CPU optimization

### Visualization Window
- **Multi-tab Interface**: Organized chart presentation
- **Interactive Charts**: Zoom, pan, and exploration capabilities
- **Professional Styling**: Publication-ready chart quality
- **Export Options**: High-resolution chart export

## Error Handling

### Common Issues
- **Missing Dependencies**: Automatic dependency checking and reporting
- **File Format Errors**: Validation and error messages for invalid files
- **Memory Limitations**: Automatic resource management and warnings
- **Processing Timeouts**: Progress monitoring and timeout warnings

### Error Recovery
- **Graceful Degradation**: Continue operation when possible
- **User Notifications**: Clear error messages and suggestions
- **Automatic Cleanup**: Resource cleanup on errors
- **State Preservation**: Maintain user data during errors

## Performance Optimization

### Memory Management
- **Efficient Data Structures**: Optimized data handling
- **Resource Monitoring**: Memory usage tracking
- **Automatic Cleanup**: Garbage collection and cleanup
- **Batch Processing**: Memory-efficient multi-sheet analysis

### Processing Optimization
- **Multi-threading**: Parallel processing capabilities
- **Progress Monitoring**: Real-time status updates
- **Timeout Management**: Processing time limits and warnings
- **Resource Allocation**: Optimal CPU and memory usage

## Security Features

### Data Protection
- **No Data Retention**: No user data stored permanently
- **Local Processing**: All analysis performed locally
- **Secure Cleanup**: Secure deletion of temporary files
- **Access Control**: No unauthorized data access

### License Compliance
- **Terms Acceptance**: Required license agreement acceptance
- **Usage Tracking**: Compliance monitoring
- **Access Control**: Licensed user verification

## Support and Contact

### Technical Support
- **Email**: info@traceseis.com
- **Website**: https://www.traceseis.com
- **Documentation**: Comprehensive user guides and tutorials for CONFIRM

### Licensing Inquiries
- **Email**: info@traceseis.com
- **Commercial License**: TraceSeis Commercial License Agreement
- **Terms**: Proprietary software with strict usage terms

## Version Information

- **Current Version**: 1.0.0
- **Release Date**: 2025
- **Compatibility**: Windows 10/11, Python 3.7+
- **License**: TraceSeis Commercial License

## Disclaimer

This software is provided "as is" without warranty of any kind, express or implied. TraceSeis, Inc. shall not be liable for any damages arising from the use of this software.

## Confidentiality Notice

This software contains trade secrets and proprietary information of TraceSeis, Inc. and is protected by copyright and trade secret law. Unauthorized access, use, or distribution is strictly prohibited.
