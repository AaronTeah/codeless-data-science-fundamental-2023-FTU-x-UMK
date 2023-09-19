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

This project is developing by using Cross-industry Standard Process for Data Mining (CRISP DM) method. 
![CRISP DM methodology](https://github.com/AaronTeah/codeless-data-science-fundamental-2023-FTU-x-UMK/assets/69444412/a5ae399b-0829-495c-9f66-45295f846685)





