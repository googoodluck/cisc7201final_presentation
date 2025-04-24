# Predicting Macau's Tourism Data Using Machine Learning Models

## Introduction and Motivation (简介和动机)

Hello everyone, today I will be presenting my research on predicting Macau's tourism data using machine learning models. This study aims to provide actionable insights and data-driven recommendations to stakeholders in Macau's tourism industry. By accurately predicting tourism trends, businesses and policymakers can make informed decisions to enhance the visitor experience, optimize resource allocation, and improve overall industry performance.

大家好，今天我将介绍我关于使用机器学习模型预测澳门旅游数据的研究。本研究旨在为澳门旅游业的利益相关者提供可操作的见解和数据驱动的建议。通过准确预测旅游趋势，企业和政策制定者可以做出明智的决策，以提升游客体验，优化资源分配，并提高整体行业绩效。

## Methodology (方法)

### Data Downloading (数据下载)

To download the required datasets, I utilized a Python script with Selenium for web automation. The script accessed the Macau Open Data website, navigated to the datasets section, and performed searches based on specified keywords. The datasets included information on total consumption, average consumption of staying and non-staying tourists, inbound tourists, staying tourists, non-staying tourists, hotel occupancy rate, mainland individual visitors, average length of stay for tourists, and average length of stay for guests.

为了下载所需的数据集，我使用了一个带有 Selenium 的 Python 脚本进行网络自动化。该脚本访问了澳门开放数据网站，导航到数据集部分，并根据指定的关键词进行搜索。数据集包括总消费、留宿和不过夜旅客的平均消费、入境旅客、留宿旅客、不过夜旅客、酒店入住率、内地个人游客、游客平均停留时间和客人平均停留时间的信息。

### Data Processing (数据处理)

We created a unified DataFrame with a quarterly time index from 2010 to 2024. This involved extracting and adding relevant data from each dataset to the DataFrame, handling missing values, and converting data types to ensure consistency and readiness for analysis.

我们创建了一个从 2010 年到 2024 年的季度时间索引的统一 DataFrame。这包括从每个数据集中提取和添加相关数据，处理缺失值，并转换数据类型以确保一致性和分析准备。

### Data Analysis and Visualization (数据分析和可视化)

Based on the processed dataset, we created various visualizations including line charts, box plots, dynamic and static PCA plots, UMAP plots, and heatmaps. These visualizations clearly showed the anomalies in the data during the pandemic period.

之后根据处理好的数据集构建了一些可视化图形，包括折线图、箱型图、动态和静态的 PCA 图及 UMAP 图，以及热点图。可以很直观地看到疫情期间的数据在我们的图形上十分的突兀。

### Coding (编码)

#### Initial Model (初始模型)

We initially created a simple consumption prediction model using polynomial regression, including all features in the dataset. The results showed a high degree of fit. We then selected four features to explore their relationship with total consumption, which also showed a high coefficient of determination (R²). However, when we reduced the features to only inbound tourists and release date, the coefficient of determination decreased, indicating that average consumption is a necessary feature.

我们最初使用多项式回归创建了一个简单的消费预测模型，将数据集分为测试集和验证集，结果表明模型的拟合度很高。之后选择了四个特征来探索它们与总消费的关系，结果表明这些特征与总消费之间的决定系数（R²）很高。然后我们进一步缩减，只保留入境旅客和发布日期两个特征，发现决定系数存在问题。因此，平均消费作为特征是必要的。

#### Improved Model (改进模型)

Further analysis revealed a significant correlation between inbound tourists and the other three features. This finding prompted us to focus on predicting inbound tourists as an intermediary step. We assumed that the average consumption values during the pandemic would be equal to the average values from the previous quarters.

进一步分析显示，入境旅客与其他三个特征之间存在显著相关性。这一发现促使我们将预测入境旅客作为中间步骤。我们假设疫情期间的平均消费值等于前几个季度的平均值。我们只需要探索日期和入境旅客之间的关系。

### Predictive Analysis (预测分析)

Using the trained model, we predicted the inbound tourists for the period after 2020. These predictions were then used to forecast the total consumption for the same period. The predicted values were combined with the actual data to visualize the impact of the pandemic on Macau's tourism industry.

使用训练好的模型，我们预测了 2020 年之后的入境旅客数量。这些预测结果随后用于预测同期的总消费。将预测值与实际数据结合起来，以可视化疫情对澳门旅游业的影响。

## Results (结果)

The results were plotted to compare the actual total consumption with the predicted total consumption under the assumption of no pandemic. The visualization clearly showed the differences and provided insights into the potential impact of the pandemic on the tourism sector.

结果被绘制成图表，以比较实际总消费与假设没有疫情情况下的预测总消费。可视化结果清楚地显示了差异，并提供了对疫情对旅游业潜在影响的见解。

## Conclusion (结论)

In conclusion, this study demonstrates the effectiveness of using machine learning models to predict tourism trends in Macau. The insights gained from this research can help businesses and policymakers make informed decisions, ultimately contributing to the sustainable development of Macau's tourism sector.

总之，本研究展示了使用机器学习模型预测澳门旅游趋势的有效性。从这项研究中获得的见解可以帮助企业和政策制定者做出明智的决策，最终有助于澳门旅游业的可持续发展。