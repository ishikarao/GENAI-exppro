# MLE Parameter Estimation Web Application

## Project Overview
- **Project Name**: MLE Explorer - Interactive Parameter Estimation
- **Type**: Single-page interactive web application
- **Core Functionality**: Demonstrate Maximum Likelihood Estimation for Normal and Exponential distributions with real-time visualization
- **Target Users**: Statistics students, data science beginners, educators

## UI/UX Specification

### Layout Structure
- **Header**: App title with subtle animation
- **Main Content**: Two-column layout on desktop, stacked on mobile
  - Left: Control panel (inputs, buttons)
  - Right: Visualization area (histogram, log-likelihood graph)
- **Results Panel**: Below visualizations showing parameter comparison and metrics
- **Footer**: Educational notes/explanations

### Responsive Breakpoints
- Mobile: < 768px (single column)
- Desktop: >= 768px (two columns)

### Visual Design

#### Color Palette
- **Background**: #0f0f1a (deep navy-black)
- **Card Background**: #1a1a2e (dark purple-navy)
- **Primary Accent**: #00d4ff (cyan)
- **Secondary Accent**: #ff6b6b (coral red)
- **Tertiary Accent**: #4ecdc4 (teal)
- **Success**: #2ecc71 (green)
- **Text Primary**: #ffffff
- **Text Secondary**: #a0a0b0
- **Border**: #2a2a4a

#### Typography
- **Font Family**: 'Outfit' (headings), 'IBM Plex Mono' (numbers/code)
- **Heading Sizes**: H1: 2.5rem, H2: 1.5rem, H3: 1.2rem
- **Body**: 1rem
- **Small/Labels**: 0.85rem

#### Spacing System
- Base unit: 8px
- Card padding: 24px
- Section gaps: 32px
- Input gaps: 16px

#### Visual Effects
- Card shadows: 0 8px 32px rgba(0, 212, 255, 0.1)
- Hover transitions: 0.3s ease
- Input focus: cyan glow border
- Buttons: gradient backgrounds with hover scale

### Components

#### Distribution Selector
- Toggle buttons for Normal/Exponential
- Active state: filled cyan background
- Inactive: outlined

#### Parameter Inputs
- Labeled input fields with units
- Number inputs with step controls
- Real-time validation (red border if invalid)

#### Action Buttons
- "Generate & Estimate" - primary cyan button
- "Reset" - secondary outlined button

#### Histogram Chart
- Canvas-based using Chart.js
- Bars: semi-transparent cyan
- True distribution: coral red line
- Estimated distribution: teal dashed line
- Legend: top-right

#### Log-Likelihood Graph
- Line chart showing log-likelihood vs parameter
- Optimal point: highlighted with marker
- Gradient fill under curve

#### Results Cards
- True vs Estimated parameter comparison
- Error metrics (Bias, MSE)
- Log-likelihood value at optimum

#### Explanation Tooltips
- Small "?" icons next to labels
- Hover reveals educational text

## Functionality Specification

### Core Features

#### 1. Distribution Selection
- Normal Distribution: μ (mean), σ² (variance)
- Exponential Distribution: λ (rate parameter)

#### 2. Parameter Input
- Normal: μ (range: -10 to 10), σ² (range: 0.1 to 10), n (sample size: 10 to 1000)
- Exponential: λ (range: 0.1 to 5), n (sample size: 10 to 1000)

#### 3. Data Generation
- Generate n random samples from selected distribution
- Normal: Box-Muller transform
- Exponential: Inverse transform sampling

#### 4. MLE Estimation
- **Normal MLE**:
  - μ̂ = (1/n) Σxi (sample mean)
  - σ̂² = (1/n) Σ(xi - μ̂)² (biased variance)
- **Exponential MLE**:
  - λ̂ = 1 / (1/n) Σxi (1 / sample mean)

#### 5. Log-Likelihood Computation
- Normal: LL = -n/2 * log(2π) - n/2 * log(σ²) - 1/(2σ²) * Σ(xi-μ)²
- Exponential: LL = n * log(λ) - λ * Σxi

#### 6. Visualization
- Histogram with 20 bins
- Overlaid PDF curves (true and estimated)
- Log-likelihood surface/curve for parameter search

### User Interactions
1. Select distribution type
2. Enter parameters
3. Click "Generate & Estimate"
4. View results and visualizations
5. Hover over elements for explanations
6. Reset to try different values

### Edge Cases
- Invalid parameter inputs: show error, prevent generation
- Very small sample sizes: warn about variance
- Numerical stability in log-likelihood computation

## Acceptance Criteria

### Visual Checkpoints
- [ ] Dark theme with cyan accents renders correctly
- [ ] Two-column layout on desktop, single on mobile
- [ ] Charts render with proper colors and legends
- [ ] Input validation shows visual feedback
- [ ] Hover effects work on all interactive elements

### Functional Checkpoints
- [ ] Normal distribution generates correct samples
- [ ] Exponential distribution generates correct samples
- [ ] MLE estimates match theoretical expectations
- [ ] Log-likelihood curve shows correct optimum
- [ ] Error metrics calculate correctly
- [ ] Reset clears all fields and charts

### Educational Checkpoints
- [ ] Tooltips explain each parameter
- [ ] Results show clear comparison
- [ ] Log-likelihood graph highlights optimum