### __Chi-Squared Test__

There are two types of chi-square tests. Both use the chi-square statistic and distribution for different purposes:

- A chi-square goodness of fit test determines if sample data matches a population. For more details on this type, see: Goodness of Fit Test.
- A chi-square test for independence compares two variables in a contingency table to see if they are related. In a more general sense, it tests to see whether distributions of categorical variables differ from each another.

### __What is a Chi-Square Statistic?__

The formula for the chi-square statistic used in the chi square test is:

![image](https://user-images.githubusercontent.com/51910127/132259410-a55a3c4b-5257-4aa2-a31c-5bfd17b7fd6e.png)

The subscript “c” is the degrees of freedom. “O” is your observed value and E is your expected value. It’s very rare that you’ll want to actually use this formula to find a critical chi-square value by hand. The summation symbol means that you’ll have to perform a calculation for every single data item in your data set. As you can probably imagine, the calculations can get very, very, lengthy and tedious. Instead, you’ll probably want to use technology:

A chi-square statistic is one way to show a relationship between two categorical variables. In statistics, there are two types of variables: numerical (countable) variables and non-numerical (categorical) variables. The chi-squared statistic is a single number that tells you how much difference exists between your observed counts and the counts you would expect if there were no relationship at all in the population.

There are a few variations on the chi-square statistic. Which one you use depends upon how you collected the data and which hypothesis is being tested. However, all of the variations use the same idea, which is that you are comparing your expected values with the values you actually collect. One of the most common forms can be used for contingency tables:

![image](https://user-images.githubusercontent.com/51910127/132259499-6f675f4d-ebcc-4093-98fe-a328d988ef95.png)

Where O is the observed value, E is the expected value and “i” is the “ith” position in the contingency table.

A low value for chi-square means there is a high correlation between your two sets of data. In theory, if your observed and expected values were equal (“no difference”) then chi-square would be zero — an event that is unlikely to happen in real life. Deciding whether a chi-square test statistic is large enough to indicate a statistically significant difference isn’t as easy it seems. It would be nice if we could say a chi-square test statistic >10 means a difference, but unfortunately that isn’t the case.

You could take your calculated chi-square value and compare it to a critical value from a chi-square table. If the chi-square value is more than the critical value, then there is a significant difference.

You could also use a p-value. First state the null hypothesis and the alternate hypothesis. Then generate a chi-square curve for your results along with a p-value (See: Calculate a chi-square p-value Excel). Small p-values (under 5%) usually indicate that a difference is significant (or “small enough”).

Tip: The Chi-square statistic can only be used on numbers. They can’t be used for percentages, proportions, means or similar statistical values. For example, if you have 10 percent of 200 people, you would need to convert that to a number (20) before you can run a test statistic.

### __Chi Square P-Values.__

A chi square test will give you a p-value. The p-value will tell you if your test results are significant or not. In order to perform a chi square test and get the p-value, you need two pieces of information:

1. Degrees of freedom. That’s just the number of categories minus 1.
2. The alpha level(α). This is chosen by you, or the researcher. The usual alpha level is 0.05 (5%), but you could also have other levels like 0.01 or 0.10.

In elementary statistics or AP statistics, both the degrees of freedom(df) and the alpha level are usually given to you in a question. You don’t normally have to figure out what they are. You may have to figure out the df yourself, but it’s pretty simple: count the categories and subtract 1.

Degrees of freedom are placed as a subscript after the chi-square (Χ2) symbol. For example, the following chi square shows 6 df:
Χ26.
And this chi square shows 4 df:
Χ24.

![image](https://user-images.githubusercontent.com/51910127/132259593-16e0da95-a9a9-4959-966b-4314a53523af.png)


The chi-square distribution (also called the chi-squared distribution) is a special case of the gamma distribution; A chi square distribution with n degrees of freedom is equal to a gamma distribution with a = n / 2 and b = 0.5 (or β = 2).

Let’s say you have a random sample taken from a normal distribution. The chi square distribution is the distribution of the sum of these random samples squared . The degrees of freedom (k) are equal to the number of samples being summed. For example, if you have taken 10 samples from the normal distribution, then df = 10. The degrees of freedom in a chi square distribution is also its mean. In this example, the mean of this particular distribution will be 10. Chi square distributions are always right skewed. However, the greater the degrees of freedom, the more the chi square distribution looks like a normal distribution.

### __Uses__

The chi-squared distribution has many uses in statistics, including:

1. Confidence interval estimation for a population standard deviation of a normal distribution from a sample standard deviation.
2. Independence of two criteria of classification of qualitative variables.
3. Relationships between categorical variables (contingency tables).
4. Sample variance study when the underlying distribution is normal.
5. Tests of deviations of differences between expected and observed frequencies (one-way tables).
6. The chi-square test (a goodness of fit test).

### __How to Calculate a Chi Square Statistic__

![image](https://user-images.githubusercontent.com/51910127/132259704-4ea36ba6-05de-4508-bb07-7138b5c203f3.png)

The chi-square formula is a difficult formula to deal with. That’s mostly because you’re expected to add a large amount of numbers. The easiest way to solve the formula is by making a table.

Example question: 256 visual artists were surveyed to find out their zodiac sign. The results were: Aries (29), Taurus (24), Gemini (22), Cancer (19), Leo (21), Virgo (18), Libra (19), Scorpio (20), Sagittarius (23), Capricorn (18), Aquarius (20), Pisces (23). Test the hypothesis that zodiac signs are evenly distributed across visual artists.


![image](https://user-images.githubusercontent.com/51910127/132338682-1fa7a84b-b541-49e9-83ba-0dacca11c192.png)
![image](https://user-images.githubusercontent.com/51910127/132338772-c17f361a-a2e6-4806-bda8-2aff88d9e7ab.png)
![image](https://user-images.githubusercontent.com/51910127/132338825-1cefb921-67aa-48fa-9a98-e890ef5398b7.png)
![image](https://user-images.githubusercontent.com/51910127/132338912-7ba90d30-f7c5-411c-a283-b8f2bc2c2a95.png)
![image](https://user-images.githubusercontent.com/51910127/132339003-e9ca03e5-5283-4b4a-ad99-59a18bc33f4f.png)
![image](https://user-images.githubusercontent.com/51910127/132339071-51f3703d-ee76-4516-80f1-5812ba702778.png)
![image](https://user-images.githubusercontent.com/51910127/132339150-b07f9ed1-2de6-4e15-b003-4e09ddec6904.png)
![image](https://user-images.githubusercontent.com/51910127/132339216-d0f89338-0d67-45b6-8139-a4d6aa2a5726.png)


[Further Read](https://www.statisticshowto.com/probability-and-statistics/chi-square/) \
[Video link](https://www.youtube.com/watch?v=f53nXHoMXx4&t=1s)
