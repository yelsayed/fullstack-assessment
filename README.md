# News Aggregator

### Description 
This assignment has 3 parts, backend, frontend and hosting. For this assignment you have to implement an application that aggregates news from two different APIs and show them on a frontend. The APIs you'll be using are [**Reddit**](https://www.reddit.com/dev/api/ "Reddit") and [**News API**](https://newsapi.org/ "News API").

The application that you submit must have thoughtful design decisions, well documented and unit tested code. This assignment should not take more than 5 hours to complete.

### The Backend Endpoints
The two functionalities that need to be implemented are "list" and "search".

This is an example request for a generic GET request which should fulfill the "list".

```
> Request
GET /news   HTTP/1.1
Authorization: Basic QWxhZGRpbjpvcGVuIHNlc2FtZQ
Accept: application/json

> Response
[
  {
    "headline": "Human organs can be stored for three times as long in major breakthrough for transplants",  // Headline of the article
    "link": "https://www.telegraph.co.uk/science/2019/09/09/human-organs-can-stored-three-times-long-major-breakthrough/",  // Link of the article
    "source": "reddit" // Source that you retrieved this news from
  },
  {
    "headline": "Depth of Field: The Shared Memory of One World Trade Center",
    "link": "https://www.wired.com/story/one-world-trade-center-history-future/",
    "source": "newsapi"
  },
]
```

You should also implement a feature that allows someone to "search" through the news.

```
> Request
GET /news?query=bitcoin   HTTP/1.1
Authorization: Basic QWxhZGRpbjpvcGVuIHNlc2FtZQ
Accept: application/json

> Response
[
  {
    "headline": "IRS goes after cryptocurrency owners for unpaid taxes",
    "link": "https://www.cbsnews.com/news/own-bitcoin-irs-pursues-cryptocurrency-owners-for-unpaid-taxes/",
    "source": "reddit"
  },
  {
    "headline": "Skirting US sanctions, Cubans flock to cryptocurrency to shop online, send funds",
    "link": "https://www.channelnewsasia.com/news/business/skirting-us-sanctions--cubans-flock-to-cryptocurrency-to-shop-online--send-funds-11901148",
    "source": "newsapi"
  },
]
```

*Suggestion:* Try to use /r/news for Reddit and the general category for News API (you don't have to but it's worth checking out).

### The Frontend

The frontend needs to call the backend endpoints to retrieve the aggregator data and display them. How you wish to display them and in what design is up to you. The frontend needs to:

- Display the news from the aggregator backend.
- Give the ability to search using the search endpoint mentioned above.
- Clicking on article should take you to the page where you can read it.
- Give the ability to favorite a news article.
- Have a page where you can check your favorite articles.

### Constraints & Suggestions
There are some constraints that you should be aware of. Not completing any of the following constraints will stop your candidacy from moving forward:
- You must use **Node**. You can use _any_ frameworks for the backend but the frontend has to be in **React**.
- You are allowed to use any frontend UI library such as Tailwind or Ant Design.
- You are allowed to use [**PRAW**](https://praw.readthedocs.io/en/v2.1.21/) for the Reddit API.
- You cannot use any database technology to aid in your development (Redis or equivalent is fine). This is just to make it easier to evaluate your assessment.
- You must return the three fields that are in the sample requests above in JSON format. You can add more fields if you'd like.
- You must return fields from all APIs if any exist. Example: If API A and API B return something then the result of these two need to be shown in the final aggregated return. If I add API C I need to see the results of that API in the final aggregator return. If API C yields no results then you don’t have to show it.

### Assessment
Primarily, we will be assessing good **design decisions**. To do this, we have a hidden API that we have written that has different specifications than the ones that have been provided above. We will be integrating our own API into your news aggregator. It needs to be a simple and clear integration, the simpler the better.

Secondly, we will be assessing good **application performance**. The overall speed of the application should not be affected by poor API speed. You need to be creative on how to solve this problem. *Suggestion: look into LRU caches.*

Finally, we will be assessing good standards for engineering. Namely, we'll be looking at code quality, code cleanliness, testability, documentation and extendability of the code. We will also be looking at your commit history to see good Git commit practice.

### Submission
You should upload your code to a Github repository (private or public) and share it with us. Your repository should have a README.md that explains how to run the code and if you’ve done anything extra. **If you fail to produce this repository within the time period mentioned in the email you received your application will be rejected.**

Best of luck!

