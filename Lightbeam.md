# About the Case Study
Lightbeam is a Firefox plug-in extension which gives a graphical representation of the first and third-party site relationship that are active
on those pages. Lightbeam provides the in-depth visualization of tracking, including parts that remain unseen by an average user (i.e.,
trackers on the internet). Tracking, regarding web technology, can be defined as leaving a record (i.e., some amount of user data) while
you browse over the internet. This information can be processed to form a profile of the user by understanding the behavior of websurfing.
Corporations with advertising websites use this information to post relevant advertisements as per the user’s interest.

# How Lightbeam works
With Lightbeam Add-on enabled when we visit some website (often referred as First Party), the plug-in creates a real-time graphical
visualization of the all the third-party sites that are active on that page. The first party site is loading third party sites and not the user. The
Lightbeam also highlights the same third parties which are active on another website we visit. The Graphical View grows with every
website we visit and every request made from the browser. In addition to Graphical View, Lightbeam also provides a List View for indepth
analysis of individual sites.

A cookie is a small amount of data created by the websites that stores in user’s browser. It provides a way to recognize the preferences
of the user on the website and maintaining the state of the browser. Cookies can also be used for tracking.
The following is the detailed explanation of how Lightbeam creates graphical representation:
![LB1](https://s3.amazonaws.com/github-resources-apt/lb1.png)
![LB2](https://s3.amazonaws.com/github-resources-apt/lb3.png)

When a user visits a first party site for the first time, it loads the thirdparty site (some third parties can be trackers, not necessarily). The third parties create a unique user profile ID which is stored locally in the database and set a cookie that contains unique user profile ID which is sent back to the browser so that the browser can save it in user's computer. Some of the websites may include same trackers. In this case, when the user visits some another site (xyz.com), and when the same tracker request for information from xyz.com, the browser passes the stored cookie to the tracker which makes tracker recognize that the user is same. In this way, the unique ID helps tracker to keep track of the user.

Lightbeam helps to visualize the complicated tracking
* Observes the event related to cookies
* Store origins associated to the events
* Generates graph using Visualization library (D3.js)

# Real World Tracking Example
![lb3](https://s3.amazonaws.com/github-resources-apt/lb4.png)
### Fig 1. Graphical View of Tracking: Circles – Visited Site (First Party Site) with msn.com with yahoo.com, Triangles – Third Party Site

![lb4](https://s3.amazonaws.com/github-resources-apt/lb6.png)
### Fig 2. Third Party sites associated with msn.com

![lb5](https://s3.amazonaws.com/github-resources-apt/lb7.png)
### Fig 3. Third Party sites associated with msn.com

![LB6](https://s3.amazonaws.com/github-resources-apt/lb8.png)
### Fig 4. Stored Cookies in the browser

In the screenshot attached above (Refer Fig 1), the user visits two sites. Initially, the user visitsmsn.com where there are many third-party sites associated with it (E.g., ScoreCardResearch.com) (Refer Fig 1 and Fig 2). The tracker here stores the user profile by assigning unique ID to it. Then, secondly, yahoo.com was visited. Yahoo.com also has the same tracker as that of msn.com. This time, the browser passes the cookie to the third-party sites, and the known tracker gets to know that it is the same user who visited msn.com by cross-referencing the Unique ID (Refer Fig 1, Fig 3 and Fig 4). Lightbeam graph shows the similar trackers by connecting the edges.

# Unexpected Edges of the Graph
The unexpected edges of the Lightbeam graph with vertices denoted with the triangle are nothing but the Third-Party Sites. Third-Party Sites are the websites which may contain links to other website operated by third parties. Some Third Parties can be trackers.

Third Party Operators includes:
* Advertisers – By understanding the behavior of the user and posting relevant advertisements.
* Analytics – Helps the owner to get relevant statistics about the website.
* Government Surveillance – Helps government to collect information about the user as part of surveillance.

![lb9](https://s3.amazonaws.com/github-resources-apt/lb9.png)
### Fig 5. Lightbeam Tracking

# Graph when visited Directly V/s Via Search Engine (Google, Yahoo, Bing)
![lb10](https://s3.amazonaws.com/github-resources-apt/lb10.png)
### Fig 6. Directed Visited Site

![lb10](https://s3.amazonaws.com/github-resources-apt/lb11.png)
### Fig 7. Via Search Engine Google

![lb10](https://s3.amazonaws.com/github-resources-apt/lb12.png)
### Fig 8. List View of Third Party Sites

![lb10](https://s3.amazonaws.com/github-resources-apt/lb13.png)
### Fig 9. Via Search Engine Yahoo

When visited directly to website bestbuy.com, the site includes 19 third party sites denoting with triangles in Lightbeam Graphical View (Refer Fig 6). When visited using search engine – google.com, the graph creates circle vertices for visited site google.com and bestbuy.com with some additional third-parties of google (E.g., gstatic.com) (Refer Fig 7). Here, the graph differs dramatically with extra visited site vertex and newer third-party sites using search engines. It is basically because the search engine works on providing search results with website links containing the entered keywords and also, they have their analytics engine which works on behavioral search results of the user. By referring Fig 6 and Fig 7, we can say that the total number of third party sites increases as the number of steps increase, i.e., searching via search engines. Some search engine may contain third-party sites (Eg.Yahoo.com) which make the graph little different by connecting the edges with similar tracker sites (Refer Fig 9).

