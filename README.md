Mining Software Repository: 

This repository contains the results and analysis of a comprehensive three-week study investigating software development practices through repository mining techniques. 
Our research explores Self-Admitted Technical Debt (SATD), pull request dynamics, and code readability across multiple open-source projects, providing insights into development decision-making processes and their impact on code quality.


Our research was conducted over three weeks, with each week focusing on a different aspect of software development:

Week 1: Self-Admitted Technical Debt (SATD) analysis

Week 2: Pull request dynamics and merge prediction

Week 3: Code readability investigation and improvement patterns


Week1 :Self-Admitted Technical Debt Analysis

The first week, we focused on Self Admitted Technical Debt(SATD)- defined as instances where developers write comments admittng their code is not good quality. It happens when developers know they wrote poor code and leave comments saying it needs to be fixed later. This research analyzed SATD examples from software projects like Eclipse, Chromium OS, ArgoUML, and Apache, where developers wrote comments such as  "//TODO this is such a hack" or "//FIXME: This is a gross hack." These comments represent developers' honest admissions that they're taking shortcuts due to time constraints or other pressures.

Research questions : 

RQ1: Does SATD in Code Comments Correlate with High Code Complexity?

To answering this question, we searched through source code files to identify methods containing SATD, calculated  cyclomatic complexity for each of these methods by counting their decision points and execution paths, and then compared the average complexity scores of SATD-containing methods against methods without any SATD comments to determine if developers tend to acknowledge technical debt in more complex code sections.

RQ2: Does SATD in Commit Messages Correlate with High Code Complexity?

For this reseach question, we analyzed the project's Git commit history to identify commits where developersmentioned technical debt in their commit messages (such as 'quick hack for now' or 'temporary workaround'), examined the actual code changes made in those commits to calculate the cyclomatic complexity of the modified methods, and then performed a comparative statistical analysis between the complexity of code changes in SATD-related commits versus regular commits to see if developers tend to introduce or modify more complex code when they're consciously taking on technical debt.

RQ3: our Own Question - Categories of SATD

In our custom research question, we designed a study to investigate whether different categories of self-admitted technical debt exhibit varying relationships with code complexity by first developing a classification system to label SATD instances into predefined categories (such as design debt, defect debt, or documentation debt), applying this categorization to the SATD comments and commits I had identified, and then analyzing whether certain types of technical debt are more strongly associated with high complexity code than others, providing insights into which kinds of shortcuts developers take in different complexity scenarios. 

Finally, we conducted statistical comparisons between the complexity distributions of SATD-containing methods versus non-SATD control groups to determine whether developers' self-acknowledged technical debt correlates with measurable code quality metrics. This approach enabled us to empirically test our research questions about the relationship between developer awareness of suboptimal solutions and actual code complexity.

Week 2: Pull Request Analysis

In the second week, we shifted our focus to understanding pull request dynamics across different repositories. We wanted to understand what causes developers to request changes in pull requests, whether we can predict if a pull request will be merged, and how different types of review comments affect the merge outcome.

Research Questions:

RQ1: What are the reasons for changes in pull requests?

We investigated the primary factors driving modification requests in pull requests across different software repositories by manually reviewing and categorizing comments from 100 pull requests, then using automated analysis to scale our findings across entire datasets.

RQ2: Can we predict whether a pull request will be merged?

We developed a machine learning model to forecast the likelihood of a pull request being accepted and merged based on various features like title length, number of comments, and other metadata characteristics.

RQ3: How do different types of review comments affect pull request merges?

We analyzed the impact of various review comment types on the probability of pull request acceptance by categorizing comments and examining their correlation with successful merges.

We analyzed pull request data from three diverse repositories: JBoss Parent POM, Eclipse Xpect, and Netflix Falcor, examining a total of 1,002 pull requests (860 merged and 142 non-merged). Our approach combined both qualitative examination through manual review of comments and quantitative techniques using machine learning and statistical analysis.

Week 3: Code Readability Investigation

In the third week, we investigated code readability patterns across Google's Java repositories (Gson, Guice, and Truth) to understand whether developers deliberately improve readability, if we can predict readability improvements, and how commit size affects readability outcomes.

Research Questions:

RQ1: Do developers increase readability deliberately?

We examined whether developers consciously attempt to improve code readability by analyzing commit messages for explicit readability improvement keywords and comparing the outcomes of these intentional efforts.

RQ2: Can we predict whether the readability of a file will be improved?

We developed machine learning models to predict readability improvements based on commit message text features, testing both cross-project and within-project approaches.

RQ3: Do larger commits (with more changed files) impact readability differently than smaller ones?

We investigated whether the size of commits (measured by number of files changed) affects readability outcomes by categorizing commits into different size groups and analyzing their success rates.

We used PyDriller to extract commit data and the University of Molise Java readability tool to evaluate source code across five dimensions: structural metrics, visual arrangement, naming conventions, comment quality, and complexity patterns. For text analysis of commit messages, we applied standard NLP preprocessing and developed a keyword dictionary covering nine readability-related categories.

Tools and Technologies Used:

Throughout this three-week study, we employed various tools and libraries:

PyDriller for commit and repository analysis

Lizard for cyclomatic complexity measurement

GitHub API for pull request data extraction

University of Molise Readability Tool for Java code readability assessment

Python libraries: pandas, scikit-learn, numpy, matplotlib, seaborn for data analysis and machine learning

Statistical tools: Mann-Whitney U tests, Shapiro-Wilk normality tests for hypothesis testing
NLP techniques: TF-IDF vectorization, text preprocessing for commit message analysis

Main Conclusions:

This three-week investigation provided valuable insights into software development practices:

Technical debt acknowledgment correlates with complexity: Developers do tend to acknowledge technical debt in more complex code sections, suggesting they're aware of quality issues when they arise.

Pull request patterns are predictable: We can predict merge outcomes with reasonable accuracy, and the type of review comments significantly impacts merge success.

Readability improvements can be predicted: Developers who explicitly mention readability improvements in their commit messages are more likely to actually improve readability, and smaller commits tend to be more successful at improving readability.
