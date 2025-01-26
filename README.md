# inswapper-512-live

*The initial test version is scheduled for release around **February 11th**. Currently, efforts are focused on optimizing the Mac app user interface and conducting standardization tests on model metrics.*


## Introduction

**``inswapper-512-live``** is an ultra-lightweight face swapping model that provides native 512x512 resolution. Compared to the ``inswapper_128`` model, it requires less than one-tenth of the computational complexity while being capable of producing results with 16 times the pixel output (512x512 vs 128x128).

<div align="left">
  <img src="https://github.com/nttstar/insightface-resources/blob/master/images/inswapper_512_live_1.jpg" width="1024"/>
</div>

## Evaluation

| ModelName          | Parameters | GFlops | ID Similarity | Realism | Attributes |
|--------------------|------------|--------|---------------|---------|------------|
| INSwapper_128      |            |        |               |         |            |
| INSwapper_Cyn      |            |        |               |         |            |
| INSwapper_Dax      |            |        |               |         |            |
| INSwapper_512_live |            |        |               |         |            |

**Metric Explanation:**

1) **ID Similarity**: This metric evaluates the similarity between the swapped face image and the source face. It utilizes a third-party high-precision face recognition model for assessment, with scores ranging from 0 to 100. A higher score indicates greater similarity.

2) **Realism**: This metric assesses the realism and clarity of the swapped face image. Scores range from 0 to 100, where a higher score signifies greater realism and clarity.

3) **Attributes**: This metric evaluates the relevance of attributes in the swapped face image compared to the target face, including factors such as gaze direction, expression, etc. Scores range from 0 to 100, with higher scores indicating better attribute alignment.

## License

All resources within this project, including applications and models, are not to be utilized for any commercial purposes and are intended solely for academic use or personal testing. 
