# Data Warehouses and Knowledge Discovery

## Connection to [[Knowledge Discovery Process]] 
Data warehouses are fundamental to the knowledge discovery process as they:
- Provide unified data views for [[Data Preparation]]
- Support complex [[Data Mining]] operations
- Enable efficient [[Pattern Mining]] and analysis
- Facilitate [[Knowledge Representation]] through integrated data structures

## Key Characteristics of Data Warehouses
- **Subject-oriented**: Organized around major subjects like customers or sales
- **Integrated**: Combines data from multiple [[Data Types and Analysis|data sources]]
- **Time-variant**: Maintains historical data for trend analysis
- **Non-volatile**: Data remains stable once entered

## Types of Data Warehouses

### Enterprise Warehouse
- Centralized repository serving entire organization
- Enables comprehensive [[Business Intelligence]] operations
- Supports cross-departmental analytics
- Integrates with various [[Data Storage Systems]]

### Data Mart
- Focused subset of data warehouse
- Serves specific [[Business Intelligence|business intelligence]] needs
- More agile than full enterprise warehouses
- Common in departmental analytics

## Three-Tier Architecture

### Bottom Tier (Warehouse Database Server)
- Handles [[Data Preparation]] tasks:
  - Data extraction from various sources
  - [[Data Quality Management|Data cleaning]]
  - Data transformation for analysis
- Uses [[Statistical Measures]] for data validation
- Maintains metadata for data tracking

### Middle Tier (OLAP Server)
- Implements [[Multidimensional Data Summarization]]
- Supports various [[Data Mining Methods]]:
  - [[Pattern Mining]]
  - [[Classification]]
  - [[Cluster Analysis]]
- Enables complex analytical calculations

### Top Tier (Front-end Layer)
- Provides [[Data Visualization]] tools
- Supports [[Knowledge Representation]]
- Enables interactive analysis
- Generates business reports

## Data Lakes vs Data Warehouses
### Data Lakes
- Store raw data in native format
- Support all [[Data Types and Analysis|data types]]:
  - [[Data Objects]]
  - Unstructured data
  - Semi-structured data
- More flexible for [[Deep Learning]] applications
- Cost-effective for large-scale storage

## Data Warehouse Modeling

### Multidimensional Data Cube
- Foundation for [[Multidimensional Data Summarization]]
- Components:
  - Dimensions: Based on [[Data Attributes]]
  - Facts: Usually [[Ratio Attributes]] or [[Interval Attributes]]
- Supports multiple analysis levels through cuboids
- Mathematical properties:
  - Number of cuboids = 2^n (n = dimensions)
  - Enables [[Statistical Measures]] across dimensions

### Example Cuboids Using [[Data Objects]]
- Empty set {} (Apex cuboid)
- Single dimension analysis
- Multi-dimensional analysis
- Supports various [[Proximity Measures]] for analysis

## Data Warehouse Schemas

### Star Schema
- Central fact table containing [[Data Attributes|attributes]]
- Dimension tables with [[Nominal Attributes]] and [[Ordinal Attributes]]
- Optimized for [[Multidimensional Data Summarization]]
- Supports efficient [[OLAP Operations]]

### Other Schema Types
- Snowflake schema for normalized dimensions
- Fact constellation for multiple fact tables
- Each supports different [[Data Mining Methods]]

## Concept Hierarchy
- Represents [[Data Objects]] at different abstraction levels
- Similar to [[Classification]] hierarchies
- Enables drill-down and roll-up operations
- Supports [[Pattern Mining]] at various levels

## Online Analytical Processing (OLAP)

### OLAP vs Traditional Processing
- OLAP: Focus on [[Business Intelligence]] and analysis
- OLTP: Focus on transaction processing
- Different [[Data Quality Management]] requirements

### Basic OLAP Operations

#### Roll-up (Drill-up)
- Aggregates using [[Statistical Measures]]
- Moves up concept hierarchies
- Supports [[Data Transformation]]

#### Drill-down
- Increases detail level
- Reveals underlying [[Data Objects]]
- Enables detailed analysis

#### Slice and Dice
- Slice: Selection on single dimension
- Dice: Multi-dimensional selection
- Uses various [[Proximity Measures]]

#### Pivot (Rotate)
- Reorganizes [[Data Visualization]]
- Enables different analytical views
- Supports pattern discovery

#data-mining #data-warehouse #OLAP #business-intelligence #data-analysis

## Related Concepts
- [[Data Preprocessing]]
- [[Statistical Analysis]]
- [[Feature Engineering]]
- [[Data Quality]]
- [[Business Intelligence]] 