# CAP4770 - Data Mining: Module 4 
#data-mining #pattern-mining #association-rules

## Frequent Patterns & Association Rules
*Related to [[Data Mining Methods]] and [[Pattern Mining]]*

> [!info] Module Objectives
> This module covers mining frequent patterns and association rules, building on concepts from [[Module 1 - What is Data Mining?]] and [[Module 2 - Data Types and Analysis]]. We will cover:
> - Basic definitions
> - Association rules and their parameters
> - Strong association rules

## Frequent Itemsets
*Connected to [[Knowledge Discovery Process]] and [[Data Fundamentals]]*

### Basic Concepts
- **Itemset**: A subset of items from set I ([[Data Objects]])
- **Transaction**: A specific type of itemset in a dataset ([[Data Types and Analysis]])
- **k-itemset**: An itemset containing k items

### Example Dataset Structure
*Uses concepts from [[Data Types and Analysis]] and [[Statistical Measures]]*
```
Set I = {I₁, I₂, I₃, I₄, I₅, I₆, I₇, I₈, I₉, I₁₀}
```

#### Sample Transaction Dataset
| Transaction ID | Items |
|---------------|-------|
| T₁ | {I₁, I₃, I₆} |
| T₂ | {I₁, I₂} |
| T₃ | {I₅, I₆, I₇, I₉} |
| T₄ | {I₁, I₂, I₆, I₈, I₁₀} |
| T₅ | {I₁, I₆, I₈, I₉} |

### Binary Representation
*Related to [[Data Transformation]]*
Itemsets can be represented as binary sequences:
- T₁ = (1, 0, 1, 0, 0, 1, 0, 0, 0, 0)
- T₄ = (1, 1, 0, 0, 0, 1, 0, 1, 0, 1)

### Frequency Concepts
*Connected to [[Statistical Measures]] and [[Data Mining Methods]]*
- **Occurrence frequency** (support count): Number of transactions containing an itemset
- **Example frequencies**:
  - freq({I₆}) = 4 (present in T₁, T₃, T₄, T₅)
  - freq({I₁, I₂}) = 2 (present in T₂, T₄)
  - freq({I₅, I₇}) = 1 (present in T₃)

> [!important] Frequent Itemset Definition
> An itemset that appears in a dataset with frequency ≥ minimum support count threshold
> *Related to [[Pattern Mining]] and [[Statistical Analysis]]*

### Important Properties
*Connected to [[Data Mining Methods]] and [[Pattern Mining]]*
- All subsets of a frequent itemset are also frequent
- If an itemset is not frequent, none of its supersets can be frequent
- For a k-itemset: number of frequent subsets = 2ᵏ - 1

## Association Rules
*Related to [[Pattern Mining]] and [[Business Intelligence]]*

### Basic Definition
- Form: A ⇒ B, where:
  - A and B are itemsets ([[Data Objects]])
  - A ∩ B = ∅
  - A is the antecedent
  - B is the consequent

### Key Metrics
*Connected to [[Statistical Measures]] and [[Data Analysis]]*

#### 1. Support
- Percentage of transactions containing A ∪ B
- Formula: support(A ⇒ B) = P(A ∪ B)

#### 2. Confidence
- Percentage of transactions containing A that also contain B
- Formula: confidence(A ⇒ B) = P(B|A)

#### 3. Lift
*Related to [[Statistical Analysis]] and [[Proximity Measures]]*
- Measures correlation between A and B
- Formula: lift(A, B) = confidence(A ⇒ B) / support(B)
- Alternative formula: lift(A, B) = P(A ∪ B) / (P(A) × P(B))

> [!note] Lift Interpretation
> - lift > 1: Positive correlation
> - lift < 1: Negative correlation
> - lift = 1: Independent events
> *Connected to [[Statistical Measures]]*

### Strong Association Rules
*Related to [[Pattern Mining]] and [[Data Mining Methods]]*
Rules with both:
- Support ≥ minimum support threshold
- Confidence ≥ minimum confidence threshold

#### Example Analysis (min_support = 40%, min_confidence = 60%)
| Rule | Support | Confidence | Strong? |
|------|---------|------------|---------|
| {I₁, I₆} ⇒ {I₈, I₉} | 20% | 33.3% | No |
| {I₁} ⇒ {I₆, I₈} | 40% | 50% | No |
| {I₆, I₈} ⇒ {I₁} | 40% | 100% | Yes |

### Practical Applications
*Connected to [[Business Intelligence]] and [[Retail]]*
- [[Recommender Systems]]
- [[Business Intelligence|Buying behavior analysis]]
- [[Web Mining]]
- [[Software Bug Analysis]]
- [[Bioinformatics|Biological analysis]]
- [[Market Basket Analysis]]

> [!example] Real World Example
> In a [[Retail]] context:
> - Items could represent products (I₁ = desktop PC, I₂ = keyboard)
> - Transactions represent customer purchases
> - Rules help identify shopping patterns and inform marketing strategies

#association-rules #frequent-patterns #data-analysis #business-intelligence #pattern-mining #statistics