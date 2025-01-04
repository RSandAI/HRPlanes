
<img src="https://raw.githubusercontent.com/RSandAI/HRPlanes/main/Assets/HRPlanes%20Header.png" height=400 width=1280 alt="github.com/RSandAI/HRPlanes"/>

<br>

This repository contains weights for YOLOv4 and Faster R-CNN networks trained with the HRPlanes dataset. YOLOv4 training has been performed using [Darknet ](https://github.com/AlexeyAB/darknet), while Faster R-CNN has been trained using [TensorFlow Object Detection API v1.13](https://github.com/tensorflow/models/tree/r1.13.0).

## Updates

**The HRPlanes Dataset is now available for download, featuring 18,477 annotated airplanes from major airports and boneyards. This comprehensive resource supports research in object detection and aerial analysis. See below for details!**

<details>

<summary>Latest updates...</summary>

<br>

<b>December 2024</b>
<ol>
	<li>The HRPlanes Dataset is now available on Zenodo. Please see below for details.</li>
	<li>The HRPlanes weights is now available on Huggingface. Please see below for details.</li>
</ol>

<b>February 2024</b>
<ol>
	<li>The HRPlanes Dataset is now available for download. Please see below for details.</li>
</ol>

</details>

<br>

# HRPlanes Dataset Details

<img src="https://raw.githubusercontent.com/RSandAI/HRPlanes/main/Assets/HRPlanes%20Samples%20All.png" alt="github.com/TolgaBkm/HRPlanes/"/>

The imagery required for the dataset was obtained from Google Earth. We downloaded 4800x2703 sized 3101 RGB images from major airports around the world, such as Paris-Charles de Gaulle, John F. Kennedy, Frankfurt, Istanbul, Madrid, Dallas, Las Vegas, and Amsterdam, as well as aircraft boneyards like Davis-Monthan Air Force Base. The dataset images were manually annotated by creating bounding boxes for each airplane using the HyperLabel software, which still provides annotation services as [Plainsight](https://app.plainsight.ai/). Quality control of each label was conducted through visual inspection by independent analysts who were not involved in the labeling procedure. This process involved checking for consistency in bounding box annotations, ensuring accurate placement around each airplane, and verifying that no annotations were missing or duplicated. A total of 18,477 airplanes have been labeled. A sample image and corresponding minimum bounding boxes for airplanes can be seen in the figure below. The dataset has been approximately split as 70% (2170 images) for training, 20% (620 images) for validation, and 10% (311 images) for testing. For those interested in monitoring closely, the sample images used in this dataset can be accessed [here](https://github.com/TolgaBkm/HRPlanes/tree/main/Sample%20Images).

<br>

# Evaluation Results

| Model       | Description                                                | mAP50  | mAP75 | mAP50-95 | Download Weights                                            |
|-------------|------------------------------------------------------------|--------|-------------|----------|------------------------------------------------------------|
| YOLOv4      | Trained using Darknet. Robust performance with high mAP at 50% IoU but a decrease at higher IoU thresholds. | 99.15% | 91.82%      | 73.02%   | [Download](https://huggingface.co/TolgaBkm/HRPlanes_Weights) |
| Faster R-CNN| Trained using TensorFlow Object Detection API. Maintains better performance at higher IoU thresholds compared to YOLOv4. | 96.80% | 90.00%      | 76.40%   | [Download](https://huggingface.co/TolgaBkm/HRPlanes_Weights) |

The evaluation results show that both networks perform well up to 75% IoU threshold; the mAP value of YOLOv4 is 73.02%, whereas Faster R-CNN provided slightly better performance with 76.40%. Although YOLOv4 produces very high mAP at 50% IoU value of 99.15%, this value reduces with increasing IoU values and decreases to 91.82% for mAP at 75% IoU. YOLOv4 seems superior considering 50% and 75% IoU thresholds. The decrease rate of AP with increasing IoU is higher for YOLOv4 compared to Faster R-CNN. This indicates that YOLOv4 cannot perform efficiently at IoU thresholds higher than 80% in our dataset. 

<!-- Including a visual representation of these trends, such as a graph, could make the performance differences between the models more accessible and intuitive. -->

<br>

# Download The HRPlanes Dataset

We are pleased to announce that the entire HRPlanes dataset is now available for download in YOLO format. This dataset, containing annotated images of airplanes from major airports and aircraft boneyards, can be accessed on [Zenodo](https://zenodo.org/records/14546832). Feel free to explore and utilize this rich resource for your research and projects.

<br>

# Citation

If you make use of the test dataset or weights, please cite our [paper](https://dergipark.org.tr/tr/pub/ijeg/issue/77206/1107890#article_cite) to acknowledge the source.

BibTeX:

	@article{bakirman2023benchmark,
	  title={A benchmark dataset for deep learning-based airplane detection: HRPlanes},
	  author={Bak{\i}rman, Tolga and Sertel, Elif},
	  journal={International Journal of Engineering and Geosciences},
	  volume={8},
	  number={3},
	  pages={212--223},
	  year={2023},
	  publisher={Murat YAKAR}
	}

Plain Text:

Bakırman, T., & Sertel, E. (2023). A benchmark dataset for deep learning-based airplane detection: HRPlanes. _International Journal of Engineering and Geosciences_, _8_(3), 212-223. https://doi.org/10.26833/ijeg.1107890

<br>

# Copyright

The use of Google Earth images must respect the ["Google Earth" terms of use](https://about.google/brand-resource-center/products-and-services/geo-guidelines/). All images and their associated annotations can be used for academic purposes only; commercial use is prohibited.

Released under the [Creative Commons Attribution-NonCommercial-NoDerivatives 4.0 International (CC BY-NC-ND 4.0) License.](https://creativecommons.org/licenses/by-nc-nd/4.0/)
