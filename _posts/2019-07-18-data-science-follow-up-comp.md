---
title: 'Data science olympics follow-up competition'
date: 2019-07-18
permalink: /posts/2019/07/data-science-follow-up
tags:
  - data science competition
  - first place
---

I got the first place in data science olympics competition.

![data-science-follow-up](/images/data-science-follow-up-comp/leaderboard.jpeg)

Few weeks ago, the [data science olympics](https://www.datascience-olympics.com/) took place simultaneously in Paris and Berlin. It's the annually biggest data science competition in Europe and more than 1000 data scientists attended the event this year.

Competitors are challenged to build the best predictive model in 2 hours in order to predict the number of nights (4 labels, 0:0 nights, 1: 1 or 2 nights, 2: between 3 nights and 1 month, 3: more than 1 month) an emergency service can provide to an individual or a group (couple, family, ...). The data were provided by the Ministère de la Cohésion des territoires.

I discovered the competition through the winning (score 0.44060, see Fig.1) solution post of Romain AYRES. Fortunately there was a follow-up of the competition (actually 214 participants) and I joined it.
During more than one month, the follow-up competition were led by Mathurin Aché from @prevision.io with a score of 0.39467 which is an improvement of approximately 0.046 of Romain's.

The evaluation score used in this competition is a weighted log loss (the lower the better), which makes any misclassification highly penalized. For instance, the misclassification of the classes 2 and 3 are respectively penalized 100 and 1000. Hence one could get a very bad score.
From my first submission which scored 0.565 few weeks ago, I finally achieved 0.36963 yesterday which is an improvement of approximately 0.07 of Romain's score. It ranks me 1/214, see Fig.2 for the current top 8th highest scores of the competition.

I learned a lot from this competition! Feel free to [join](https://qscore.datascience-olympics.com/competitions) it (1043 days left) and beat the highest score (mine) so that the competition would be more exciting!

Congratulations to all winners of the first round competition that achieved good scores in 2h! You have to join the competition to know that it's not easy to have an improvement of the score even of 0.01.

Fig.2 Follow-up currently top 8th scores
![data-science-follow-up-2](/images/data-science-follow-up-comp/leaderboard-2.jpeg)