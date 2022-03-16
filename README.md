<img src="images/microsoft_tenne.png" alt="tenne image" style="width: 400px;" class = "center"/>


# Microsoft's Movie Studio Vision: A Needs Analysis

**Authors**: Rebecca Frost-Brewer

## Overview

This project analyzes current trends in the movie industry to establish a vision for Microsoft's new movie studio, Microsoft Tenné. Descriptive analysis of data from IMDb, The Movie Database, and Box Office Mojo provides insight into the genre of films that have the highest audience ratings and highest gross earnings. Microsoft Tenné can use this analysis to guide their decision-making process in determining what genre of movie to produce.


## Business Problem

Microsoft sees many big companies creating original video content and want to establish their own movie studio to compete within the digital content market. 

To assist Microsoft in solving this problem, I will consider:

* What genres are the most successful, both in terms of audience rating and gross earnings?
* Of the top grossing films, which genres were most successful (had the highest gross earnings)?
* Is there a correlation between audience rating and gross earnings?


## Data Understanding

The data for this analysis have come from:

* [The Movie Database](https://www.themoviedb.org/) (movie title, audience rating)
* [IMDb](https://www.imdb.com/) (movie title, release year, genres, and audience rating)
* [Box Office Mojo](https://www.boxofficemojo.com/) (movie title, gross earnings)

The target variables for this analysis are release year, gross earnings, genres, and audience ratings. These variables are all important and necessary to address Microsoft's business problem. Audience ratings, gross earnings, and release year are numeric variables (though gross earnings is continuous) and genres are categorical. 

The data used in this analysis has been compiled from three different platforms and includes all movies these platforms monitor. Since we are providing Microsoft with recommendations for success, we can safely assume these platforms accurately account for the movies of interest.

As we consider this data however, we should note that the data includes movies from 2010 to 2018. This is noteworthy because the data does not include the most recent three years of movie-making; since movie-watching trends can shift dramatically year to year, the conclusions and recommendations presented here may change based on more recent movies.


## Data Preparation

To prepare the data for analysis, I needed to combine four individual csv files into one master file. Luckily, since we're dealing with movies and movie titles, I was able to use the titles as the key for joining the dataframes.

For the IMDb files, I did drop the 'original_title', 'runtime_minutes', and 'numvotes' columns as they are not relevant or pertinent to the business questions I am addressing.

For each of the files, I also dropped all rows that had any NaN values. I made this decision because I determined that if a movie was missing any data from these sources, that movie would not be mainstream popular nor would have gross earnings of significance. For the purposes of this analysis, I decided to focus on any movies with an average audience rating 7.0 or greater and with gross earnings greater than $3mil. Movies with NaN values would not meet those conditions, therefore could be dropped without worrying about significantly altering the analysis.

Futher, both IMDb and The Movie Database had a measure of average rating - I created a new variable that took the average of these averages, for one "master" average rating that was used in analysis. That way, the ratings from both sources were incorporated.

Lastly, I modified the gross earnings number by dividing the value by 1mil. Since the gross earnings for the movies I was analyzing are obviously more than just 1mil, I wanted the value to be more readable.

To finalize the data preparation, I created a smaller dataframe of just those movies with an average rating of 7.0 or greater and gross earnings of at least $3mil. For movies with multiple genres, I split each genre individually.


## Results

This analysis solves the stated business problem by determining what kind of movies have been the most successful - in audience rating and gross earnings - between 2010-2018. In utilizing three large datasets from industry-standard giants of IMDb, The Movie Database, and Box Office Mojo, the data is comprehensive and trustworthy.

This analysis shows the following:

* The top three genres by number of movies created: Drama (250), Comedy (102), Adventure (90)
* The top three genres by average rating: Musical (7.7), Sci-Fi (7.6), Animation (7.5)
* The top three genres by average gross earnings (in millions): Sci-Fi (251), Adventure (214), Action (207)
* There is a very weak, positive correlation between rating average and gross earnings, with a correlation coefficient of 0.0896


### Number of Movies per Genre
<img src="images/by_genre.png" alt="movies per genre" style="width: 600px;"/>

### Genres by Gross Earnings (US$ million)
<img src="images/by_earning.png" alt="earning per genre" style="width: 600px;"/>

### Gross Earnings by Genre Per Year: 2013-2018
<img src="images/by_year.png" alt="genre earning per year" style="width: 600px;"/>


## Conclusions

This analysis leads to three recommendations of what movies to produce for Microsoft's new movie studo, Tenné.

* **For successful gross earnings, Tenné should produce Sci-Fi, Adventure, and Action movies.** These three genres have demonstrated success in averaging the highest gross earnings of all genres.
* **For successful audience ratings, Tenné should produce Musical, Sci-Fi, and Animation movies**. These three genres have the highest ratings of all other genres.
* **Create Sci-Fi movies**. Between 2013 and 2018, 492 movies were produced, and only **29** of those movies were Sci-Fi. Knowing that Sci-Fi movies do well in gross earnings **and** audience ratings **and** the market is not overly saturated with Sci-Fi movies, this genre would be the most likely to be successful.


## Next Steps

Further analyses could yield additional insights to further improve Microsoft Tenné's decision-making protocol in determining what genre of movie to create.

* **Analyze more recent data from 2019-2021.** One, this would provide more current data, and two, this would incorporate the changes in viewing practices as a result of the Covid-19 pandemic. Throughout the pandemic, more people watched movies from home and movie studios did direct-to-stream releases. Pulling data from streaming services on number of streams will be highly informative in terms of what people have been watching.
* **Analyze streaming data.** As mentioned above, using data to compare ratings and earnings of traditional theatre-released movies vs. ratings and number of streams of released-to-streaming platforms will be critical as Microsoft enters the field. Are traditional theatre-released movies the most successful?
* **Analyze demographics of movie-makers and movie-watchers.** Could Microsoft become a leader in creating films by and for marginalized and underrepresented populations within the film industry - women, people of color, women of color, LGBTQIA people, multilingual films? Given the success of Black Panther, Parasite, and Roma (as just a few examples), is there a case to be made for Microsoft becoming the home for diverse movies?


## For More Information

Please review our full analysis in [our Jupyter Notebook](./dsc-phase1-project-template.ipynb) or our [presentation](./DS_Project_Presentation.pdf).

For any additional questions, please contact **Rebecca Frost-Brewer (frostbrewerr@gmail.com)**

## Repository Structure

Describe the structure of your repository and its contents, for example:

```
├── README.md                                   <- The top-level README for reviewers of this project
├── microsoft-tenne-project.ipynb               <- Narrative documentation of analysis in Jupyter notebook
├── microsoft-tenne-project-presentation.pdf    <- PDF version of project presentation
├── code
│   ├── __init__.py                             <- .py file that signals to python these folders contain packages
├── data/zippedData                             <- Both sourced externally and generated from code
└── images                                      <- Both sourced externally and generated from code
```
