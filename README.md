# Targeting Power-Middle Influencers


## with graph analysis and sentiment analysis

Check out the source code for this project [here](https://github.com/sdmirch/instagram-influencer-graph).

### tl;dr
I identified the top power-middle influencers on Instagram using graph and sentiment analysis. Power-middle influencers have a devoted following and tend to have a higher interaction rate with their followers, and therefore can make more authentic and affordable endorsements of niche products.


{% include ForceGraphEx.html %}

<img style="float: left;" src="images/DegreeEigenvector_presentation.png">
<img style="float: right;" src="images/DegreeEigenvector_presentation.png">



## Top Influencers
-  Critical Mass Filter: Must have more than 5000 followers.

- Influence Score: Eigenvector centrality.

![Network Eigenvector Centrality](images/DegreeEigenvector_presentation.png)

- Interaction Score: Ratio of likes to followers.

![Likes and Follows within network](images/LikesExampleNetwork.png)


- Authenticity Score: Inversely proportional to positive sentiment in captions.

```
text = """I finally SENT my project today wooohoooo! 🎊The technical crux of the 2nd pitch of "The Kill Artist" was an airy 5.13a invert move out the roof of an enormous chimney. But the mental crux was the real hurdle for me."""
analyzer = SentimentIntensityAnalyzer()
vs = analyzer.polarity_scores(text)
print("{:-<65} {}".format(text, str(vs)))
```
