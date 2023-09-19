# BreedMinds Data Model

## Abstract: 
In an age where pets have become cherished companions, the ability to accurately identify and understand the breeds of animals holds significant importance. This project trains a model that is designed to predict the breeds of animals by harnessing machine learning models. The primary aim of this application is to empower pet owners, animal enthusiasts, and shelter volunteers with a tool that offers quick and reliable insights into the diverse world of animal breeds.This project represents a convergence of technology and animal welfare, offering a valuable resource to pet owners, animal shelters, and individuals curious about the diverse world of animal breeds. 

## Introduction: 
In today's world, the bonds between humans and their animal companions have grown deeper and more profound than ever before. The diverse array of animal breeds, each with its unique set of characteristics and care requirements, presents both pet owners and animal enthusiasts with an ever-enticing tapestry to explore. Accurate breed identification not only aids in understanding an animal's lineage but also facilitates informed decisions regarding their health, behavior, and overall well-being. Our mission is to provide a swift and reliable means of predicting animal breeds, enabling users to gain quick insights into the unique characteristics and care requirements associated with each breed. As we embark on this journey at the intersection of technology and animal welfare, our commitment is not only to create a valuable resource but to continually refine and adapt it in response to user feedback. We envision a world where every pet owner and animal enthusiast can readily access the diverse world of animal breeds, forging stronger bonds and providing the best possible care for their beloved companions. This project stands as a testament to our dedication to both technological innovation and the well-being of the animals we hold dear. It is an invitation to explore, understand, and cherish the world of animal breeds, one prediction at a time. 

