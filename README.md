## Lab 1 description

Here's the public dashboard https://idguafi.github.io/mlfs-book/air-quality/


## NOTE:

You will need an aqicn, and hopsworks api key to be able to run these notebooks. 

See requirements document for required packages. 

We aimed for an A grade and implemented the various models and pipelines as described in the lab description. For the C-level task, we implemented a model with and without lagged features. We utilised the versioning system in hopsworks for this. For the A-level task, we re-did the entire pipleine in a different branch so that we can show you both branches during the presentation. This required quite a lot of rewrites since everything was hardcoded for a single sensor previously. The system is now robust and can handle both single and multi sensor inference. You can see forecasts and hindcasts in the link. 

Under notebooks/airquality you will find five notebooks, four of which are relevant to the task at hand. 

We'll describe each of them below: 

Notebook 1: Mainly takes care of feature engineering, data cleaning, and creates all the feature groups in hopsworks. The latter are then backfilled with historical pm25 and weather data. This is supposed to be run once (however, once can run it as much as they like)

Notebook 2: This notebook - as its name describes - is the daily feature pipeline that downloads and ingests new data into our feature store(s) every day. The new weather data is then used in inference later on.  Lagged features are computed when pm25 is fetched and is later used as well. 

Notebook 3: Here we train and evaluate our model(s) and deploy them to hopsworks. This makes use of the backfilled data from NB1. Worth noting that in the A-level version of this lab, we train one 'expert' model per sensor in the city of birmingham, which is then used to make forcasts for each sensor in notebook 4. 

Notebook 4: This is another daily notebook that is used in the Actions. This notebook will make use of our features and data provided from the previous steps to make predictions/forecasts about the air quality. This is then plotted, saved, and displayed in our github page (link above).

Authored by Joel Maharena and Sam Barati





