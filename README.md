# Mining Software Repository Study

This repository contains the results and analysis of a comprehensive three-week study investigating software development practices through repository mining techniques. 
Our research explores Self-Admitted Technical Debt (SATD), pull request dynamics, and code readability across multiple open-source projects, providing insights into development decision-making processes and their impact on code quality.

## Study Overview

• **Duration**: 3 weeks of intensive analysis

• **Focus Areas**: Technical debt acknowledgment, collaboration patterns, and code quality evolution

• **Repositories Analyzed**: Eclipse, Chromium OS, ArgoUML, Apache projects, JBoss, Netflix Falcor, Google Java projects

• **Data Scale**: 12,968 methods, 5,312 commits, 1,002 pull requests, 17,630 readability assessments

## Research Questions 

### Week 1: Self-Admitted Technical Debt (SATD) Analysis

#### Research Questions:

• **RQ1**: Does SATD in code comments correlate with high code complexity?

• **RQ2**: Does SATD in commit messages correlate with high code complexity?  

• **RQ3**: Do different SATD categories exhibit varying relationships with complexity?

#### Results:

• **Strong correlation found**: Methods with SATD showed +2.14 mean complexity increase vs -0.87 for non-SATD methods

• **Statistical significance**: Mann-Whitney U test confirmed p < 0.001 with medium effect size (0.56)

• **Category-specific patterns**: Design Debt showed strongest correlation with complexity increases (+2.3), while Documentation Debt had minimal impact (-0.4)

• **Commit-level analysis**: Less pronounced relationship at broader commit level (p = 0.078)

### Week 2: Pull Request Analysis

#### Research Questions:

• **RQ1**: What are the primary reasons for pull request changes?

• **RQ2**: Can we predict pull request merge outcomes?

• **RQ3**: How do different review comment types affect merge probability?

#### Results:

• **Primary change drivers**: Failing tests (18.5%), logic errors (13.0%), and merge conflicts (13.0%)

• **Prediction accuracy**: Random Forest model achieved 89% overall accuracy with 0.74 ROC curve

• **High sensitivity**: 98.27% accuracy for predicting merged PRs (170/173 correct)

• **Comment type impact**: Review-oriented comments achieved 100% merge rate, while issue-focused comments had 66.8% success rate

• **Key predictive features**: Title length (0.257), total comments (0.139), issue comments (0.121)

### Week 3: Code Readability Investigation

#### Research Questions:

• **RQ1**: Do developers deliberately improve readability?

• **RQ2**: Can we predict readability improvements from commit messages?

• **RQ3**: How does commit size impact readability outcomes?

#### Results:

• **Deliberate improvement**: ~15% of commits contained explicit readability keywords with statistically significant better outcomes

• **Predictive modeling**: 67% accuracy achieved using commit message text features

• **Cross-project patterns**: Models performed better across repositories than within single projects

• **Commit size effect**: Single-file commits achieved highest success rate (42.7%), while few-files commits had lowest (26.0%)

• **Common improvement terms**: "format," "simplifi," "renam," "javadoc" strongly associated with readability gains

## Tools and Technologies

### Data Mining & Analysis:

• **PyDriller**: Repository commit analysis and metadata extraction

• **Lizard**: Cyclomatic complexity measurement

• **GitHub API**: Pull request data extraction and processing

• **University of Molise Readability Tool**: Java code readability assessment

### Machine Learning & Statistics:

• **Python Libraries**: pandas, scikit-learn, numpy, matplotlib, seaborn

• **Models**: Random Forest classifiers for prediction tasks

• **Statistical Tests**: Mann-Whitney U tests, Shapiro-Wilk normality tests

• **NLP Techniques**: TF-IDF vectorization, text preprocessing for commit message analysis

### Repositories Analyzed:

• **Apache Projects**: Commons-Net, Phoenix, Zookeeper, Tapestry-5, Calcite

• **Google Java**: Gson, Guice, Truth

• **GitHub Projects**: JBoss Parent POM, Eclipse Xpect, Netflix Falcor

## Statistical Methodology


• **Sample Sizes**: 12,968 methods analyzed for complexity, 1,002 pull requests (860 merged, 142 non-merged)

• **Validation Approaches**: Cross-project and within-project model evaluation

• **Effect Size Calculations**: Practical significance assessment beyond statistical significance

• **Normality Testing**: Shapiro-Wilk tests to determine appropriate statistical methods

• **Multi-dimensional Analysis**: Five readability dimensions (structure, visual, naming, comments, complexity)

## Main Conclusions

### Technical Debt Insights:

• **Awareness correlation**: Developers acknowledge technical debt in more complex code sections

• **Category differences**: Design debt most strongly associated with complexity increases

• **Method-level vs commit-level**: Individual method patterns more pronounced than broad commit patterns

### Collaboration Patterns:

• **Predictable outcomes**: Pull request success can be forecasted with reasonable accuracy

• **Communication impact**: Review comment types significantly influence merge probability

• **Quality indicators**: Title length and comment volume serve as merge predictors

### Code Quality Evolution:

• **Intentional improvement**: Explicit readability mentions correlate with better outcomes

• **Size matters**: Smaller commits more successful at improving readability

• **Cross-project consistency**: Readability improvement patterns transcend individual repositories

## Team


• **Mahdieh Ahmadi** - University of Passau (ahmadi13@ads.uni-passau.de)

• **Erfan Mollasalehi** - University of Passau (mollas01@ads.uni-passau.de)  

• **Zahra Borzoo** - University of Passau (borzoo01@ads.uni-passau.de)

## Acknowledgments


• Special thanks to **Prof. Dr. Steffen Herbold** and course instructors for continuous guidance

• University of Passau AI Engineering department for research support
