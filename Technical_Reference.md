# CONFIRM - Confusion Matrix Framework - Technical Reference
## Developer and Advanced User Guide

### Table of Contents
1. [System Architecture](#system-architecture)
2. [Class Structure](#class-structure)
3. [Data Flow](#data-flow)
4. [Configuration Options](#configuration-options)
5. [API Reference](#api-reference)
6. [Performance Considerations](#performance-considerations)
7. [Error Handling](#error-handling)
8. [Extensibility](#extensibility)

---

## System Architecture

### Overview
The Geophysics Contingency Analysis Tool is built using a modular, object-oriented architecture with the following key components:

- **Main Application**: `GeophysicsAnalyzer` class
- **Visualization Engine**: `VisualizationWindow` class
- **Chart Designer**: `ProfessionalVisualizationDesigner` class
- **Data Management**: Sheet selection and validation systems
- **Processing Engine**: Multi-threaded analysis pipeline

### Technology Stack
- **GUI Framework**: Tkinter (Python's standard GUI library)
- **Data Processing**: NumPy, Pandas, SciPy
- **Visualization**: Matplotlib, Seaborn
- **File I/O**: OpenPyXL for Excel operations
- **Concurrency**: Threading, ThreadPoolExecutor

### System Requirements
```python
# Minimum package versions
numpy >= 1.24.0
pandas >= 2.0.0
scipy >= 1.10.0
matplotlib >= 3.7.0
seaborn >= 0.12.0
openpyxl >= 3.1.0
adjustText >= 1.3.0
```

---

## Class Structure

### Core Classes

#### GeophysicsAnalyzer
**Primary Application Class**

```python
class GeophysicsAnalyzer:
    def __init__(self, root):
        # Main application initialization
        # UI setup and event binding
        # Data management initialization
        # Threading infrastructure setup
```

**Key Methods:**
- `setup_ui()`: Initialize user interface
- `process_data_placeholder()`: Single sheet analysis entry point
- `batch_process_sheets_directly()`: Multi-sheet analysis entry point
- `export_results()`: Export analysis data
- `cleanup_resources()`: Resource cleanup and shutdown

**Data Attributes:**
- `confusion_matrix`: Current analysis results
- `batch_results`: Multi-sheet analysis results
- `comparison_summary`: Cross-sheet comparison data
- `excel_file`: Loaded Excel file reference

#### VisualizationWindow
**External Visualization Interface**

```python
class VisualizationWindow:
    def __init__(self, parent, analyzer):
        # Visualization window initialization
        # Tab-based interface setup
        # Chart generation coordination
```

**Key Methods:**
- `create_window()`: Create main visualization window
- `load_visualizations()`: Load all available visualizations
- `create_multi_sheet_visualizations()`: Multi-sheet charts
- `create_single_sheet_visualizations()`: Single sheet charts
- `export_all_charts()`: Export all visualizations

#### ProfessionalVisualizationDesigner
**Professional Chart Generation**

```python
class ProfessionalVisualizationDesigner:
    def __init__(self):
        # Standardized chart dimensions
        # Professional color palettes
        # Font and styling configurations
        # Performance color mapping
```

**Key Features:**
- Standardized chart dimensions (12.0 x 8.0 inches)
- Professional color schemes
- Consistent typography
- Performance-based color mapping

#### SheetSelectionConfig
**Configuration Management**

```python
class SheetSelectionConfig:
    def __init__(self):
        # Dialog sizing and behavior
        # Preview configuration
        # Auto-selection settings
```

---

## Data Flow

### Single Sheet Analysis Flow

```
1. File Selection → 2. Sheet Selection → 3. Analysis Trigger → 4. Data Processing → 5. Results Display
     ↓                    ↓                    ↓                    ↓                    ↓
Excel File Load    Sheet Validation    Process Data    Statistical Analysis    UI Update
```

**Detailed Flow:**
1. **File Loading**: Excel file loaded via file dialog or drag-and-drop
2. **Sheet Detection**: Available sheets automatically detected and listed
3. **Analysis Trigger**: User clicks "Single Sheet" button
4. **Data Processing**: 
   - Data validation and preprocessing
   - Contingency table creation
   - Chi-square test execution
   - Effect size calculations
5. **Results Generation**: Statistical results and confusion matrix
6. **UI Update**: Results displayed in appropriate panels

### Multi-Sheet Analysis Flow

```
1. File Loading → 2. Sheet Selection → 3. Batch Processing → 4. Individual Analysis → 5. Comparison → 6. Summary
     ↓                ↓                    ↓                    ↓                    ↓                ↓
Multi-Sheet File   Sheet Selection    Process Queue    Parallel Processing    Cross-Sheet Analysis    Results Display
```

**Detailed Flow:**
1. **File Loading**: Multi-sheet Excel file loaded
2. **Sheet Selection**: User selects sheets to analyze
3. **Batch Processing**: Sheets queued for processing
4. **Individual Analysis**: Each sheet processed independently
5. **Comparison Analysis**: Cross-sheet metrics calculated
6. **Summary Generation**: Quality control and ranking
7. **Results Display**: Comprehensive results in QC panel

### Data Processing Pipeline

```
Raw Excel Data → Validation → Preprocessing → Statistical Analysis → Quality Assessment → Results Compilation
     ↓              ↓            ↓                ↓                    ↓                    ↓
Sheet Contents   Data Check   Format Check    Chi-Square Test    QC Metrics    Final Output
```

---

## Configuration Options

### System Configuration Constants

```python
# Security and resource configuration
MAX_MEMORY_MB = 512
MAX_WORKERS = 2
OPERATION_TIMEOUT = 300
MAX_CELLS = 1000000

# Data management configuration
PROJECTS_DIR = Path.home() / "TraceSeis_Projects"
BACKUPS_DIR = PROJECTS_DIR / "Backups"
SETTINGS_FILE = PROJECTS_DIR / "settings.json"
MAX_BACKUPS = 10
```

### UI Configuration

```python
# Window dimensions and behavior
WINDOW_WIDTH = 1500
WINDOW_HEIGHT = 800
MIN_WINDOW_WIDTH = 1200
MIN_WINDOW_HEIGHT = 800

# Panel sizing
ANALYSIS_PANEL_HEIGHT = 500
DATA_PANEL_HEIGHT = 300
```

### Processing Configuration

```python
# Threading configuration
MAX_WORKERS = 2
THREAD_NAME_PREFIX = "GeophysicsWorker"

# Timeout configuration
PROCESSING_TIMEOUT = 300  # seconds
TIMEOUT_WARNING_THRESHOLD = 30  # seconds
CRITICAL_TIMEOUT_THRESHOLD = 120  # seconds
```

---

## API Reference

### Core Analysis Methods

#### Single Sheet Analysis
```python
def process_data_placeholder(self):
    """Process single sheet analysis using unified batch architecture"""
    # Entry point for single sheet analysis
    # Delegates to batch processing core logic
```

#### Multi-Sheet Analysis
```python
def batch_process_sheets_directly(self, selected_sheets):
    """Process sheets without showing selection dialog"""
    # Core multi-sheet processing logic
    # Handles progress monitoring and error handling
```

#### Data Export
```python
def export_results(self):
    """Export analysis results to various formats"""
    # Supports CSV, Excel, and text formats
    # Includes comprehensive metadata
```

### Visualization Methods

#### Chart Generation
```python
def create_confusion_heatmap_in_window(self):
    """Create confusion matrix heatmap visualization"""
    # Generates interactive heatmap
    # Supports normalization options
```

#### Multi-Sheet Visualizations
```python
def create_multi_sheet_side_by_side_view(self):
    """Create multi-sheet side-by-side comparison"""
    # Comparative visualization across sheets
    # Quality-based grouping
```

### Quality Control Methods

#### QC Assessment
```python
def get_chi_square_qc_summary(self, result):
    """Generate quality control summary for analysis result"""
    # Calculates QC grade and metrics
    # Identifies data quality issues
```

#### Quality Grouping
```python
def group_sheets_by_quality(self, batch_results):
    """Group sheets by quality control grades"""
    # High/Medium/Low quality classification
    # Performance-based grouping
```

---

## Performance Considerations

### Memory Management

#### Data Structure Optimization
- **Efficient Data Types**: Use appropriate NumPy data types
- **Memory Monitoring**: Track memory usage during processing
- **Garbage Collection**: Automatic cleanup of temporary objects

#### Batch Processing Optimization
- **Streaming Processing**: Process sheets sequentially to minimize memory
- **Result Aggregation**: Aggregate results efficiently
- **Resource Cleanup**: Immediate cleanup after each sheet

### Processing Optimization

#### Multi-threading Strategy
```python
# Thread pool configuration
self.thread_pool = ThreadPoolExecutor(
    max_workers=MAX_WORKERS, 
    thread_name_prefix="GeophysicsWorker"
)
```

#### Progress Monitoring
- **Real-time Updates**: Progress updates every 200ms
- **Timeout Management**: Automatic timeout detection
- **Resource Monitoring**: CPU and memory usage tracking

### Scalability Considerations

#### Large Dataset Handling
- **Chunked Processing**: Process data in manageable chunks
- **Memory Limits**: Enforce maximum memory usage
- **Progress Feedback**: Provide user feedback for long operations

#### File Size Limitations
- **Maximum Cells**: 1,000,000 cells per sheet
- **Memory Threshold**: 512MB maximum memory usage
- **Processing Timeout**: 300 seconds maximum processing time

---

## Error Handling

### Error Classification

#### Data Errors
- **File Format Errors**: Invalid Excel files
- **Data Structure Errors**: Incompatible data formats
- **Validation Errors**: Data quality issues

#### Processing Errors
- **Memory Errors**: Insufficient memory
- **Timeout Errors**: Processing exceeds time limits
- **Threading Errors**: Concurrency issues

#### System Errors
- **Dependency Errors**: Missing required packages
- **Permission Errors**: File access issues
- **Resource Errors**: System resource limitations

### Error Recovery Strategies

#### Graceful Degradation
```python
try:
    # Primary processing logic
    result = process_data(data)
except Exception as e:
    # Fallback processing
    result = fallback_process(data)
    # Log error for debugging
    log_error(e)
```

#### User Notification
- **Clear Error Messages**: Descriptive error descriptions
- **Recovery Suggestions**: Actionable error resolution steps
- **Progress Indication**: Show current error recovery status

#### Automatic Cleanup
- **Resource Cleanup**: Release system resources
- **State Restoration**: Return to stable application state
- **Error Logging**: Record errors for analysis

### Error Prevention

#### Input Validation
```python
def validate_excel_file(self, file_path):
    """Validate Excel file before processing"""
    # Check file format
    # Verify file accessibility
    # Validate file size
    # Check sheet structure
```

#### Preprocessing Checks
- **Data Type Validation**: Ensure correct data types
- **Range Checking**: Validate numerical ranges
- **Completeness Assessment**: Check for missing data

---

## Extensibility

### Adding New Analysis Types

#### Custom Analysis Method
```python
def custom_analysis_method(self, data):
    """Custom analysis implementation"""
    # Custom processing logic
    # Result formatting
    # Quality assessment
    return results
```

#### Integration Points
- **Analysis Pipeline**: Add to main processing flow
- **Results Display**: Integrate with UI panels
- **Export Support**: Include in export functionality

### Adding New Visualizations

#### Custom Chart Method
```python
def create_custom_chart(self, data):
    """Create custom visualization"""
    # Chart generation logic
    # Styling and formatting
    # Integration with visualization window
```

#### Chart Integration
- **Tab Creation**: Add new visualization tabs
- **Data Binding**: Connect to analysis results
- **Export Support**: Include in chart export

### Configuration Extensions

#### Custom Settings
```python
# Add to configuration constants
CUSTOM_SETTING = "default_value"

# Add to UI configuration
custom_config_frame = ttk.Frame(parent)
custom_setting_var = tk.StringVar(value=CUSTOM_SETTING)
```

#### User Preferences
- **Settings Persistence**: Save user preferences
- **Configuration UI**: User-configurable options
- **Default Values**: Sensible defaults for new features

### Plugin Architecture

#### Plugin Interface
```python
class AnalysisPlugin:
    """Base class for analysis plugins"""
    def process(self, data):
        """Process data and return results"""
        pass
    
    def get_name(self):
        """Return plugin name"""
        pass
    
    def get_description(self):
        """Return plugin description"""
        pass
```

#### Plugin Integration
- **Dynamic Loading**: Load plugins at runtime
- **Configuration Management**: Plugin-specific settings
- **Error Isolation**: Isolate plugin errors from main application

---

## Development Guidelines

### Code Standards

#### Python Conventions
- **PEP 8 Compliance**: Follow Python style guidelines
- **Type Hints**: Use type annotations where appropriate
- **Documentation**: Comprehensive docstrings for all methods

#### Error Handling
- **Exception Specificity**: Catch specific exception types
- **Error Logging**: Log errors with context information
- **User Feedback**: Provide clear error messages

#### Performance
- **Efficient Algorithms**: Use appropriate data structures
- **Memory Management**: Monitor and optimize memory usage
- **Progress Feedback**: Keep users informed of progress

### Testing Considerations

#### Unit Testing
- **Method Testing**: Test individual methods in isolation
- **Mock Objects**: Use mocks for external dependencies
- **Edge Cases**: Test boundary conditions and error cases

#### Integration Testing
- **End-to-End Testing**: Test complete workflows
- **Data Validation**: Verify data processing accuracy
- **UI Testing**: Test user interface functionality

#### Performance Testing
- **Load Testing**: Test with large datasets
- **Memory Testing**: Monitor memory usage patterns
- **Timeout Testing**: Verify timeout handling

### Deployment Considerations

#### Distribution
- **Executable Creation**: PyInstaller for standalone executables
- **Dependency Management**: Ensure all dependencies included
- **Installation Process**: Simple installation for end users

#### Configuration Management
- **Environment Variables**: Support for environment-specific settings
- **Configuration Files**: User-editable configuration
- **Default Values**: Sensible defaults for all settings

---

## Troubleshooting Guide

### Common Development Issues

#### Import Errors
- **Missing Dependencies**: Install required packages
- **Version Conflicts**: Check package version compatibility
- **Path Issues**: Verify Python path configuration

#### Memory Issues
- **Memory Leaks**: Check for circular references
- **Large Datasets**: Implement data chunking
- **Resource Cleanup**: Ensure proper cleanup in error cases

#### Performance Issues
- **Algorithm Complexity**: Optimize processing algorithms
- **I/O Operations**: Minimize file I/O operations
- **Threading Issues**: Monitor thread pool performance

### Debugging Techniques

#### Logging
```python
import logging

# Configure logging
logging.basicConfig(level=logging.DEBUG)
logger = logging.getLogger(__name__)

# Use logging throughout application
logger.debug("Processing data: %s", data_info)
logger.error("Processing failed: %s", error_info)
```

#### Progress Monitoring
- **Progress Bars**: Visual progress indication
- **Status Updates**: Real-time status information
- **Performance Metrics**: Monitor processing performance

#### Error Tracking
- **Stack Traces**: Capture full error information
- **Context Information**: Include relevant data context
- **User Actions**: Track user actions leading to errors

---

*This technical reference is part of the CONFIRM (Confusion Matrix Framework) documentation. For technical support or licensing inquiries, contact TraceSeis, Inc.*
