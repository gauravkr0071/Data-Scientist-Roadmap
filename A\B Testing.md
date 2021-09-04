### __Overview__
- A/B testing is a popular way to test your products and is gaining steam in the data science field
- Here, we’ll understand what A/B testing is and how you can leverage A/B testing in data science using Python

### __Introduction___

Statistical analysis is our best tool for predicting outcomes we don’t know, using the information we know.

Picture this scenario – You have made certain changes to your website recently. Unfortunately, you have no way of knowing with full accuracy how the next 100,000 people who visit your website will behave. That is the information we cannot know today, and if we were to wait until those 100,000 people visited our site, it would be too late to optimize their experience.

This seems to be a classic Catch-22 situation!

This is where a data scientist can take control. A data scientist collects and studies the data available to help optimize the website for a better consumer experience. And for this, it is imperative to know how to use various statistical tools, especially the concept of A/B Testing.
![image](https://user-images.githubusercontent.com/51910127/132100430-d4db43cb-ff20-48ac-be41-b23665044c22.png)

A/B Testing is a widely used concept in most industries nowadays, and data scientists are at the forefront of implementing it. In this article, I will explain A/B testing in-depth and how a data scientist can leverage it to suggest changes in a product.

### __Table of contents__
- What is A/B testing?
- How does A/B testing work?
- Statistical significance of the Test
- Mistakes we must avoid while conducting the A/B test
- When to use A/B test

### __What is A/B testing?__

A/B testing is a basic randomized control experiment. It is a way to compare the two versions of a variable to find out which performs better in a controlled environment.

For instance, let’s say you own a company and want to increase the sales of your product. Here, either you can use random experiments, or you can apply scientific and statistical methods. A/B testing is one of the most prominent and widely used statistical tools.

In the above scenario, you may divide the products into two parts – A and B. Here A will remain unchanged while you make significant changes in B’s packaging. Now, on the basis of the response from customer groups who used A and B respectively, you try to decide which is performing better.
![image](https://user-images.githubusercontent.com/51910127/132100500-09a00f82-2cd7-4000-b21c-1d2ef9046b19.png)
It is a hypothetical testing methodology for making decisions that estimate population parameters based on sample statistics. The population refers to all the customers buying your product, while the sample refers to the number of customers that participated in the test.

### __How does A/B Testing Work?__

The big question!

In this section, let’s understand through an example the logic and methodology behind the concept of A/B testing.

Let’s say there is an e-commerce company XYZ. It wants to make some changes in its newsletter format to increase the traffic on its website. It takes the original newsletter and marks it A and makes some changes in the language of A and calls it B. Both newsletters are otherwise the same in color, headlines, and format.
![image](https://user-images.githubusercontent.com/51910127/132100526-c9cb9ad5-8e17-404d-9ced-800ff6889d39.png)

### __Objective__

Our objective here is to check which newsletter brings higher traffic on the website i.e the conversion rate. We will use A/B testing and collect data to analyze which newsletter performs better.

- __Make a Hypothesis__ : Before making a hypothesis, let’s first understand what is a hypothesis.

A hypothesis is a tentative insight into the natural world; a concept that is not yet verified but if true would explain certain facts or phenomena.

It is an educated guess about something in the world around you. It should be testable, either by experiment or observation. In our example, the hypothesis can be “By making changes in the language of the newsletter, we can get more traffic on the website”.

In hypothesis testing, we have to make two hypotheses i.e Null hypothesis and the alternative hypothesis. Let’s have a look at both.

1. __Null hypothesis or H0:__ The null hypothesis is the one that states that sample observations result purely from chance. From an A/B test perspective, the null hypothesis states that there is no difference between the control and variant groups. It states the default position to be tested or the situation as it is now, i.e. the status quo. Here our H0 is ” there is no difference in the conversion rate in customers receiving newsletter A and B”.
2. __Alternative Hypothesis or H0:__ The alternative hypothesis challenges the null hypothesis and is basically a hypothesis that the researcher believes to be true. The alternative hypothesis is what you might hope that your A/B test will prove to be true.

In our example, the Ha is- __“the conversion rate of newsletter B is higher than those who receive newsletter A“.__

Now, we have to collect enough evidence through our tests to __reject the null hypothesis__.

- __Create Control Group and Test Group__

Once we are ready with our null and alternative hypothesis, the next step is to decide the group of customers that will participate in the test. Here we have two groups – __The Control group__, and __the Test (variant) group.__

The Control Group is the one that will receive newsletter A and the Test Group is the one that will receive newsletter B.

For this experiment, we randomly select 1000 customers – 500 each for our Control group and Test group.

Randomly selecting the sample from the population is called random sampling. It is a technique where each sample in a population has an equal chance of being chosen. __Random sampling is important in hypothesis testing because it eliminates sampling bias, and it’s important to eliminate bias because you want the results of your A/B test to be representative of the entire population rather than the sample itself.__

Another important aspect we must take care of is the __Sample size__. It is required that we determine the minimum sample size for our A/B test before conducting it so that we can eliminate __under coverage bias__. It is the bias from sampling too few observations.

- __Conduct the A/B Test and Collect the Data__

One way to perform the test is to calculate daily conversion rates for both the treatment and the control groups. Since the conversion rate in a group on a certain day represents a single data point, the sample size is actually the number of days. Thus, we will be testing the difference between the mean of daily conversion rates in each group across the testing period.

When we run our experiment for one month, we noticed that the mean conversion rate for the Control group is 16% whereas that for the test Group is 19%.

### __Statistical significance of the Test__

Now, the main question is – Can we conclude from here that the Test group is working better than the control group?

The answer to this is a simple No! For rejecting our null hypothesis we have to prove the Statistical significance of our test.

There are two types of errors that may occur in our hypothesis testing:
1. __Type I error__: We reject the null hypothesis when it is true. That is we accept the variant B when it is not performing better than A
2. __Type II error__: We failed to reject the null hypothesis when it is false. It means we conclude variant B is not good when it performs better than A

To avoid these errors we must calculate the statistical significance of our test.

An experiment is considered to be statistically significant when we have enough evidence to prove that the result we see in the sample also exists in the population.

That means the difference between your control version and the test version is not due to some error or random chance. To prove the statistical significance of our experiment we can use a two-sample T-test.

The __two–sample t–test__ is one of the most commonly used hypothesis tests. It is applied to compare whether the average difference between the two groups.

![image](https://user-images.githubusercontent.com/51910127/132100934-8c5e4683-4dc0-4a27-bcf5-82d4e57fd91e.png)

To understand this, we must be familiar with a few terms:

1. __Significance level (alpha)__: The significance level, also denoted as alpha or α, is the probability of rejecting the null hypothesis when it is true. Generally, we use the significance value of 0.05

2. __P-Value__: It is the probability that the difference between the two values is just because of random chance. P-value is evidence against the null hypothesis. The smaller the p-value stronger the chances to reject the H0. For the significance level of 0.05, if the p-value is lesser than it hence we can reject the null hypothesis 

3. __Confidence interval__: The confidence interval is an observed range in which a given percentage of test outcomes fall. We manually select our desired confidence level at the beginning of our test. Generally, we take a 95% confidence interval 

Next, we can calculate our t statistics using the below formula:

![image](https://user-images.githubusercontent.com/51910127/132100998-c75f9dc7-a728-4606-8226-a60075f18672.png)

Credits : [Analaytics vidhya](https://www.analyticsvidhya.com/blog/2020/10/ab-testing-data-science/)