## Literary Review
The Louisville_Metro_KY_-_Animal_Service_Intake_and_Outcome.csv dataset is taken from [Louisville Metro Open Data](https://data.louisvilleky.gov/datasets/LOJIC::louisville-metro-ky-animal-service-intake-and-outcome/about) page. This is a set of data that recorded by Animal Services in Louisville Metro KY. It recorded all instances of animals brought into Animal Services with outcomes from 2019 to 2022. There are many different column in this dataset, but in this model we will only focus on some certain column, which is intype, outtype, animaltype, sex, bites, petsize, color, and breed. In this dataset, some specific words are used, hereby is the data dictionary for those words. 

1. intake type/intake subtype - The reason why the animal was impounded.
   * ABANDONED: Animal was impounded because of a violation of the Abandonment ordinance
   * DISPOSAL: The animal was brought to the shelter deceased to be properly disposed
   * FIELD: An animal control officer picks up a deceased animal while outside the shelter.
   * OWNER: A owner turns in their deceased animal
   * STRAY: A deceased unowned animal is brought in to MAS by a citizen.
   * OTC: The animal was impounded at the shelter due to the owner being evacuated due to a natural disaster
   * FOSTER: When a foster returns an animal to MAS to go up for adoption
   * RETURN: When a foster returns an animal to MAS to go up for adoption

2. animal type - Type of animal impounded
3. sex - The sex of the animal
   * M: Male
   * F: Female
   * N: Neutered
   * S: Spayed
   * U: Unknown
4. Bites - Does the animal have a bite reported to MAS
   * Y: Yes
   * N: No
5. pet size - The size of the animal impounded in relation to the animal type
6. color - The color of the animal
7. breed - The breed of the animal

## Methodology
#### This project is developing by using Cross-industry Standard Process for Data Mining (CRISP DM) method. 
![CRISP DM methodology](https://github.com/AaronTeah/codeless-data-science-fundamental-2023-FTU-x-UMK/assets/69444412/a5ae399b-0829-495c-9f66-45295f846685)

### Business Understanding
This project is developing by using Cross-industry Standard Process for Data Mining (CRISP DM) method. Our project is tend to develop a data model that can be predict the breed of animal by using the intype, outype, animaltype, sex, bites, petsize, and color data to recognize the breed of animals. This model can be used in every veterinary clinic to help them define the breed of the animal. It also can be implemented in apps that help people to recognize the breed of an animal.

### Data Understanding: 
The Louisville_Metro_KY_-_Animal_Service_Intake_and_Outcome.csv dataset recorded a list of all instances of animals brought into Animal Services with outcomes in Louisville Metro KY. This is the source data for the number of animals taken in by Animal Services and the number of animals transferred out of Animal Services. To understand the data, every field for the column are needed to read. First, the csv data is imported by using the CSV Reader. Through the data prompted this dataset have 50900 rows and 18 column, but there are a lot of missing value in the dataset. To get the accuracy result, the cleaning process is needed. In this section, Pie Chart components also used to know how many category and the percentage for each category for the breed of animals. Through the data visualized, it is clear that the Domestic SH accounted 34.83%, Pit Bull accounted 9.48%, Domestic MH accounted 4.09% and the rest is other accounted 51.6%. The stacked area cart also be used to see the number of every different pet size. 

#### Proses for data understanding
![image](https://github.com/AaronTeah/codeless-data-science-fundamental-2023-FTU-x-UMK/assets/69444412/0b0aed6e-caf1-4e29-a9ee-ec21109d295a)

#### Louisville_Metro_KY_-_Animal_Service_Intake_and_Outcome.csv dataset 
![image](https://github.com/AaronTeah/codeless-data-science-fundamental-2023-FTU-x-UMK/assets/69444412/352fb60b-e0a6-4f89-92cd-b59fb2aa918e)

#### Pie Chart for breed
![image](https://github.com/AaronTeah/codeless-data-science-fundamental-2023-FTU-x-UMK/assets/69444412/21a04534-51ed-4441-8b83-2a023aa57a4f)

#### The stacked area for pet size
![image](https://github.com/AaronTeah/codeless-data-science-fundamental-2023-FTU-x-UMK/assets/69444412/3d5bf907-1c9a-4670-b59a-18c3314f14c7)

### Data Preparation
In this section, data will be transformed to two different types, which is numeric type and category type. 

1. Model 1: Transform all the data as numerical data
    
   Use the column filter to select the data needed for this model. It is included intype, outtype, animaltype, sex, bites, petsize, color, and breed. Due to there are too many type of the breed in the table, the Rule Engine is used to classified that to only 4 main category, which is PIT BULL, DOMESTIC SH, DOMESTIC MH, and OTHER.
   ```
   $breed$ = "PIT BULL" => "PIT BULL"
   $breed$ = "DOMESTIC SH" => "DOMESTIC SH"
   $breed$ = "DOMESTIC MH" => "DOMESTIC MH"
   TRUE => "OTHER"
   ```
   Next, change the whole dataset from category to number by using Category To Number component. After the numeric number occur, use the column filter to select only the numeric number data and use the Missing Value component to remove the missing value. Lastly, we use the Number To String function to change the data type to string.
   
   #### Proses for Transform all the data as numerical data   
   ![image](https://github.com/AaronTeah/codeless-data-science-fundamental-2023-FTU-x-UMK/assets/69444412/75598595-5cff-49bd-ab9e-aca1b200d62d)

3. Model 2: Remain the data type and clean the data
  
   Use the Missing Value component to remove all the missing data in the dataset. After that use the Rule Engine to reclassified the type of breed to 4 main category, which is PIT BULL, DOMESTIC SH, DOMESTIC MH, and OTHER.

   #### Process for cleaning the data
   ![image](https://github.com/AaronTeah/codeless-data-science-fundamental-2023-FTU-x-UMK/assets/69444412/0d13602d-a579-4ef5-ae85-344d83764ba7)

### Modelling
To train the model that can predict the breed of animal, the decision tree method is used. A decision tree is a non-parametric supervised learning algorithm, which is utilized for both classification and regression tasks. It has a hierarchical, tree structure, which consists of a root node, branches, internal nodes and leaf nodes. The model will find the pattern for every breed by using the tree decision. First, use Data Partitioning to create two separate partitions from original data set: training set (70%) and test set (30%). After that Connect the training set with the Decision Tree Learner to training the model. Lastly, connect the output to Decision Tree Predictor with test set for append the model predictions. 

#### Modelling process
![image](https://github.com/AaronTeah/codeless-data-science-fundamental-2023-FTU-x-UMK/assets/69444412/b41d6b98-a355-4a7c-8c0d-cb0b854bb60e)

#### Part of decision tree result
![image](https://github.com/AaronTeah/codeless-data-science-fundamental-2023-FTU-x-UMK/assets/69444412/a08b2975-a71e-430d-8c2b-580384f56765)

### Evaluation (Result and discussion) 
The scorer will be used to Score the model by compute a confusion matrix between real and predicted class values and calculate the related accuracy measures. Scatter plot also will be used to visualize the model result. 

#### Scorer and Scatter Plot
![image](https://github.com/AaronTeah/codeless-data-science-fundamental-2023-FTU-x-UMK/assets/69444412/497aa41f-79f9-4083-8293-d65ffbe0af52)

#### Result scatter plot 
![image](https://github.com/AaronTeah/codeless-data-science-fundamental-2023-FTU-x-UMK/assets/69444412/ac8add3e-7aa8-4cee-8315-5f27ca55920b)

The scorer result show that model 1 have 82.331% accuracy and model 2 have 82.023% accuracy. That are 0.308% different compare with this two model. It notice that for decision tree learning, the performance of using numeric dataset is better than category dataset. 

#### Model 1(Left) and Model 2(Right)
![image](https://github.com/AaronTeah/codeless-data-science-fundamental-2023-FTU-x-UMK/assets/69444412/00daf9cb-4fbb-479f-b631-a26d6e998232)

To get the more accuracy result, we try to change the combination of data column that use in this model. The following will show different combination and the result. 

#### 82.665% accuracy
![image](https://github.com/AaronTeah/codeless-data-science-fundamental-2023-FTU-x-UMK/assets/69444412/0590481d-d96e-40fe-b77c-88593594474d)

#### 82.252% accuracy
![image](https://github.com/AaronTeah/codeless-data-science-fundamental-2023-FTU-x-UMK/assets/69444412/ed6d92bf-8000-49ba-8036-00e07e7daa1d)

#### 82.945% accuracy
![image](https://github.com/AaronTeah/codeless-data-science-fundamental-2023-FTU-x-UMK/assets/69444412/97ac48fa-33b7-4ef1-b196-b2afe1bcaab3)

### Deployment (Conclusion)
In the conclusion, the model 1 that use intype, animaltype, bites, petsize, color, and breed column can get the more accuracy result, which is 82.945%. Data selection is one of the big concern point when we want to do data analysis. Useless data will affect the accuracy of the model. For example, the animal id is useless when we want to recognize the breed of the animal, because every id is unique. To training a machine learning model, it is also good in use numerical data instead of using category data. For real world application, this model can be used in every veterinary clinic to help them define the breed of the animal. It also can be implemented in apps that help people to recognize the breed of an animal. 






