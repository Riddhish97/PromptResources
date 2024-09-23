## Inferring

In this lesson, you'll learn how to infer sentiment and identify topics from feedback provided for software products and tech-related news.

### Product Feedback

Consider the following product feedback on a software tool:

I recently purchased a project management software, and overall I'm happy with its features. The interface is clean, and the tools it offers fit my team’s needs perfectly. However, there were some issues with the initial setup, and I had to contact customer support. Fortunately, they were very responsive and resolved the issues quickly. It's a solid product, but it could use a more user-friendly onboarding process.

#### Inferring Sentiment

You can infer whether the sentiment of the review is positive, neutral, or negative based on the writer’s overall tone and word choice.

```
Prompt:
What is the sentiment of the following product review?

Review: '''I recently purchased a project management software, and overall I'm happy with its features. The interface is clean, and the tools it offers fit my team’s needs perfectly. However, there were some issues with the initial setup, and I had to contact customer support. Fortunately, they were very responsive and resolved the issues quickly. It's a solid product, but it could use a more user-friendly onboarding process.'''
```

Expected Response: Positive

#### Inferring Emotions

In addition to sentiment, you can identify specific emotions expressed in the review.

```
Prompt:
Identify the emotions expressed in the following product review. List no more than five emotions.

Review: '''I recently purchased a project management software, and overall I'm happy with its features. The interface is clean, and the tools it offers fit my team’s needs perfectly. However, there were some issues with the initial setup, and I had to contact customer support. Fortunately, they were very responsive and resolved the issues quickly. It's a solid product, but it could use a more user-friendly onboarding process.'''
```

Expected Response: satisfaction, frustration, relief, appreciation

#### Identifying Frustration

If you want to specifically check if the reviewer expressed frustration or dissatisfaction, you can use a more focused prompt.

```
Prompt:
Does the reviewer express frustration in the following feedback?

Review: '''I recently purchased a project management software, and overall I'm happy with its features. The interface is clean, and the tools it offers fit my team’s needs perfectly. However, there were some issues with the initial setup, and I had to contact customer support. Fortunately, they were very responsive and resolved the issues quickly. It's a solid product, but it could use a more user-friendly onboarding process.'''
```

Expected Response: Yes

#### Extracting Key Information

To gather key details from the feedback, such as the product or company name, use this approach.

```
Prompt:
Identify the following items from the review text:

Name of the product purchased
Company that provided the product
Review: '''I recently purchased a project management software, and overall I'm happy with its features. The interface is clean, and the tools it offers fit my team’s needs perfectly. However, there were some issues with the initial setup, and I had to contact customer support. Fortunately, they were very responsive and resolved the issues quickly. It's a solid product, but it could use a more user-friendly onboarding process.'''
```

Expected Response:
{ "Product": "project management software", "Company": "unknown" }

#### Handling Multiple Tasks at Once

To handle more than one inference in a single prompt, you can extract sentiment, detect frustration, and retrieve product information at the same time.

```
Prompt:
Identify the following from the review text:

Overall sentiment (positive or negative)
Is the reviewer expressing frustration? (true or false)
Product name
Company name
Review: '''I recently purchased a project management software, and overall I'm happy with its features. The interface is clean, and the tools it offers fit my team’s needs perfectly. However, there were some issues with the initial setup, and I had to contact customer support. Fortunately, they were very responsive and resolved the issues quickly. It's a solid product, but it could use a more user-friendly onboarding process.'''

```

Expected Response:
{ "Sentiment": "positive", "Frustration": true, "Product": "project management software", "Company": "unknown" }

### Inferring Topics

Consider the following news article:
In a recent report published by the National Technology Council, it was revealed that tech industry wages have steadily increased over the past five years. The report highlighted that software engineers and data scientists have seen the largest wage growth, with many companies expanding their workforce to keep up with the demand for digital innovation. However, there were concerns about the widening wage gap between tech professionals and those in non-tech roles. The Council proposed several recommendations to address these disparities, including better training programs and increased investment in non-tech sectors.

#### Identifying Topics

You can identify key topics discussed in the news article by analyzing the text.

```
Prompt:
Determine five topics being discussed in the following article:

Article: '''In a recent report published by the National Technology Council, it was revealed that tech industry wages have steadily increased over the past five years. The report highlighted that software engineers and data scientists have seen the largest wage growth, with many companies expanding their workforce to keep up with the demand for digital innovation. However, there were concerns about the widening wage gap between tech professionals and those in non-tech roles. The Council proposed several recommendations to address these disparities, including better training programs and increased investment in non-tech sectors.'''
```

Expected Response: wages, tech industry, workforce, wage gap, training

#### Creating a News Alert

You can create a system that alerts when specific topics are mentioned in the article.

```
Prompt:
From the following list of topics, determine if each is discussed in the article below. Return 1 if discussed, and 0 if not.

Topics: wages, tech industry, healthcare, education, workforce

Article: '''In a recent report published by the National Technology Council, it was revealed that tech industry wages have steadily increased over the past five years. The report highlighted that software engineers and data scientists have seen the largest wage growth, with many companies expanding their workforce to keep up with the demand for digital innovation. However, there were concerns about the widening wage gap between tech professionals and those in non-tech roles. The Council proposed several recommendations to address these disparities, including better training programs and increased investment in non-tech sectors.'''
```

Expected Response:
{ "wages": 1, "tech industry": 1, "healthcare": 0, "education": 0, "workforce": 1 }
