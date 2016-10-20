# Research proposal
Judith Niks - 10631534

Beate Ancevska - 11364920

Annabel Burger - 11042249

Wietske Dotinga - 10781889

### Research theme: 
IS and the western journalism; a media hype; a self-reinforcing news process; or “just news”?

### Questions:
1.	What is a ‘media hype’ and a ‘self-reinforcing news process’?
> This is an interesting question, but is it one you can answer through analysis? 
> I would see this as a point of clarification, for your analysis, rather than a research question.

2.	What is the pattern of IS related terms (IS; Isis; Islamic State) on the websites of the NRC Handelsblad and New York Times surrounding the dates of the terroristic attacks in Europe (in chronological order: Charlie hebdo, Paris Bataclan, Zaventem, Nice)?
3.	Does one of Stefan Geiss’ types of a ‘news wave’ fit the found pattern? 
> These are both really good questions :+1

### Methodology:
1.	Defining the search terms: we chose to work with article keywords "Isis", "IS", "Islamic State" and the corresponding term used in the East: "daesh";
2.	Obtaining the articles corresponding to the three chosen time periods (of three different attacks carried by ISIS) using NYT API, and LexisNexis archive for the NRC Handelsblad (running command line);
> I like that you have used more than one dataset. It gives more credence to your analysis.

3. Refining and organizing data using R Studio, arranging the articles corresponding to the publication date and comparing it to Geiss's News Waves theory;
4. Using regular expressions, exploring the articles further for any additional conclusionsons on the Western news coverage of the three attacks;
5. Visualising the different findings using R Studio.

> This is all fine.

### Hypothesis:
We chose NRC Handelsblad and New York Times, because they are both liberal, western newspapers. The difference is: one is set in the EU and one in the USA, so there is a difference in the relative geographical distance to the attacks. This might influence coverage on the matter and thereby the form of ‘news waves’ in both newspapers.  
We think the data analysis on both these newspapers will uncover the way IS related news becomes a media hype in one or both of the newspapers and that the news wave pattern in the EU will be more intense than in the USA before “other” (non-related IS) news will takeover. 
This may strengthen assumptions like: IS really does have influence on our journalism, so they do get what they wish for; attention. 
> good.

### Dataset:
We will use articles from the New York Times and NRC Handelsblad. The New York Times has an API that lets you download the articles, which we will use to download the articles from the selected dates. 
NRC Handelsblad doesn't have an API, but their archive is available on Lexis Nexis. We will use the Lexis Nexis tools to select the articles from the dates we want. We can download these articles in different file formats from their website. This can not be done by an API, but the website is easy to use and the articles can be downloaded fairly quickly.
> good.

### Visualization:
We will create a line graph to support the findings from our data set. The line graph will be visualized using R and RStudio.
In our first line graph we will visualize the amount of articles written a week after the attacks from ISIS. We are looking four attacks in total. In our second graph we will visualize if these articles refer to prior attacks. We will also make a third conclusive graph that puts all outr data together as conclusion. 
> A line graph may work fine, then you have no problem. However, don't feel you have to stick to the line graph if it is not offering you the visualisation you need. Feel free to shift if needed.

