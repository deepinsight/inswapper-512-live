# inswapper-512-live

*The initial test version is scheduled for release around **February 11th**. We are currently optimizing the Mac APP UI and standardizing the model metrics testing.*


## Introduction

**``inswapper-512-live``** is an ultra-lightweight face swapping model that provides native 512x512 resolution. Compared to ``inswapper_128``, it requires less than 1/10 of the computational resources yet produces outputs with 16 times the pixel count(512x512 vs 128x128).

<div align="left">
  <img src="https://github.com/nttstar/insightface-resources/blob/master/images/inswapper_512_live_1.jpg?raw=true" width="1024"/>
</div>

## Evaluation

*The numbers in the table may fluctuate as we continue to gather more diverse test data.*

| Model                                                                                              | Output      | Params   | GFLOPs    | Similarity | Realism  | Attributes |
| -------------------------------------------------------------------------------------------------- | ----------- | -------- | --------- | ---------- | -------- | ---------- |
| [INSwapper_128](https://github.com/deepinsight/insightface/tree/master/examples/in_swapper)        | RGB 128x128 | 138.3M   | 174.7G    | 86.9       | 63.3     | 78.8       |
| [INSwapper_Cyn](https://www.picsi.ai)                                                              | -           | -        | -         | 92.8       | 75.9     | 80.6       |
| [INSwapper_Dax](https://www.picsi.ai)                                                              | -           | -        | -         | 92.5       | 86.0     | 81.5       |
| [INSwapper_Dax(w Optimizer)](https://www.picsi.ai/docs#-optimizer-and-enhanced-interface-features) | -           | -        | -         | **93.4**   | **90.2** | **87.7**   |
| INSwapper_512_live_base                                                                            | RGB 512x512 | **9.5M** | **12.1G** | 87.0       | 73.7     | 80.1       |
| INSwapper_512_live_mini                                                                            | RGB 512x512 | **4.7M** | **6.3G**  |            |          |            |

*Both the number of parameters and GFLOPs are calculated under FP32 precision.*

**Evaluation Metric Explanation:**

1) **Similarity**: The similarity between the generated face and the source face is evaluated using a third-party, high-precision face recognition model. The similarity score is calculated using the cosine similarity between the feature embeddings of the source and output images, scaled to a range of 0-100, where higher scores indicate greater similarity.

2) **Realism**: This metric evaluates the realism and clarity of the generated face. We employ a comprehensive evaluation framework that combines the FID score, custom-designed metrics for facial clarity, and human perceptual evaluation. The score ranges from 0 to 100, with higher scores indicating a more realistic and clear result. We used a test set consisting of hundreds of high-resolution facial images, and randomly resized between 160x160 and 640x640 pixels in testing time.

3) **Attributes**: This metric assesses the correlation between the attributes of the generated face and the target face, including factors such as pose, gaze direction, expression, etc. We employ third-party facial attribute models to extract feature representations of both the generated and target images. The similarities between these feature vectors are then computed to obtain the final metric score, which ranges from 0 to 100, with higher scores indicating better attribute alignment.

## License

All resources in this project, including models, libraries and applications, are strictly for academic use or personal testing and cannot be used for any commercial purposes. 
