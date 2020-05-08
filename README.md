Presented by: [Ray Hong](http://www.rayhong.net), [Jessica Hullman](http://users.eecs.northwestern.edu/~jhullman/), and [Enrico Bertini](http://enrico.bertini.io/)

## Background

With the rapid increase in the deployment of machine learning (ML) in a wide range of practical application areas, we are witnessing increased concern about our capabilities to understand _how_ ML models work; shifting our focus on interacting with ML from a unidirectional focus on _model accuracy_ to a larger perspective that includes a strong focus on ML _model interpretability_. Despite this rapid expansion in model interpretability tools and formal and empirical definitions, our understanding of how interpretability is understood by and how it impacts the actual ML practitioners is still limited. Bridging this gap with an empirical approach is necessary for grounding our work in the real problems we face when dealing with interpretability issues.

## Methodology

This project presents our results of the empirical inquiry; we conducted semi-structured interviews with 22 ML practitioners from 20 different companies across 5 months of a period, who work in a wide variety of domains including banking, finance, healthcare, IT, social media, consulting, manufacturing, internet services, and transportation. They are responsible for building models that are state-of-the-art in their field; some of the models they built are used by millions of daily active users and/or support critical decisions where life is at stake (17 data scientists or machine learning engineers (DS), 2 software engineers who build infrastructure related to model interpretability (SE), 2 product managers (PM), and one UX researcher (UX), see the table below).

| PID | Company Domain     | Job title and role                | Domain problems                              |
| :-- | :----------------- | :-------------------------------- | -------------------------------------------- |
| P1  | Software           | Staff manager in Research (DS)    | Object detection for telepresence robots     |
| P2  | Consulting         | CEO (DS)                          | Identity recognition, fraud detection        |
| P3  | Banking            | Senior ML Engineer (DS)           | Credit risk assessment, call transcription   |
| P4  | Software           | Lead Data Scientist (DS)          | Sentiment analysis, object detection, AutoML |
| P5  | Banking            | Data Engineer (SE)                | Anomalous recurring online payment detection |
| P6  | Banking/Finance    | Head of AI (DS)                   | Credit evaluation for business loans         |
| P7  | Internet Services  | Senior Software Developer (SE)    | Tooling for tabular/image data               |
| P8  | Social Media       | Data Scientist (DS)               | Service user retention prediction            |
| P9  | Banking/Finance    | Principal Data Scientist          | Customer acquisition/financial forcasting    |
| P10 | Software           | Product Manager (PM)              | Tooling (visualizing model interpretation)   |
| P11 | Consulting         | Lead Data Scientist (DS)          | Revenue maximization strategy prediction     |
| P12 | Internet Services  | Head of ML (DS)                   | Oversees more than 50 models                 |
| P13 | Transportation     | Senior Software Engineer (DS)     | Place recommendation, partners acquisition   |
| P14 | Social Media       | ML Engineering Manager (DS)       | Advertisement ranking                        |
| P15 | Transportation S/W | Senior ML Research Scientist (DS) | Claim handling, driver voice assistance      |
| P16 | Healthcare         | Medical Doctor (DS)               | Mortality, deterioration, and radiology      |
| P17 | Manufacturing      | Senior Researh Scientist (DS)     | Oil pump/power grid operation                |
| P18 | Software/Research  | CTO (SE)                          | Tooling (image-based model interpretation)   |
| P19 | Finance            | Senior Analytics Expert (PM)      | Credit score prediction                      |
| P20 | Healthcare         | CTO, Head of Data Science (DS)    | Lung cancer operation                        |
| P21 | Software           | Principal Design Manager (UX)     | Best images selection, transcription         |
| P22 | Healthcare         | Senior Data Scientist (DS)        | Care management/resource utilization         |

## Results

In total, we collected 19 hours and 10 minutes of audio recorded interviews and performed qualitative analysis. Our interviewing approach aimed to differentiate how our interviewees perceived interpretability _roles_, _processes_, _goals_, and associated _challenges and design opportunities_. We will briefly cover some notable challenges and design opportunity; if interested, our full manuscript is available as follows:

[https://arxiv.org/abs/2004.11440](https://arxiv.org/abs/2004.11440)

#### 1. Identifying, Representing, and Integrating Human Expectations

One of the most recurring reasons for practitioners in performing model interpretability was seeking for "edge cases" where the model behaves _unexpectedly_ than human expectations formed based on their domain experience and common sense. Throughout the interviews, we found model interpretability is about the _comparison_ between a human mental model and a model's behavior, identification of differences, understanding why such differences occurred, and deciding whom--a human, or a model--to follow. We propose that interpretability research would benefit from interfaces and mechanisms to help a human (1) articulate their expectations around predictions in model interpretation tasks (2) efficiently recognize the gaps between their expectations and model representations, (3) gain context through further evidence available to the model that may help them assess the gap, and (4) enable them to debug/change model behavior based on their findings.

More systematic approaches to identifying these important "anchors" for interpretability work would increase interpretability-related task productivity. Looking to research in belief elicitation and mental model discovery within psychology, economics, and related disciplines in designing such approaches may be informative.

#### 2. Communicating and Summarizing Model Behavior

We observed model interpretability related tasks are performed as a form of "dialogue" between different stakeholders within an organization, which often results in misinterpretation. Several participants voiced the necessity for _interpretability for everyone_ which refers to solutions that would be appropriate for both data scientists and domain experts. The cooperative and social nature of much of the interpretability work suggests that transferring knowledge frequently happens in the form of model "hand-offs". In these situations, having representations, such as visualizations, that can concisely capture how those receiving a model might expect it to behave about their mental models could be useful to provide the types of model "bug" discoveries that some participants described occurring unexpectedly after deployment.

#### 3. Scalable and Integratable Interpretabiltiy Approach for Model Comparison and Data Preparation

Many participants shared their concerns with integrating existing interpretability tools in their workflows and organizational infrastructure. Problems commonly cited are that: methods are not available because they were developed in academic settings, where creating robust and dependable software is not the norm; tools were not easy to integrate in existing platforms because they cannot be adapted to their specific environment; or simply that tools do not scale to the sheer size of their data sets.

We suggest two emerging interpretability-related use cases: _data preparation_, and _model comparison_. Interpretability tools are needed in even an ideation stage where no complete data is ready for building their target model. Better tools are needed before training to assist with data debugging, to detect issues with data before they are used for training, as well as for feature engineering and model design. Our findings suggest that having a better way for a model designer to test hypotheses about what effect different decisions on _feature sets_ may have on model performance without necessarily building all these models entirely would improve model interpretability practice. Participants also pointed out that existing model interpretability approaches seem to overlook important, but perhaps less principled, aspects of approaches to comparing the outputs of multiple models to build a deeper understanding. We identified several different cases for model comparison: when comparing different parameters, selection of features, timestamps, and more.

#### 4. Post Deployment Support

We found multiple participants are often struggling with monitoring the models' behavior and update their model based on a set of insights while stakeholders apply their model's prediction outcomes. We believe data visualization tools are one way to facilitate monitoring model behavior. Automated anomaly detection may be useful in addition, to identify and surface potentially troubling behaviors, given an appropriate specification of critical expectations that should hold such as one learned from domain experts. As several participants alluded to, this is particularly hard in production because problems may stem from different modules of complex data architecture and not only from the model itself.

## Cite

This work is accepted in the 23rd ACM Conference on Computer-Supported Cooperative Work and Social Computing (CSCW2020). We described emerging themes, insightful quotes from our participants, and more detailed findings in our [paper](https://arxiv.org/abs/2004.11440).

Bibtex:

```
@article{hong2019design,
  title={Human Factors in Model Interpretability:Industry Practices},
  author={Hong, Sungsoo Ray and Hullman, Jessica and Bertini, Enrico},
  journal={Proceedings of the ACM on Human-Computer Interaction},
  volume={4},
  number={CSCW1},
  pages={1--26},
  year={2020},
  publisher={ACM New York, NY, USA},
  DOI={10.1145/3392878}
}
```

APA in-text:

```
Sungsoo Ray Hong, Jessica Hullman, and Enrico Bertini. 2020.
Human Factors in Model Interpretability: Industry Practices, Challenges, and Needs.
Proc. ACM Hum.-Comput. Interact.4, CSCW1, Article 311 (May 2020), 26 pages. https://doi.org/10.1145/33928781
```

05-08-2020
