# IS and the Western Journalism: a media hype; a self-reinforcing news process; or ‘just news’?
Judith Niks - 10631534

Beate Ancevska - 11364920

Annabel Burger - 11042249

Wietske Dotinga - 10781889

### Introduction to the subject
The past two years the Western news has been reporting considerably more about Isis. Knowing that Isis wants to get attention with Western society - so they can spread fear - we started wondering if they somehow manage to influence Western Journalism, and thereby get the attention they are looking for. 

Peter Vasterman and Stefan Geiß separately wrote about these phenomena whereby Key Events turn into Media Hypes. Because the West is a well connected society this Media Hype can eventually cause the key event to continually reoccur whenever a topic related to the issue comes up in the news. This phenomenon is called a news wave and has certain patterns. These patterns can show over a period of time how much influence a key event has on the coverage of the issue and the issues they are related to. It will eventually give an insight to the intensity of the related issues that are spoken of in the mass Media, and if the key event influences the way journalism covers the news.

In our case these key events will be the Terror Attacks by Isis in Europe from the past two years. And the related issues: Isis itself. By searching the databases of two liberal western Newspapers and asking the following question “What is the pattern of IS related terms (‘Isis, Islamic State or Daesh) in the printed articles of the NRC Handelsblad and New York Times surrounding the dates of the terroristic attacks in Europe (in chronological order: Charlie hebdo, Paris Bataclan, Zaventem (Brussels), Nice)?” we tried to find a pattern that could tell us more about the news wave phenomenon in relation to Isis. 

Did Western Journalism - and in our case the journalists of two liberal and Western Newspapers - start publishing more articles about Isis after each attack? And if they did so, does it show patterns we can compare to the news waves Vasterman and Geiß talk about? Because if it does we could suggest that Isis does have influence on the western journalism and thereby get the attention they are looking for.  

### Approach 
Our research called for three main steps: acquiring the datasets - which were articles that mentioned one or more of the three Isis related terms published in the weeks following each attack - refining and arranging the data and visualizing it. During the process we encountered several obstacles that made us slightly change our approach. Below, we discuss the steps taken in detail. 
####Acquiring the data 
When attempting to acquire the articles which mentioned the terms related to Isis and corresponded with the attack dates, we decided to use articles. The NRC website didn’t have an API, so we went on with our search by choosing to work with two different way to obtain the printed articles - Using NYT API developer’s network, or accessing the NRC Handelsblad articles through the LexisNexis database. 
#####NYT API approach:
First, we defined the search parameters like the time period of search, the search keywords to obtain data about the corresponding NYT articles. Here’s the url used to obtain these results for the first attack: (api.nytimes.com/svc/search/v2/articlesearch.json?q="isis"&begin_date=20150107&end_date=20150114&sort=oldest&&api-key=de5331e71c6f47188a9b8238820490ab)

