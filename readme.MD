# Time-MMD: A New Multi-Domain Multimodal Dataset for Time Series Analysis


## Introduction

Time-MMD is the first multi-domain, multimodal time series dataset covering 9 primary data domains. We ensures fine-grained modality alignment with text-numerical series, eliminates data contamination, and provides high usability. (Check [our paper](https://arxiv.org/abs/2406.08627) for more details!)

## Dataset Overview

Time-MMD consists of 1) numerical sequences 2) textual sequences. Binary timestamps `(start, end)` are occupied which enables the adapatation onto various tasks or demands.

The structure of this repo is:

```
- Readme.MD
- numerical
    - Agriculture
        - Agriculture.csv
    - (Domain Name)
        - (Domain Name).csv
    ...
- textual
    - (Domain Name)
        - (Domain Name)_report.csv
        - (Domain Name)_search.csv
-- Downstream_Tasks
    - ShortTerm Forecasting
    - LongTerm Forecasting
    - Imputation
    - Anomaly Detection
```

Here, Downstream_Tasks is used to introduce how Time-MMD supports different downstream tasks. 
For Short-Term and Long-Term Forecasting, please check our library [MM-TSFlib](https://github.com/AdityaLab/MM-TSFlib) for detailed usage examples.
we denote to support more tasks and domains in the future. Please feel free to let us know your demands.

### Numerical Data

Numerical data of each domain contains a csv file with has the following format:

```
start_date, end_date, OT, (other variable 1), (other variable 2), ...
```
Here, OT represents the default target variable for prediction in each dataset. Its specific meaning is as follows:
<div align="center">
    <img src="https://github.com/AdityaLab/Time-MMD/blob/main/DescriptionOfOT.png" width="500">
</div>

For specific data sources, please refer to Appendix C of our paper.

### Textual Data

Textual data of each domain contains two csv file, one for report data and another for search data. All data are in a unified format:

```
start_date, end_date, fact, pred
```

Visualization of relevant report (a, left) and search (b, right) counts in Time-MMD over time is as follows:
<div align="center">
    <img src="https://github.com/AdityaLab/Time-MMD/blob/main/VisualizationOfText.png" width="500">
</div>

<!-- Here's a complete list of domains and corresponding properties:

|Domain|Target|Frequency|Timestamps|Timespan|
|---|---|---|---|---|
|Agriculture|Retail Broiler Composite|Monthly|496|1983-Present|
|Climate|Drought Level|Monthly|496|1983-Present|
|Economy|International Trade Balance -->

For specific data sources, please refer to Appendix C of our paper.
### Use Case
For the multi-modal time-series forecasting task based on the Time-MMD dataset, you may check our library [MM-TSFlib](https://github.com/AdityaLab/MM-TSFlib). Please note that this Lib is only a first-step attempt toward the multimodal extension of TSF and does not represent the optimal solution.

## Citation

If you find this repo useful, please cite our paper.

```
@misc{liu2024timemmd,
      title={Time-MMD: A New Multi-Domain Multimodal Dataset for Time Series Analysis}, 
      author={Haoxin Liu and Shangqing Xu and Zhiyuan Zhao and Lingkai Kong and Harshavardhan Kamarthi and Aditya B. Sasanur and Megha Sharma and Jiaming Cui and Qingsong Wen and Chao Zhang and B. Aditya Prakash},
      year={2024},
      eprint={2406.08627},
      archivePrefix={arXiv},
      primaryClass={id='cs.LG' full_name='Machine Learning' is_active=True alt_name=None in_archive='cs' is_general=False description='Papers on all aspects of machine learning research (supervised, unsupervised, reinforcement learning, bandit problems, and so on) including also robustness, explanation, fairness, and methodology. cs.LG is also an appropriate primary category for applications of machine learning methods.'}
}
```

## Contact
If you have any questions or suggestions, feel free to contact:
hliu763@gatech.edu
