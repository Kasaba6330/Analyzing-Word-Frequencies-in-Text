# Analyzing-Word-Frequencies-in-Text
This project will guide you through the process of analyzing word frequencies in a text corpus. The goal is to apply the statistical techniques covered so far-such as calculating means, variance, and distributions-to gain insights into the linguistic characteristics of the dataset.

**Project Overview**

**Objective**

The primary objective of this project is to analyze the frequency distribution of words in a given text corpus. This will include:
1. Calculating basic statistics(mean,variance) of word frequencies.
2. Visualizing the frequency distribution of common words.
3. Comparing observed word frequencies with expected distribution (e,g., normal or poisson distributions).
4. Drawing insights about word usage patterns in the dataset.

**Dataset**

For this project, we will use a sample dataset such as the text of "Àsà àti ìse Yorùbá C. L. Adéoyé". You can easily replace this with any other text dataset, such as tweets, product reviews, or news articles.

**Mean**

The mean is the average value of adataset. In NLP, we use the mean to calculate the average lenght of sentences, the average frequncy of words, or other text characteristics.
Let's calculate the mean word frequency in a given text corpus to understand how frequently words appear on average. This can be useful in identifying common terms and filtering out non-informative ones for more effective text analysis.

**Variance**

Variance measures how spread out the values in a dataset are from the mean. In NLP, variance can indicate the variability in sentence length, word frequency, or other text features.

**Binomial Distribution**

The Binomial Distribution is a discrete probability distribution used to model the probability of a fixed number of successes in a fixed number of independent trials, where each trial has only two outcomes: success or failure. This distribution is especially useful in NLP when modelling binary events, such as whether or not a word appears in a sentence.

**NLP Relevance:**

In NLP, the binomial distribution is useful for tasks where we want to know how likely it is for a word to appear a specific number of times across several sentences or documents. This is particularly useful in:

1. Spam Detection: Determining the likelihood of certain words appearing in spam vs. non-spam messages.
2. Sentiment Analysis: Measuring occurrences of positive or Negative words to assess sentiment.
   
**Parameters**

1. n: The number of trials (e.g., number of sentences).
2. p: The probability of success in each trial(e.g., probability that a specific word appears in a sentence).

The formula for binomial distribution is P(X = x) = nCx * p^x * (1-p)^(n-x), where 'n' is the number of trials, 'x' is the number of successes, 'p' is the probability of success on a single trial, and 'nCx' (or nCr) represents the number of combinations of choosing 'x' successes from 'n' trials. 
Here's a breakdown of the formula and its components:
P(X = x)

: The probability of achieving exactly 'x' successes in 'n' trials. 
nCx (or nCr)

: The number of combinations. It is calculated as n! / [x!(n-x)!].
n! (n factorial) is the product of all positive integers up to 'n' (e.g., 5! = 5 × 4 × 3 × 2 × 1 = 120).
x! is the factorial of the number of successes.
(n-x)! is the factorial of the number of failures. 
p^x

: The probability of 'p' successes, where 'p' is the probability of success on a single trial. 
(1-p)^(n-x)

: The probability of '1-p' (the probability of failure) raised to the power of (n-x), the number of failures. 
In summary, you multiply the number of ways to get 'x' successes by the probability of those successes and the probability of the failures that occur in the remaining trials. 

**Example in NLP:**

Imagine we want to model the likelihood of a particular word appearing in a set of sentences. If a word has a probability (p) of appearing in any given sentence, we can use the binomial distribution to calculate the probability that the word appears exactly(k) times in (n) sentences. For example, if we want to calculate the probability of the word 'data' appearing exactly 3 times in  10 sentences, given that it has a 30% chance of appearing each sentence, we can use the binomial distribution.

**Poisson Distribution**

The Poisson Distribution is a discrete probability distribution used to model the probability of a given number of events happening independently and at a constant rate. It's especially useful in NLP for modelling word occurrences when we assume a constant average rate of occurrence.

**NLP Relevance:**

The Poisson distribution is valuable in tasks where we analyze  the frequency of rare or specialised terms across a large dataset. This distribution supports:

1. Information Retrieval: Modelling the likelihood of rare query terms to improve search accuracy.
2. Lexical Analysis: Analysing the frequency of infrequent words, like domain-specific terminology in technical documents.

**Parameters**

1. λ (lambda): The average rate (or mean) of occurrences within the interval.

**Formula**

The Poisson distribution formula to find the probability of exactly 'x' events occurring in a fixed interval is:
P(X=x) = (e⁻λ λˣ) / x! 

Where:

P(X=x): is the probability of exactly x events occurring.

λ (lambda): is the average rate of events per interval. 

e: is the mathematical constant, approximately 2.71828. 

x: is the actual number of events you are interested in. 

x!: is the factorial of x (e.g., 3! = 3 × 2 × 1 = 6). 

**Example in NLP**

The Poisson distribution is suitable for modelling the number of times a rare word appears in a document of fixed length. For instance, if a particular technical term appears 5 times on average in specific papers of 1000 words, we can use the Poisson distribution to calculate the probability of it appearing exactly (k) times in a new document.

**Normal Distribution**

The Normal Distribution, also known as the Gaussian distribution, is a continuous probability distribution commonly used to model continuous data. It's symmetric and has a "bell curve' shape, which makes it suitable for phenomena that cluster around a mean value. In NLP, the normal distribution is often applied to model features like sentence length or word usage frequency.

**NLP Relevance**

In NLP, the normal distribution is used to model features that vary continously and cluster around a mean value. This is useful in:

1. Language Modeling: Modeling sentence lengths for generating realistic sentences.
2. Readability Analysis: Estimating word or sentence length distributions to assess readability.
   
**Parameters**

1. μ (mu): The mean or average of the distribution
2. σ (sigma): The standard deviation, which represents the spread of data around the mean.

**Formula**

The normal distribution formula, or probability density function (PDF), is given by:
f(x) = (1 / (σ√(2π))) * e^(-((x-μ)² / (2σ²))). 

In this formula:

f(x)
is the probability density function, which describes the likelihood of a specific value occurring. 
x
is the value for which you're calculating the probability.
μ (mu)
is the mean of the distribution, representing the center of the bell curve. 
σ (sigma)
is the standard deviation, measuring the dispersion or spread of the data. 
e
is the base of the natural logarithm, approximately 2.71828. 
π (pi)
is the mathematical constant pi, approximately 3.14159. 

This formula is used to describe various natural phenomena and is often referred to as the "bell curve" due to its characteristic shape. 

**Example in NLP:**

In NLP, we can use the normal distribution to model continuous variables like sentence length. If we know that the average sentence in a corpus has a length of 20 words with a standard deviation of 5 words, the normal distribution helps us predict the probability of encountering a sentence of any given length.

**t-test**

The t-test compares the means of two groups to determine if they are statistically different. In NLP, we often use a t-test to analyze word or phrase frequencies between different text types.

Example in NLP: Sentiment analysis: We might use a t-test to determine if positive words appear with different frequencies in reviews for two products. This can reveal if one product's reviews are generally more positive than the other's.

**Chi-square Test**

The Chi-square test is used for categorical data to test if two variables are independent. In NLP, we might apply it to test the association between word categories and text classes (e.g., spam vs non-spam).
Examples in NLP:
Spam Detector: We can use chi-square test to determine if certain eords are strongly associated with spam emails compared to non-spam emails.
