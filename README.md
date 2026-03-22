# zootopia-gender-discourse-analysis
A quantitative discourse analysis of Zootopia characters through a gender lens. Utilizing R (sentimentr, AFINN, Mixed-effects models) to examine Type-Token Ratio (TTR) and sentiment scores. Findings suggest gender de-differentiation in modern animation, supporting values of gender equality.

## Project Overview

This repository contains a comprehensive digital humanities analysis of gender representation in the animated film *Zootopia*. Using quantitative text analysis and sentiment analysis techniques, we examine discourse features of male and female characters to investigate whether the film reflects gender equality values through its narrative texts.

## Research Questions

1. Are there significant differences in linguistic complexity (measured by Type-Token Ratio) between male and female characters in *Zootopia*?
2. Are there significant differences in sentiment scores between male and female characters in *Zootopia*?

## Key Findings

- **Linguistic Complexity (TTR)**: No significant difference in Type-Token Ratio between male and female characters, indicating comparable vocabulary diversity.
- **Sentiment Analysis (Word-level)**: No statistically significant difference in word-level sentiment scores between genders.
- **Sentiment Analysis (Sentence-level)**: A marginally significant difference (p = 0.030) was found, with female characters exhibiting slightly more positive sentiment than male characters.
- **Overall Conclusion**: Character-specific individual differences are far more influential than gender factors in shaping discourse features.

## Methodology

### Data Collection & Preparation
- Extracted 888 subtitle entries from 49 characters via web scraping from the Zootopia Fandom Wiki
- Collected character metadata (gender, species, alignment, dietary type) from the same source
- Applied comprehensive data cleaning including removal of contextual markers and standardization

### Analysis Framework
**Phase 1: Lexical Complexity Analysis**
- Calculated Type-Token Ratio (TTR) as a measure of vocabulary diversity
- Performed t-tests and mixed-effects models to examine gender differences
- Controlled for character-level variation using random intercepts

**Phase 2: Sentiment Analysis**
- **Word-level**: Used the AFINN-111 dictionary for lexicon-based sentiment scoring
- **Sentence-level**: Applied the `sentimentr` package for context-aware sentiment measurement
- Compared sentiment distributions between genders using both parametric and non-parametric tests

**Phase 3: Statistical Modeling**
- Mixed-effects models (LMM) to account for nested data structure (utterances within characters)
- Wilcoxon tests for non-normal data distributions
- Effect size calculations (Cohen's d, Cliff's delta) for practical significance assessment

### Extended Analysis
- Case study comparison of protagonists Judy Hopps vs. Nick Wilde
- TF-IDF analysis to identify distinctive vocabulary per character
- NRC emotion lexicon analysis to classify text into 8 emotion categories

## Repository Structure

```
├── Main_Document.qmd           # Complete analysis with embedded R code and visualizations
├── Main_Document.html          # Compiled HTML report
├── Used_Package.md             # Complete list of R packages with descriptions
├── README.md                   # Project documentation
├── data/
│   ├── Character_info.csv          # Character metadata (gender, species, alignment, diet)
│   ├── Zootopia_Transcript_checked.csv    # Cleaned subtitle data
│   ├── Zootopia_Transcript_processed.csv  # Raw extracted subtitles
│   └── [Additional HTML source files]
├── dictionary/
│   ├── AFINN/                  # AFINN sentiment dictionary
│   │   ├── AFINN-111.txt
│   │   └── AFINN-README.txt
│   ├── NRC/                    # NRC emotion dictionary
│   └── added_stop_words.txt    # Custom stop words list
└── student_photo/              # Student identification photos

```

## Technical Stack

### R Packages (18 total)

**Data Processing**: `dplyr`, `stringr`, `tidytext`

**HTML Processing**: `xml2`, `rvest`

**Visualization**: `ggplot2`, `viridis`, `scales`

**Statistical Analysis**: `lme4`, `lmerTest`, `effsize`

**Sentiment Analysis**: `sentimentr`, `syuzhet`

**Model Visualization**: `dotwhisker`, `broom.mixed`, `sjPlot`

## Key Contributions

1. **Interdisciplinary Approach**: Combines digital humanities methodology with rigorous statistical testing
2. **Methodological Transparency**: Detailed data cleaning, preprocessing, and analytical procedures
3. **Multiple Analysis Layers**: Three-tiered sentiment analysis (word-level, sentence-level, emotion classification)
4. **Robustness**: Mixed-effects modeling controls for character-level variation and data nesting
5. **Critical Reflection**: In-depth discussion of limitations, including the "protagonist effect" and sample imbalance

## Quality Assurance

- Manual data validation and cross-checking between subtitle and character datasets
- Shapiro-Wilk normality tests to verify statistical assumptions
- Variance homogeneity testing before applying parametric tests
- Wilcoxon rank-sum tests for robustness verification
- Effect size reporting alongside p-values for practical significance

## Implications

The findings suggest that *Zootopia* reflects gender equality aims through narrative design, with character-level differences primarily driven by narrative roles rather than gender stereotyping. However, the marginally significant sentiment difference (females showing more positive sentiment) echoes traditional gender stereotypes, though only weakly. This reflects the film's efforts toward gender de-differentiation while acknowledging the ongoing influence of broader cultural patterns.

## Limitations & Future Work

**Current Limitations**:
- Limited film sample (single work) affects generalizability
- Small character count for some demographic groups
- Sentiment analysis sensitivity to context and linguistic variation
- Data imbalance due to protagonist dominance

**Future Directions**:
- Comparative analysis across multiple Disney animated films
- Enhanced sentiment analysis models using deep learning approaches
- Expansion to include multimodal analysis (visual, audio components)
- Longitudinal analysis of gender representation trends in animation

## Authors

**Student Team**: LC, NC, LJJ, GQY, MYT  
**Course**: Introduction to Digital Humanities  
**Institution**: BFSU, Beijing, China
**Date**: 2026/03/22

## License

[MIT, CC-BY-4.0]

## Acknowledgments

- Zootopia Fandom Wiki for character and transcript data
- AFINN-111 sentiment dictionary
- NRC emotion lexicon
- R community and open-source package developers

---

## Getting Started

### Prerequisites
- R (version 4.0+)
- Quarto (for rendering qmd files)
- Required packages (see `Used_Package.md`)

### Installation
1. Clone this repository
2. Install required R packages using `pacman::p_load()`
3. Ensure data files are present in the `/data` directory
4. Open `Main_Document.qmd` in RStudio or Quarto CLI

### Running the Analysis
```r
# Render the complete analysis
quarto::quarto_render("Main_Document.qmd")
```

## Contact & Support

For questions or issues regarding this analysis, please contact [lucas0805happylinchen@gmail.com].
