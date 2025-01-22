# Data Mining Module 2: Data Types and Analysis

## Data Fundamentals

### Core Concepts
1. **Data Objects**
   - Entities in applications (persons, cars, patients, items)
   - Represented as records in databases
   
2. **Data Attributes**
   - Data fields representing features/characteristics
   - Example: person object → first name, last name, DOB
   
3. **Attribute Types**
- **Nominal**
  - Values are names/labels
  - Example: 'single', 'married'
- **Ordinal**
  - Values can be sorted
  - Differences not meaningful
  - Example: Likert scale (1-5)
- **Interval**
  - Values have order
  - Differences are meaningful
  - No inherent zero
  - Example: earthquake years
- **Ratio**
  - Similar to interval
  - Has inherent zero
  - Ratios are meaningful
  - Example: document length in bytes

## Statistical Measures

### Measures of Central Tendency
1. **Mean**
   - Average of all values
   - Formula: $\frac{\sum_{i=1}^n x_i}{n}$

2. **Median**
   - Middle value when sorted
   - Average of two middle values if even count

3. **Mode**
   - Most frequent value

4. **Midrange**
   - Average of smallest and largest values
   - Formula: $\frac{min + max}{2}$

### Measures of Dispersion
1. **Range**
   - Difference between largest and smallest values
   - Formula: max - min

2. **Variance** ($σ^2$)
   - Average of squared deviations from mean
   - Formula: $\frac{1}{n}\sum_{i=1}^n(x_i - μ)^2$

3. **Standard Deviation** ($σ$)
   - Square root of variance
   - Formula: $\sqrt{σ^2}$

## Proximity Measures

### Minkowski Distance
- General formula for measuring dissimilarity
- Formula: $distance(i,j) = \sqrt[p]{|x_i^1 - x_j^1|^p + |x_i^2 - x_j^2|^p + ... + |x_i^k - x_j^k|^p}$

Special cases:
1. **Manhattan Distance** (p=1)
   - Sum of absolute differences
   
2. **Euclidean Distance** (p=2)
   - Square root of sum of squared differences
   
3. **Supremum Distance** (p→∞)
   - Maximum difference between components

### Cosine Similarity
- Measures similarity using angle between vectors
- Range: [-1, 1] where 1 means most similar
- Formula: $sim(x,y) = \frac{x \cdot y}{||x|| ||y||}$

## Data Transformation

### Min-max Normalization
- Maps values from one interval to another
- Formula: $v' = \frac{v-a_1}{b_1-a_1}(b_2-a_2) + a_2$
- Used to give attributes equal weight
- Example: Mapping [20,30] → [0,1]

## Connections to Other Notes
- Links to [[Data Mining Introduction]]
- Related to [[Knowledge Discovery Process]]
- Connected to [[Data Preparation]]