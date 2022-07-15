# Hazardous Environment Dataset
A visuo-lingual dataset for hazardous environments. The work has been accepted to [IROS 2022](https://iros2022.org/).

The dataset is divided into two parts: **language dataset** and **image dataset**.

1. The **language data** is stored in the form of a dictionary and can be found in [DangerLanguageInformation.p](https://github.com/vikshree/hazard_dataset/blob/main/DatasetLanguageInformation.p). The dictionary is structured as:
  ```bash
      |-- Movie name -> Name of the movie.
        |-- Scene name -> Scene category.
          |-- Image number -> Number corresponding to the image.
            |-- 'Danger Level' -> Array of size 5 depicting the number of people voting for each danger level.
            |-- 'Keywords' -> Words provided by AMT users.
            |-- 'img_path' -> Path of the corresponding image file in Image dataset.
            |-- 'mode' -> Mode of the danger distribution for that particular image.
            |-- 'entropy' -> Entropy of the normalized probability mass function of danger.
            |-- 'median' -> Median of the normalized probability mass function.
            |-- 'Language' -> Array of tuples where each tuple denotes the keywords used ny AMT uder and corresponding danger rating. 
            |-- 'category' -> Dataset category: train/val/test.
  ```
  For example, 
  ```bash
      |-- 'EscapeFromNewYork'
        |-- 'Bridge_129'
          |-- '15'
            |-- 'Danger Level' -> [1, 5, 4, 5, 0]  
            |-- 'Keywords' ->  ['man looking at man', 'lighting', 'collapsed site', 'people', 'wall', 'collapse', 'rubble sliding', 'landslide', 'brick', 'isolation', 'rubble', 'dust', 'building', 'demolish', 'man', 'accident', 'damaged building', 'reciprocation', 'electrical wires', 'wreckage', 'climbing', 'concrete', 'metal', 'trapped', 'building collapse', 'death', 'blood', 'earthquake', 'debris', 'trapped', 'building', 'collapsed', 'climbing', 'rubble', 'destruction', 'darkness', 'falling', 'cutting', 'collapse', 'collapse', 'rubble', 'explosive', 'vandalization', 'destruction', 'destroy']
            |-- 'img_path' -> 'train/EscapeFromNewYork/Bridge_129/img15.png'
            |-- 'mode' -> 3
            |-- 'entropy' ->  0.786245363513509
            |-- 'median' -> 3.0
            |-- 'Language' ->  [('man looking at man', 1), ('lighting', 1), ('collapsed site', 1), ('people', 2), ('wall', 2), ('collapse', 2), ('rubble sliding', 3), ('landslide', 3), ('brick', 3), ('isolation', 2), ('rubble', 2), ('dust', 2), ('building', 2), ('demolish', 2), ('man', 2), ('accident', 4), ('damaged building', 4), ('reciprocation', 4), ('electrical wires', 3), ('wreckage', 3), ('climbing', 3), ('concrete', 4), ('metal', 4), ('trapped', 4), ('building collapse', 4), ('death', 4), ('blood', 4), ('earthquake', 4), ('debris', 4), ('trapped', 4), ('building', 3), ('collapsed', 3), ('climbing', 3), ('rubble', 2), ('destruction', 2), ('darkness', 2), ('falling', 2), ('cutting', 2), ('collapse', 2), ('collapse', 3), ('rubble', 3), ('explosive', 3), ('vandalization', 4), ('destruction', 4), ('destroy', 4)] 
            |-- 'category' -> 'train'
  ```

2. The **image dataset** can be downloaded from [here](https://drive.google.com/file/d/1rnG9OsqSuqR8KBbmW9mSeKuisVHQFt1j/view?usp=sharing). The 'DisasterMovieDataset' folder contains the dataset and is arranged as follows:
  ```bash
      |-- Category -> Dataset category: train/val/test.
        |-- Movie name -> Name of the movie.
          |-- Scene name -> Scene category.
            |-- Images -> All image files in '.png' format present in that category, from that movie, belonging to that specific scene.
  ``` 
----
**Please cite our paper as:**
### Citation
```Shell
@article{shree2022multimodal,
  title={Multi-modal Perception for Cooperative Escape Planning in Hazardous Environments},
  author={Shree, Vikram and Allen, Sarah and Asfora, Beatiz and Banfi, Jacopo and Campbell, Mark},
  booktitle={2022 IEEE/RSJ International Conference on Intelligent Robots and Systems},
  organization={IEEE}
}
```
---
Sample dataset
------
Below are few sample images from the dataset, their corresponding danger danger rating, and keywords provided by Amazom Mechanical Turkers.


| Image with danger responses | Keyword samples with danger ratings|
| ------------- |:-------------:| 
| <img src="files/d5_01.png" width="800"> | ('fire', 5) <br> ('smoke', 3) <br> ('trapped', 3) <br> ('explosion', 4) <br> ('accident', 4)| 
| <img src="files/d5_02.png" width="800"> | ('dark', 5) <br> ('fire', 5) <br> ('trapped', 4) <br> ('smoke', 4) <br> ('heat', 5) | 
| <img src="files/d5_03.png" width="800"> | ('flood', 5) <br>  ('cold', 5) <br> ('water', 4) <br> ('death', 5) <br> ('sinking', 4) | 
| <img src="files/d5_04.png" width="800"> | ('water', 5) <br> ('damage', 5) <br> ('inundation', 5) <br>  ('ship', 5) <br> ('rush', 5) | 
| <img src="files/d5_05.png" width="800"> | ('smoke', 5) <br> ('heat', 5) <br> ('fire', 5) <br> ('accident', 4) <br> ('fireman', 5) | 
| <img src="files/d4_01.png" width="800"> | ('drowning', 5) <br> ('ship', 5) <br> ('passanger', 5) <br> ('stuck', 4) <br>('water', 1) | 
| <img src="files/d4_02.png" width="800"> | ('smoke', 2) <br> ('smoke', 5) <br> ('burning', 4) <br> ('danger', 4) <br> ('elevator', 4) <br> ('firefighters', 4) | 
| <img src="files/d4_03.png" width="800"> | ('soot', 4) <br> ('freeze', 5) <br> ('flood', 5) <br> ('boat', 4) <br> ('drown', 4) | 
| <img src="files/d4_04.png" width="800"> | ('dark', 3) <br> ('fumes', 2) <br> ('tripping', 1) <br> ('haze', 4) <br> ('damaged', 4) | 
| <img src="files/d4_05.png" width="800"> | ('unsafe', 5) <br> ('smoking', 3) <br> ('rubble', 5) <br> ('electricity', 5) <br> ('spark', 4) | 
| <img src="files/d3_01.png" width="800"> | ('dirty', 2)<br> ('lowlight', 1) <br> ('darkness', 2) <br> ('cracks', 3) <br> ('collapse', 5) | 
| <img src="files/d3_02.png" width="800"> | ('darkness', 3) <br> ('smoke', 4) <br> ('gun', 4) <br> ('light', 2) <br> ('rubble', 1) | 
| <img src="files/d3_03.png" width="800"> | ('mess', 1) <br> ('trash', 1) <br> ('wreckage', 2) <br> ('collapse', 3) <br>  ('accident', 3) | 
| <img src="files/d3_04.png" width="800"> | ('broken', 2) <br> ('blast', 5) <br> ('waste', 5) <br> ('metal', 2) <br> ('wreckage', 3) | 
| <img src="files/d3_05.png" width="800"> | ('disaster', 3) <br> ('falling', 3) <br> ('cracking', 3) <br> ('tremor', 3) <br> ('broken', 5) | 
| <img src="files/d2_01.png" width="800"> | ('darkness', 2) <br> ('car', 1) <br> ('smoke', 4) <br> ('fire', 4) <br> ('destruction', 4) | 
| <img src="files/d2_02.png" width="800"> | ('sewer', 3) <br> ('rushing', 5) <br> ('ocean', 3) <br> ('inundation', 2) <br> ('darkness', 2) |
| <img src="files/d2_03.png" width="800"> | ('trash', 2) <br> ('earthquake', 4) <br> ('debris', 2) <br> ('dark', 3) <br> ('alley', 3) | 
| <img src="files/d2_04.png" width="800"> | ('kids', 1) <br> ('quiet', 1) <br> ('scared', 2) <br> ('hiding', 2) <br> ('subway', 3) | 
| <img src="files/d2_05.png" width="800"> | ('stairs', 2) <br> ('flooding', 4) <br> ('damaged', 2) <br> ('house', 2) <br> ('smoky', 3) | 
| <img src="files/d1_01.png" width="800"> | ('destroying', 2) <br> ('vandalism', 1) <br> ('robbed', 1) <br> ('breaking', 2) <br> ('haze', 2) | 
| <img src="files/d1_02.png" width="800"> | ('wall', 1) <br> ('car', 1) <br> ('man', 1) <br> ('building', 1) <br> ('clean', 1) | 
| <img src="files/d1_03.png" width="800"> | ('tranquility', 1) <br> ('formal', 1) <br> ('ship', 1) <br> ('skylight', 1) <br> ('stairs', 1) | 
| <img src="files/d1_04.png" width="800"> | ('hallway', 1) <br> ('door', 1) <br> ('ligth', 1) <br> ('house', 2) <br> ('vacant', 1) | 
| <img src="files/d1_05.png" width="800"> | ('smoke', 3) <br> ('debris', 3) <br> ('dark', 2) <br> ('falling', 1) <br> ('candles', 3) | 

## Contact
Vikram Shree ([vs476@cornell.edu](mailto:vs476@cornell.edu))
