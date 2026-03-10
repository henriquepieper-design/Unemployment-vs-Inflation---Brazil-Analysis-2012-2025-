# Unemployment vs Inflation - Brazil Analysis (2012-2025)
Analysis of the relationship between unemployment rate and inflation (IPCA) in Brazil, investigating the validity of the Phillips Curve in the recent Brazilian economic context.

## Objective
To investigate whether there is a correlation between unemployment and inflation in Brazil from 2012 to 2025, empirically testing the Phillips Curve - an economic theory that suggests an inverse relationship between these variables.
Initial hypothesis: The higher the unemployment, the lower the inflation (negative correlation).

## Data Source

### 1. Unemployment Rate

- **Source**: IBGE/SIDRA (Brazilian Institute of Geography and Statistics)
- **Table**: 6468 - PNAD Contínua (Continuous National Household Sample Survey)
- **Variable**: Unemployment rate in the reference week (%)
- **Frequency**: Quarterly
- **Period**: 1st quarter 2012 to 3rd quarter 2025
- **Link**: [SIDRA - Table 6468](https://sidra.ibge.gov.br/tabela/6468)

### 2. Inflation (IPCA)

- **Source**: Central Bank of Brazil
- **Series**: 433 - IPCA (Consumer Price Index - monthly variation)
- **System**: SGS - Time Series Management System
- **Frequency**: Monthly (aggregated to quarterly)
- **Period**: January 2012 to December 2025
- **API**: [BCB - Time Series](https://api.bcb.gov.br/)

## Methodology

### 1. Data Collection

- **Unemployment**: Import via SIDRA API (IBGE)
- **IPCA**: Import via Central Bank API
- Both collected programmatically using Python

### 2. Data Processing

- Data cleaning and formatting
- Conversion of monthly IPCA to quarterly average (compatibility with unemployment data)
- Merge of datasets by 'Quarter' column

### 3. Analysis

- Descriptive statistics
- **Pearson correlation** calculation
- Visualizations:
   - Time series (unemployment and IPCA)
   - Scatter plot (relationship between variables)

## Results

### Chart 1: Unemployment Over Time

![Unemployment](charts/taxa_desemprego.png)

**Key observations:**

- 2012-2014: Low and stable unemployment (~7%)
- 2015-2017: Spike to ~14% (economic crisis)
- 2020-2021: Peak of ~15% (COVID-19 pandemic)
- 2022-2025: Gradual recovery (~6-7%)

### Chart 2: IPCA Over Time

![Inflation](charts/ipca.png)

**Key observations:**

- Highly volatile IPCA throughout the period
- 2015: Inflation peak (~1.25% quarterly)
- 2020: Deflation (-0.15%) - pandemic effects
- 2022: Largest deflation of the period (-0.43%)
- 2021-2022: High inflation (post-pandemic)

### Chart 3:  Relationship Between Unemployment and IPCA

![Unemployment_vs_inflation](charts/desemprego_vs_inflacao.png)

**Pearson Correlation: -0.03**

**Interpretation:**

- Virtually null correlation (very close to zero)
- Points scattered without clear pattern
- Unemployment DOES NOT predict inflation (and vice versa)

## Key Findings

### 1 - Phillips Curve **DOES NOT** hold in recent Brazil
The analysis revealed a correlation of -0.03, indicating the absence of a linear relationship between unemployment and inflation in the analyzed period.

### 2 - Brazilian inflation has more complex causes
The lack of correlation suggests that inflation in Brazil is primarily determined by other factors:
- **Exchange rate (dollar):** Exchange rate variations impact import prices
- **Commodities:** Oil, food, energy prices
- **Monetary policy:** Selic rate and Central Bank decisions
- **Expectations:** Inertial inflation and price indexation
- **External shocks:** Pandemic, international conflicts

### 3 - Stagflation periods
Moments were identified where unemployment and inflation rose together, contradicting classical theory:

- **2015-2016:** Recession with high inflation
- **2021:** Slow recovery with elevated inflation

### 4 - High IPCA volatility
Brazilian inflation shows much larger oscillations than unemployment, indicating sensitivity to short-term shocks.

## Final Considerations
### Conclusions
This study demonstrates that, in the Brazilian context between 2012 and 2025, the classical Phillips Curve does not consistently apply. The nearly null correlation between unemployment and inflation indicates that:

- 1. Unemployment is not a good predictor of inflation in Brazil
- 2. External factors dominate Brazilian inflationary dynamics
- 3. Emerging economies like Brazil may exhibit different behaviors from developed economies

### Implications
**For economic policymakers, this suggests that:**

- Reducing unemployment does not necessarily generate inflationary pressure
- Inflation control requires attention to exchange rates, commodities, and expectations
- Employment and inflation policies can be treated more independently

### Limitations

- Analysis limited to the 2012-2025 period
- Quarterly data may hide short-term relationships
- Temporal lags were not considered
- Correlation analysis does not imply causation


### Technologies Used

- **Python** 3.13.9
- **Pandas** - Data manipulation and analysis
- **Matplotlib** - Visualizations
- **Requests** - API consumption
- **Jupyter Notebook** - Development environment

## How to Reproduce
1. **Clone the repository**
'''bash
git clone https://github.com/your-username/unemployment-vs-inflation.git
cd unemployment-vs-inflation
'''
2. **Install dependencies**
'''bash
pip install -r requirements.txt
'''
3. **Run the notebook**
'''bash
jupyter notebook analysis.ipynb
'''

## References

## References

- IBGE - [PNAD Contínua](https://www.ibge.gov.br/estatisticas/sociais/trabalho/9173-pesquisa-nacional-por-amostra-de-domicilios-continua-trimestral.html)
- Central Bank of Brazil - [SGS - Time Series Management System](https://www3.bcb.gov.br/sgspub/)
- Phillips, A. W. (1958). "The Relation Between Unemployment and the Rate of Change of Money Wage Rates in the United Kingdom, 1861–1957"
- Blanchard, O. (2017). "Macroeconomics" (7th ed.)


## Author
Henrique Rosso Pieper

- Email: henriquepieper@gmail.com

**If this project was useful to you, consider giving it a star!**