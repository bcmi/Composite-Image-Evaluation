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

  + Clip score: use [CLIP](https://github.com/openai/CLIP) to extract the embeddings from the input foreground image and the generated foreground patch, and measure their similarity.
 
  + Dino score: use [DINO](https://github.com/facebookresearch/dino) to measure the average cosine similarity between the input and generated foreground.  
<!--
Specifically, we crop out foreground patch from generated composite and mask the non-object region to compute CLIP score with the masked input foreground, in which we estimate the mask of foreground object using [SAM](https://github.com/facebookresearch/segment-anything). We employ pretrained [clip-ViT-B-32](https://huggingface.co/openai/clip-vit-base-patch32) as image encoder following [Paint-by-Example](https://github.com/Fantasy-Studio/Paint-by-Example/tree/main).
-->

+ Evaluate the over quality of foreground or the whole composite image.

  + FID: use pretrained image encoder (*e.g.*, InceptionNet, CLIP) to extract the embeddings from real images and generated images, and measure their [Fréchet Inception Distance](https://github.com/mseitzer/pytorch-fid).
  + QS: use [quality score](https://github.com/cientgu/GIQA) to measure the quality of each single generated image, and compute average score.    
