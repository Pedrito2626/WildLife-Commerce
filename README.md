# WildLife-Commerce: Strategic Analysis of International Wildlife Trade (CITES 2000-2021)
This project represents a comprehensive data analysis focused on the international trade of wild fauna species, utilizing a massive dataset from the Convention on International Trade in Endangered Species of Wild Fauna and Flora (CITES) covering the period from 2000 to 2021. The primary objective is to break down global trade patterns, identify key species and regions involved, and provide strategic insights for conservation policy formulation and monitoring.

## 1. Project Overview
Through a rigorous process of cleaning, transformation, and analysis of nearly 3 million transaction records, this study aims to offer a differentiated perspective between the frequency of transactions and the actual volume of specimens traded. Advanced data visualization and statistical analysis techniques are employed to reveal temporal trends, dominant geographical flows, and the trade's impact on the conservation status of various species.

## 2. Methodologies and Key Features
The analysis is structured in several phases, employing the following methodologies and tools:

### Data Preprocessing:

- Efficient loading and management of a DataFrame comprising 2.8 million rows and 19 columns.

- Identification and handling of null values, with a particular focus on the Cantidad (Quantity) column (which lacks specification in 95.5% of records).

- Normalization and standardization of categorical variables (fauna classes, IUCN codes, threat statuses, country names, and subregions) to ensure consistency and facilitate analysis.

- Transformation of the Año (Year) column for clear chronological interpretation.

### Dual Trade Analysis:

- Critical differentiation between frequency analysis (number of trade transactions, including those with unspecified quantities) and volume analysis (actual number of specimens, only for records with Cantidad > 0).

- This dual approach allows for a nuanced understanding of trade, distinguishing between transactional activity and quantitative impact.

### Advanced Exploratory Data Analysis (EDA):

- Temporal: Identification of annual peaks and trends in both trade frequency and volume.

- Geographical: Determination of leading exporter and importer regions, subregions, and countries. Analysis of trade flows between regions.

- Classes and Species: Quantification of the participation of different fauna classes (Reptiles, Birds, Mammals, Amphibians) and the most traded individual species by both criteria (frequency and volume).

- Conservation: Assessment of the distribution of transactions and volumes by threat status (IUCN Red List Categories).

### Executive Visualization:

- Creation of interactive and static dashboards (Plotly Express, Matplotlib, Seaborn) optimized for executive presentations, prioritizing clarity and impact of insights.

- Utilization of professional color palettes and font/dimension configurations for optimal projection.

### Insight Generation and Recommendations:

- Extraction of key findings directly from the analyses, with practical implications for conservation and trade intelligence.

- Formulation of strategic recommendations based on empirical evidence.

## 3. Dataset
The project utilizes the CITES trade database (Vert_CITES_2000_2021.csv), a comprehensive resource on international species trade.
Period: 2000 - 2021

- Initial Dimensions: ~2.8 million records and 19 columns.

- Key Variables: Taxon, Class, IUCN_code, IUCNName, Year, Threat_code, Source_clean, Live, n (Quantity of specimens), Exporter, Importer, Exporter_Country, Importer_Country, Exporter_region, Importer_region, Exporter_subregion, Importer_subregion.

- Critical Consideration: The n (Quantity) column has 95.5% of its values as zero, meaning the quantity was not specified. This highlights the need for a dual analysis and is addressed in the recommendations.

## 4. Key Findings and Insights
The analyses revealed complex and often diverging patterns between the frequency and volume of wildlife trade:

### Overall Temporal Dynamics:

- CITES trade showed a growing trend in the number of transactions between 2000 and 2021, albeit with fluctuations.

- The peak in transactions was observed in 2005, while the peak in volume of specimens traded was in 2000. This divergence is critical, suggesting changes in the nature of trade over time (possibly fewer massive transactions but a higher frequency of smaller-volume trades).

### Geographical Patterns (Export and Import):

- Divergent Leadership: South Africa is positioned as the global leader in export transaction frequency (10.7%), while Indonesia clearly dominates in export specimen volume (20.2 million specimens). This divergence suggests that South Africa handles a large number of small transactions, while Indonesia specializes in large-volume trade of fauna or derived products.

- Dominant Regions: Africa is the most frequent exporting region (32.5% of transactions), while Asia clearly leads in imports (39.9% of transactions) and is also a significant exporting region (14.9%).

