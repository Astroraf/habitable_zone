# Habitable Zone Detection
## Binary Classifcation of whether exoplanet lives within the habitable zone

Author: [Rafael Ferreira](https://github.com/Astroraf)

<p align="center">
<img src="https://thumbs.gfycat.com/BaggySpottedKakarikis.webp"> 
</p>

## <span style="color: deepskyblue;">Overview </span>
As the field of astronomy and astrophysics progresses, so does the instrumentation that these scientist are using. Over the course of 25 years, we have disovered upwards to 4,000 known exoplanets orbiting other stars within the Milky Way Galaxy. The means of detection varies from instrument to instrument, with the most common detection techniques being the transit method, when the planet goes in front of its host star, showing a dip in brightness over a period of time. Radial Velocity, uses the host star slight movement caused by the push and pull of the exoplanet(s) that orbit the star. The last well known dection is imaging, but is not widely until we have better instrumentation like the James Webb Telescope, yet to be realeased into space. When using any of these three techniques, the main focus is detecting what stars live within the habitable zone. That is where liquid water can exist at temperatures between 273 K, the freezing point of water, and 373 K, the boiling point of water. Where liquid water or the habitable zone exist in other solar systems all depends on the type of star the system has. The more luminous stars have habitable zones that are push far out then compared to stars with lower lumnosities. My sole focus is determing wether the exoplanets that where discovered and archive in the NASA database fall within the habitable zone. Once the planets are determined to live within the habvitable zone, more research can be done if these planets are terrestial or gaseous planets, with the potential of humans exploring these exoplanets one day for humans to live. 

[Source](https://exoplanetarchive.ipac.caltech.edu/cgi-bin/TblView/nph-tblView?app=ExoTbls&config=PSCompPars)

<p align="center">
<img src="http://planetbteam.com/wp-content/uploads/2020/03/EssentialCreamyClumber-small.gif"> 
</p>

## Approach 

### Habitable Zone 

1. **Cleaning and Preprocessing:** Handled all missing information for the characteristics of the host stars and exoplanets, dropped unneeded/unsuable columns, and prepared models in ways necessary for modeling. 

2. **Exploratory Data Analysis:** Database was cleaned, then features created to create a plethora of visuals in order to better understand the distribution of host stars, types of exoplanets, and the class imbalance that occurs between planets that are within the habitable zone. 

3. **Modeling:** Tested several classification models to find the best best option for the NASA dataset

4. **Evaluation:** Evaluated the models test for the best results and made a determination about each finding. 

### Models Tested:

> * RandomForest
> * Xgboost
> * LightGBM

## Findings

The first step in the project was to explore the dataset from the NASA archive. What I found was what I was expecting in terms of the type of stars that produce exoplanets and the number of planets that exist within the habitable zone. Most of the stars that are producing exoplanets are around the range from G to M type stars. The stars allow for exoplanets to easily exist and are much more suitable to allow for a habitable zone to exist for liquid water to arise. 

<p align="center"><img width="500" height="300" src="/kepler-confirmed-planets/images/HR_diagram.png" alt="HR_diagram"></p> 

Another aspect of the data was finding the huge class imbalance that exist between the number of exoplanets that live within the habitable zone, and that live outside their habitable zone. Under what we know about life, it seems reasonable to understand that there are far fewer exoplanets that live within habitable zone. Dealing with this class imbalance, I use resampling to over sample the minority class, and undersample the majority class. 

<p align="center"><img width="500" height="300" src="/kepler-confirmed-planets/images/Class_Imbalance.png" alt="class_imb"></p> 

After dealing with several models, with various different parameters, I settled on _______ as the best model for predicting if an exoplanet lives within the habitable zone. I evaluated each model on the F1 score, the balance between precision and recall of each model. I want my model to be as precise as possible when predicting if an exoplonet lives within the habitable zone, and as sensitive to exoplanets that live just outside the habitable zone.

## Conclusion

With what we know how scarce life is, being that we are the only known planet to have life on it, it is reasonable to realize that fewer planets that we disover will be within the habitable zone. This is not to say it is highly improbable. Life can come in many forms, through the smallest single celled eukaryotes, from four legged 'animals', to sentient beings. As time goes on, our instrumentation becoming more safisticated, the number of exoplanets will increase drastically, and with that, many more exoplanets living within the habitable zone. The search for our next home, the search for an exoplanet with life, has just began. Creating a model to properly identify exoplanets living within their habitable zone will let humanitiy focus on the exoplanets that will either lead to our next home, or let us know that we are not alone. 

## Future Steps
My next steps for this classification project would to consider the albedo affect ont he each exoplanet, that is the anount of radiation that is asbored and reflected by each exoplanet. This allows for certain areas on the exoplanet to allow for liquid water to exist, where other areas are far to hot or cold for liquid water to exist. Another step is to gather over 20,000 observations of exoplanets to then use Neural Networks to make the best possible predictions on exoplanets living within the habitable zone. 

## Sources
1. [Data](https://exoplanetarchive.ipac.caltech.edu/cgi-bin/TblView/nph-tblView?app=ExoTbls&config=PSCompPars)
2. [Spec Type Temps](https://sites.uni.edu/morgans/astro/course/Notes/section2/spectraltemps.html)
3. [Habitable Zone](https://www.planetarybiology.com/calculating_habitable_zone.html)
4. [Feature Description](https://exoplanetarchive.ipac.caltech.edu/docs/API_exoplanet_columns.html)
5. [Stellar Radius](https://www.enchantedlearning.com/subjects/astronomy/stars/startypes.shtml)
6. [Luminosity Equation](http://www.astronomy.ohio-state.edu/~thompson/1144/Lecture9.html#:~:text=L%20%3D%20F%20x%20Area%20%3D%204,2%20%CF%83SB%20T4&text=%22%20The%20Luminosity%20of%20a%20star,power%20and%20its%20Radius%20squared.%22)
7. [Kepler Equation](https://www.vanderbilt.edu/AnS/physics/astrocourses/ast201/keplerslaws_3.html)
8. [Habitable Zone Paper](https://www.astro.umd.edu/~miller/teaching/astr380f09/lecture14.pdf)
9. [Host Stars Database](http://www.exoplanetkyoto.org/exohtml/A_All_HostStars.html)

## Repository Structure
    
    ├── Notebooks ├── data_cleaning                     Cleaned all data, created all features, and target column                           
                  ├── EDA                               Created Visuals to explore the data
                  ├── Modeling                          Notebook of all models attempted with GridSearchCV
    ├── images                                          Images
    ├── README.md                                       ReadMe
    └── presentation_deck                               Contains the presentation deck associated with this project
