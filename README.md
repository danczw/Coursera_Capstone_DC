# Neighborhood likelihood - k-means clustering

**A brief comparison of neighborhoods in Hamburg and Berlin using k-means clustering - based on their venue infrastructure.**

This repository is for the final Capstone project of my IBM Data Science Professional Certification. IBM Watson Studio was used.

<br>

Scope
=====

Berlin and Hamburg are Germany's two largest cities. While Berlin is counting roughtly 3.6 million inhabitants and Hamburg roughtly 1.8 million, both cities are quite different. Berlin is filled with an eclectic mix of history, culture and gorgeous sights, it’s a city that intrigues yet embraces visitors with open arms. The city is bursting with internationality as a result of many new residents from all over the world.

<img src="./assets/berlin.jpg" alt="Berlin Brandenburger Tor" width="400"/>

Germany’s second city, Hanseatic Hamburg is both typically German and unique in its own way. With a long maritime history, this North Sea port city has a distinct feel from anywhere else in the country and tons of cool things to see and do.

<img src="./assets/hamburg.jpg" alt="Berlin Brandenburger Tor" width="400"/>

Both cities beeing in the northern part of Germany, there is a great exchange between residents of both cities. This analysis is intended to show which areas of one city resemble those of the other: Berlin and Hamburg.

This could be helpful for different use case (and different stakeholders):

* **People moving from one city to the other** often would like to live in a very specific type of neighborhood. This comparison can help those to filter for areas similar (or even different, if you are up for something new) to what you are used to.
* **Companies expanding within one of the cities** might want to look for similar type of neighborhoods, as they are targeting a specific user group. The comparison can be used for a first indication.
* **Companies expanding from one city to the other** might also try to find a neighborhood to settle in first. They can use their experience from the original city and look for a fitting (e.g. similar) neighborhood in the second one.

The comparison will be based on the structure of venues within both cities and their neighborhoods. For example, imagine you are living in a rather hip Berlin area with many smaller restaurants, open parks for recreation and some secluded bars in between. Now moving to Hamburg you are looking for that same feeling and therefore wonder which neighborhoods may be fitting. The venue structure within smaller areas will give a first indication of what the neighborhood atmosphere is like.

<br>

Data
=====

Two different kind of data is needed for the comparison.

1. **City neighborhood and respective geographical data:** in order to analyse the cities on a meaningfull level, they need to be divided into differen areas, e.g. neighborhoods, boroughs. Luckily both is available as a Github repro and can be found [here](https://github.com/zauberware/postal-codes-json-xml-csv). This data includes 11 rows, of which only state (i.e. Berlin or Hamburg), ZIP-code (10 for Berlin, 22 for Hamburg), latitude and longitude per ZIP-code will be needed. ZIP-codes will be used for dividing both cities into smaller areas. ZIP-code is chosen as it is an unique identifier. In the following this data is cleaned and filtered to what is needed.

2. **Venue and respective geographical data:** The first 100 venues per ZIP-code in both Hamburg and Berlin are scraped in order to cluster the different areas. This data, including the Venue name, its category, latitude and longitude, is gathered using the Foursquare API. 