# Habitable Zone Detection
## Binary Classifcation of whether exoplanet lives within the habitable zone

Author: [Rafael Ferreira](https://github.com/Astroraf)

<p align="center">
<img src="https://thumbs.gfycat.com/BaggySpottedKakarikis-mobile.mp4"> 
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

# RandomForest
# Xgboost
# LightGBM

## Findings

The first step in the project was to explore the dataset from the NASA archive. What I found was what I was expecting in terms of the type of stars that produce exoplanets and the number of planets that exist within the habitable zone. Most of the stars that are producing exoplanets are around the range from G to M type stars. The stars allow for exoplanets to easily exist and are much more suitable to allow for a habitable zone to exist for liquid water to arise. 

<p align="center"><img width="900" height="300" src=".png" alt="HR_diagram"></p> 

Another aspect of the data was finding the huge class imbalance that exist between the number of planets that live within the habitable zone, and that live outside the habitable zone. Under what we know about life, it seems reasonable to understand that there are far fewer exoplanets that live within habitable zone. Dealing with this class imbalance, I use resampling to over sample the minority class, and undersample the majority class. 

<p align="center"><img width="900" height="300" src=".png" alt="class_imb"></p> 



## Repository Structure
    
    ├── data_cleaning                     Cleaned all data, created all features, and target column          
    ├── EDA                               Created Visuals to explore the data
    ├── Modeling                          Notebook of all models attempted with GridSearchCV
    ├── images                            Images
    ├── README.md                         ReadMe
    └── presentation_deck                 Contains the presentation deck associated with this project