- Critical Trade Corridors: Dominant trade flows were identified, highlighting routes such as Europe → Asia (49.2% of Europe's flow), Africa → Europe (39.4% of Africa's flow), and Americas → Europe (37.2% of the Americas' flow).

- Asia's Role: Asia's prominence as the main importing region and a significant exporting region suggests its central role in wildlife trade. This could be attributed to cultural factors (traditional medicine, exotic pets), gastronomic demands, or demand for wildlife-derived products.

- Regional Efficiency: Asia exhibited the highest "trade efficiency" (volume/transaction ratio), indicating that it handles a high volume of specimens per recorded transaction.

### Species and Fauna Classes:

- Reptile Dominance: The Reptilia class is the most traded in both frequency (39.9%) and, overwhelmingly, in volume (81.3%), suggesting a high volume of trade for species such as lizards, snakes, and crocodiles.

- Top Species: Crocodylus niloticus is the species with the most transactions (36,256 transactions), while Varanus salvator is the species with the highest trade volume (9,865,058 specimens). The low overlap (20%) in the top 10 species by frequency and volume underscores that different species are subject to different types of trade (e.g., pets vs. bulk derived products).

- Conservation Implications: Despite the high frequency of trade in "Non-threatened" species, a considerable number of threatened species (545) were identified among those traded, which raises an alert.

## 5. Limitations of the Analysis
The main limitation is the 95.5% of transactions without specified quantities in the dataset. This implies that the frequency analysis provides a view of trade activity, but the actual volume could be significantly underestimated or misrepresented in most cases.

- The granularity of the data may not capture the full complexity of illegal supply chains or diversions of use.

## 6. Strategic Recommendations
Based on the findings, the following recommendations are proposed to strengthen wildlife governance and conservation:

### Improve CITES Data Quality:

- Reporting Incentives: Implement mechanisms to encourage countries to consistently report the quantity of specimens in all transactions.

- Strict Standards: Develop and enforce more rigorous standards for quantity specification in CITES reports.

- Estimation Algorithms: Explore and develop predictive models to estimate missing quantities in historical records, using correlated variables (e.g., Class, Taxon, Origin, Country).

### Targeted Monitoring and Control:

- Early Warning: Establish early warning systems for species in critical threat statuses (Critically Endangered, Endangered) that show any commercial activity.

- Divergent Species Tracking: Prioritize monitoring and research on species like Varanus salvator or Crocodylus niloticus that show a high discrepancy between trade frequency and volume. This could indicate large-scale illegal trade or significant underreporting.

- Real-time Dashboards: Develop interactive dashboards for CITES authorities to visualize and react quickly to anomalous patterns or spikes in key regions and species.

### Regional Trade Intelligence:

- Predictive Analytics: Implement models to forecast future trends in wildlife trade, considering economic, social, and environmental factors that may influence supply and demand.

- Critical Corridors: Strengthen international cooperation and control capabilities in identified trade corridors (e.g., Europe-Asia, Africa-Europe, Americas-Europe), which represent significant flows and points of high concentration.

- Region-Specific Policies: Design CITES compliance policies and programs tailored to the specific characteristics of each region, acknowledging different export and import dynamics (e.g., Africa as a frequency exporter, Asia as a volume importer).
  
## 7. Project Structure
```
├── data/
│   ├── processed/
│   │   └── trafico_fauna_limpio.csv  # Cleaned and processed data
│   └── raw/
│       └── Vert_CITES_2000_2021.csv  # Original raw data
├── notebooks/
│   ├── 01_EDA.ipynb               # Initial Exploratory Data Analysis & Data Cleaning
│   └── 02_Graphics.ipynb          # Advanced Analysis, Visualizations & Dashboard Generation
├── .gitattributes
├── README.md                      # Project README file
└── requirements.txt               # Python dependencies
```
## 8. Technical Stack
Python 3.11.5

### Key Libraries:

- pandas: For data manipulation and analysis.

- numpy: For numerical operations.

- matplotlib: For static data visualization.

- seaborn: For enhanced statistical data visualization.

- plotly.express & plotly.graph_objects: For interactive visualizations and dashboard creation.

- scipy.stats: For statistical tests (e.g., Chi-squared, as seen in the previous project analyzing-data-pandas).

- warnings: For managing warnings during execution.

## 9. How to Run the Project
To set up the environment and run the analysis notebooks, follow these steps:

### 1. Clone the repository:

**Bash**
git clone https://github.com/pedrito2626/wildlife-commerce.git
cd wildlife-commerce

### 2. Create a virtual environment (recommended):

**Bash**
python -m venv venv

### 3. Activate the virtual environment:

- On Windows:

**Bash**
.\venv\Scripts\activate

- On macOS/Linux:

**Bash**
source venv/bin/activate

### 4. Install dependencies:

**Bash**
pip install -r requirements.txt
**Note: Ensure the requirements.txt contains all necessary libraries for this project (e.g., pandas, numpy, matplotlib, seaborn, plotly, scipy).**

### 5. Run the Jupyter notebooks:

**Bash**
jupyter notebook

This command will open the Jupyter interface in your web browser. From there, you can navigate to the notebooks/ directory and open 01_EDA.ipynb and 02_Graphics.ipynb to execute the analysis step-by-step.
