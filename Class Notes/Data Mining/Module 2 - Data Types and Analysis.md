# Data Mining Module 2: Data Types and Analysis

## Data Fundamentals

### Core Concepts

#### 1. Data Objects
- Basic units of analysis in data mining
- Examples:
  - Customers in a retail database
  - Patients in healthcare records
  - Products in inventory systems
  - Students in educational data
- Properties:
  - Unique identifiers
  - Multiple attributes
  - Relationships with other objects

#### 2. Data Attributes
- Characteristics that describe data objects
- Examples:
  - Person: name, age, address, salary
  - Product: ID, price, category, stock level
  - Transaction: date, amount, items, location
- Role in analysis:
  - Feature selection
  - Pattern identification
  - Classification criteria

#### 3. Attribute Types

##### Nominal Attributes
- Categorical values
- No inherent order
- Examples:
  - Colors: red, blue, green
  - Gender: male, female
  - Status: active, inactive
- Operations allowed:
  - Equal to (=)
  - Not equal to (≠)

##### Ordinal Attributes
- Values have meaningful order/ranking
- No meaningful differences between values
- Examples:
  - Sizes: small, medium, large
  - Education: bachelor's, master's, doctorate
  - Satisfaction: low, medium, high
- Operations allowed:
  - Equal to (=)
  - Not equal to (≠)
  - Greater than (>)
  - Less than (<)

##### Interval Attributes
- Numeric values with meaningful differences
- No true zero point
- Examples:
  - Temperature in Celsius/Fahrenheit
  - Calendar years
  - IQ scores
- Operations allowed:
  - All ordinal operations
  - Addition (+)
  - Subtraction (-)

##### Ratio Attributes
- Numeric values with true zero point
- Ratios are meaningful
- Examples:
  - Height, weight
  - Money amounts
  - Time durations
- Operations allowed:
  - All interval operations
  - Multiplication (×)
  - Division (÷)

## Statistical Measures

### Measures of Central Tendency

#### 1. Mean (Average)
- Formula: $\frac{\sum_{i=1}^n x_i}{n}$
- Properties:
  - Sensitive to outliers
  - Uses all data points
  - Best for symmetric distributions
- Use cases:
  - Income analysis
  - Performance metrics
  - Quality control

#### 2. Median
- Middle value when data is sorted
- Properties:
  - Resistant to outliers
  - Splits data into two equal parts
  - Good for skewed distributions
- Special cases:
  - Even number of values: average of two middle values
  - Odd number of values: middle value

#### 3. Mode
- Most frequent value
- Properties:
  - Can have multiple modes
  - Works with nominal data
  - Good for categorical data
- Use cases:
  - Customer preferences
  - Product popularity
  - Common categories

#### 4. Midrange
- Formula: $\frac{min + max}{2}$
- Properties:
  - Simple to calculate
  - Very sensitive to outliers
  - Limited statistical use

### Measures of Dispersion

#### 1. Range
- Formula: max - min
- Properties:
  - Simple to calculate
  - Very sensitive to outliers
  - Gives spread of data

#### 2. Variance ($σ^2$)
- Formula: $\frac{1}{n}\sum_{i=1}^n(x_i - μ)^2$
- Properties:
  - Measures spread around mean
  - Always non-negative
  - Units are squared

#### 3. Standard Deviation ($σ$)
- Formula: $\sqrt{σ^2}$
- Properties:
  - Same units as original data
  - Most common measure of spread
  - Used in normal distribution

## Proximity Measures

### Minkowski Distance
- General formula: $distance(i,j) = \sqrt[p]{|x_i^1 - x_j^1|^p + |x_i^2 - x_j^2|^p + ... + |x_i^k - x_j^k|^p}$
- Applications:
  - Pattern recognition
  - Cluster analysis
  - Similarity search

#### Special Cases:
1. **Manhattan Distance (p=1)**
   - Sum of absolute differences
   - Good for grid-like patterns
   - Less sensitive to outliers

2. **Euclidean Distance (p=2)**
   - Straight-line distance
   - Most common distance measure
   - Good for continuous data

3. **Supremum Distance (p→∞)**
   - Maximum component difference
   - Used in special applications
   - Computationally efficient

### Cosine Similarity
- Formula: $sim(x,y) = \frac{x \cdot y}{||x|| ||y||}$
- Properties:
  - Range: [-1, 1]
  - 1: perfectly similar
  - 0: orthogonal
  - -1: opposite
- Applications:
  - Text mining
  - Document classification
  - Recommendation systems

## Data Transformation

### Min-max Normalization
- Formula: $v' = \frac{v-a_1}{b_1-a_1}(b_2-a_2) + a_2$
- Purpose:
  - Scale data to specific range
  - Make attributes comparable
  - Prepare for algorithms
- Applications:
  - Neural networks
  - Distance calculations
  - Feature scaling

### Best Practices
- Choose appropriate normalization method
- Consider data distribution
- Handle outliers appropriately
- Validate results

## Links to Other Topics
- [[Data Preprocessing]]
- [[Statistical Analysis]]
- [[Feature Engineering]]
- [[Distance Metrics]]
- [[Data Quality]]