The data obtained was in json format, so we used online converter to produce the results in .csv, which we could later open with RStudio. After converting the data, we noticed that the search only produced the first 10 article entries from the corresponding dates. To obtain the full result for the NYT newspaper, we pursued with using the LexisNexis database for both newspapers in question. 
#####Lexis Nexis approach: 
Using LexisNexis (https://academic.lexisnexis.nl/) we were able to obtain the complete datasets for all the dates we were interested in. But it did take a while before we found out which searchterms to use. Because the term ‘IS’ was an invalid searchterm (because it corresponded with the verb ‘is’) we decided to replace it by the term ‘Daesh’. The final search terms became:
* Isis OR Islamic State OR Daesh (for the New York Times)
* Isis OR Islamitische Staat OR Daesh (for the NRC Handelsblad)

Beside this encounter we also had to solve the problem that NRC doesn’t publish on Sunday and the New York Times did. We decided to disinclude NRC’s “zero sunday” and take this into consideration while comparing the results. After completing the search we had to download the data for the days individually. We did this in a TSV format and imported them by hand into RStudio to complete our dataset. 

####Refining and arranging the data 
After downloading the data from the archive we used RStudio to refine it. We used three scripts to refine the data. We first used a script to merge the datasets of the 7 days of articles for each attack. This formed 8 different datasets with information about all the articles on the day of the attack and the 6 days after (excluding Sundays for NRC Handelsblad). After the merging of datasets two were not in the right date order. We used the console in RStudio to order these two datasets by date.

The second script we used was to count the amount of articles written on each date. After this we still had 8 datasets, but these datasets contained the information we needed instead of unnecessary information about the articles itself. We had 4 datasets for each newspaper and merged those using a script to merge datasets by columns. We renamed the columns by using the console in RStudio and used these two final datasets to visualise our data.
####Visualizing the data 
When we finally acquired our datasets Annabel started testing visualizations. The first thing we encountered was that the line graphs we wanted to make wouldn’t show. With the plot function in R together with the xlab and ylab codes we kept getting a bar graph. We kept trying different X and Y codes that we’re in our CSV file but it wouldn’t run the way we wanted it to. We then realised we needed a different table to fill in the R code to plot. So we changed the original CSV file to something different whereby we thought it would be easier to plot. When the tables were sorted in the right way we plotted eight graphs all for the individual attacks and the different newspapers. 

We then created two new datasets to plot one graph of the amount of articles for all four attacks together for each newspaper. We used the googleVis library in R to create these two interactive graphs of the datasets, so it would be easy to look at the exact amount of articles for each attack on each day. When we had the two interactive graphs we decided we no longer needed the individual graphs, because the interactive graphs where enough. 

###Results 

###Analysis & interpretation of the results  
Our found data created a slightly different visualization than we at first expected. After having plotted all the data, we could almost immediately tell that comparing both newspapers wasn’t part of the deal anymore. The graphs showed us big of a difference in the numbers of published articles between the newspapers. Where the NRC Handelsblad barely published an average of 3 to 4 per day, the New York Times manage to publish 28 at one single weekday. Beside the differences in the amount of published articles, we could also see a difference in the graphs itself, so we decided to analysis both newspapers separately.

The New York Times didn’t show any kind of wavy activities at first sight and after some more researching and comparing it with the used theories we were sure to conclude that our results on the New York Times didn’t even suggest that there could be a dimple in the way they cover Isis related news surrounding the dates of the Isis attacks in Europe. Thinking it through, we weren’t even that surprised by the results of the New York Times after all, because considering the American history and their committed roll in the war on terror, it seems quite possible that on a daily basis reporting on terror made American Journalism less vulnerable for the Media Hypes Isis created by attacking Europe. Looking back at our approach, it maybe could have showed us more if we took 2, 3 or 4 weeks of data per attack.

The NRC Handelsblad on the other hand showed us enough to at least suggest an evidence for news waves. In the week after each attack you could clearly see an increase in published stories. After one or two peaks it would go down again, which is called ‘short coverage’. Because this seems to happen after every attack for the past two years now it looks like the NRC Handelsblad has a degressive firestorm news wave. This kind of news wave is marked by a long term wavy activity with high peaks and commonly found by larger news topics which are for a longer period of time in the news and occasionally escalate. According to our findings and the theory of Vasterman this should suggest that the Isis attacks indeed have influence on the intensity the NRC published about the issues surrounding Isis.

Overall we think that both newspapers should be compared with their own articles published about Isis in a calmer week instead of each other, considering their different ways of covering the stories. Besides that, we think that news waves caused by the Isis attacks in Europe could be shown in a week after the attack already. This might suggest that a new journalistic approach of story coverage is needed to make sure we won’t give Isis more attention than is exactly needed in the near future.

###Individual reflections 
#####Annabel:
What I mostly leant during this period is that one can do great things with just a couple codes. This class and the lessons gave me much more confidence in my computer and coding skills. I became very fond of RStudio as a place to run codes and work on things. I noticed that I found command line very hard and frustrating. Why RStudio was so great is that it was very clear and things just mostly went right. Further regarding the research, it was really enjoyable to be able to work in a group. Everyone had their strengths but still helped each other with everything, a critical eye was very useful. I spent the most time plotting the graphs for the visualization of our project in RStudio, which was actually very gratifying seeing your work visualized. I learnt many skills during this period and even more useful many programs to make it a bit easier. I found this class enjoyable and usefull.

#####Judith: 
Starting this class I already knew that I was interested in coding and scripting. This summer I taught myself some basic coding skills for web design, but using codes for data based research taught me the importance of well formulated research questions and determination to pursue them. Trial and error in coding and constantly rethinking your research strategy is exhausting and sometimes even demotivating. Having to change your research proposal that got you motivated to begin with is hard. However, it did make me realize the benefits of working in a group where people have different skills. Daring to try codes, ask questions and debate about your approach in this group composition was a great learning experience, because it taught me that my theoretical point of view isn’t always in line with the actual possibilities of data based research. I eventually spent most of my time learning to understand what was possible by trying codes and understanding what others were doing to make sure that our research proposal would be in line with the aforementioned possibilities. Considering the overall lack of experiences of our group doing data based research, I think we came a long way.
#####Wietske:
This class gave me an insight on how to use code to research data. I had programming experience before starting this class, but I had never used it to do research before. Trying to use scripts in R showed me what the possibilities are of using code to manipulate big datasets or multiple datasets easily. I found that working in a group with someone else’s research questions can be very helpful in looking at data in a different way. It forces you to work with the research question itself and not think about the available datasets first. This class also taught me about the limitations of data-based research. It showed me the limitations of using certain datasets to answer research questions and how to work with the data that is available to you. Through the use of trial and error we managed to answer our research question. 
#####Beate: 
While making me want to cry at some points and laugh at another, this project demonstrated to me how much we can do through searching, trying things out and experimenting. This was a great bunch of knowledge to receive in the period leading up to Bachelor thesis. I gained insights in the processes of data research and I believe I managed to work out enough material to make me want to come back to this type of methods again. I know how to download the data I need, how to perform functions on that data and produce results. And while the method can only be applied to particular questions, it opens the understanding of how much information there is, and how valuable it can be. 
      For getting the project together, the input of each of us was very valuable, because when it comes to trial and error, it’s good to have a lot of both. Our team of beginners each proved to themselves that multiple errors might lead to better answers. Exploring different options and sharing results was our approach to the project. And this approach will make the next times easier and more effective. 

###Appendix
                                           
    Geiß, S. The Shape of News Waves. How the Intensity of Coverage of News Events Develops over Time. Paper for the conference of the Association for Public Opinion Research (WAPOR) in Chicago. Mainz: Johannes Gutenberg-Universität, 2010. 
                
    Vasterman, Peter. ‘Mediahype, de turbo van de nieuwsvoorziening. Kenmerken van zelfversterkende processen in het nieuws.’ In: Jo Bardoel en Huub Wijfjes (red.) Journalistieke cultuur in Nederland. Amsterdam: Amsterdam University Press, 2015.
                                       
    Vasterman, P. ‘Media-Hype. Self-reinforcing News Waves, Journalistic Standards and the Construction of Social Problems.’ European Journal of Communication 20.4. (2005): 508-530. 
                                           
    Wien, C., & Elmelund-Praesteker, C. An Anatomy of Media Hypes: Developing a Model for the Dynamics and Structure of Intense Media Coverage of Single Issues. European Journal of Communication. 24.2. (2009): 183-201. 
                
            
        

            
        









