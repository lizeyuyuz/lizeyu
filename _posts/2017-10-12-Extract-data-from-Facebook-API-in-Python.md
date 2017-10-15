---
layout: post
title: "Extract data from Facebook API in Python"
author: "Zoey Li"
categories: journal
tags: [python, api, web-scraping]
---

We are going to look at how to scrape comments on wall street journal Facebook
page using Facebook API in Python.

First, get your access token from [here](https://developers.facebook.com/docs/facebook-login/access-tokens#apptokens)

```python
# set up access token
app_id = "1503542683084"
app_secret = "64c53a604d723174f1f0826dc8bfa9" # DO NOT SHARE WITH ANYONE!
access_token = app_id + "|" + app_secret
page_id = 'wsj'
```
Import these modules:

```python
# import modules
import requests
import json
```
If you read Facebook API docs [here](https://developers.facebook.com/docs/graph-api/using-graph-api) and play around with the [Graph API explorer](https://developers.facebook.com/tools-and-support/) a bit, you should see how it works.

- To get all the comments including the nested ones, use `filter=stream`.

- To get comments within a specific period, use
  `created_time&until=2017-10-05&since2017-10-10`. Note that the `until` date
is excluded. This will include only comments from 10-04 to 10-10 inclusive. 

- To set the number of comments you get for every request, use `limit=25`. 25
  is the default number. You can go a little higher, but there's an upper
limit around 500 for comments or 100 for posts (the numbers need to be
verified, haven't found official maxima). The default is fairly easy to work
with. Say if there are 12000 comments in total, then the api will give you 25
comments a time, and `12000/25` pages of comments. So you need to make use of
the `next` key. 

- Somehow the API returns an empty json at the end, using
  `order=reverse_chronological` avoids this problem.


```python
# scrape comments

comments_scraped = []

res = requests.get('https://graph.facebook.com/v2.10/{}/posts?fields=created_time&until=2017-10-05&since=2017-10-10&limit=25&access_token={}'.format(page_id, access_token))

for post in re.json()['data']:
    post_id = post['id']
    cres = requests.get('https://graph.facebook.com/v2.10/{}/comments?limit=25&order=reverse_chronological&filter=stream&access_token={}'.format(post_id, access_token))
    while 'paging' in cres.json():
        for comment in cres.json()['data']:
            comments_scraped.append([post_id, comment['id'], comment['message']])
        if 'next' in cres.json()['paging']:
            cres = requests.get(cres.json()['paging']['next'])
        else:
            break
```

