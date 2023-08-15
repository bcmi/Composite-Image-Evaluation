# Composite-Image-Evaluation

Here are some possible evaluation metrics to evaluate the quality of composite images from different aspects. 

+ Evaluate whether the foreground is harmonious with background.

  + Harmony score: use [illumination encoder](https://github.com/bcmi/BargainNet-Image-Harmonization) to extract the illumination codes from foreground and background, and measure their similarity.
 
  + Inharmony hit: use [inharmonious region localization model](https://github.com/bcmi/MadisNet-Inharmonious-Region-Localization) to detect the inharmonious region, and calculate the overlap (e.g., IoU) between detected region and foreground region. 

+ Evaluate whether the foreground object placement is reasonable.

  + OPA score: use [object placement assessment model](https://github.com/bcmi/Object-Placement-Assessment-Dataset-OPA) to predict the accuracy of object placement. 

+ Evaluate whether the foreground is compatible with background in terms of geometry and semantics.

  + FOS score: use [foreground object search model](https://github.com/bcmi/Foreground-Object-Search-Dataset-FOSD) to calculate the compatibility score between foreground and background in terms of geometry and semantics. 

+ Evaluate the fidelity of foreground, i.e., whether the synthesized foreground is similar to the input foreground.

  + Clip score
  + Dino score

+ Evaluate the over quality of foreground or the whole composite image.

  + FID
  + QS
