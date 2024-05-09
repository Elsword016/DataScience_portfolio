# Image Processing 
Some projects to showcase my learning, particularly focussing on fine-tuning models on biological data and image processing in general. Some might be related to experiment data for which I won't share the data for obvious reasons. 

## 1. CLIP-Seg + SAM segmentation
Implementation of simple panoptic segmentation using CLIPSegmentation model (https://huggingface.co/blog/clipseg-zero-shot) and then refining the low-resolution mask with Segment Anything(https://segment-anything.com/) by prompting it with points sampled within the low-res mask from CLIPSeg.

![CLIPsam](https://github.com/Elsword016/Road-to-learning-ML/assets/29883365/cda9759b-1c70-40af-b4f3-25a818d6c89d)

## 2. Segment Anything model prompting ##
Trying out Segment Anything model from MetaAI with bounding box prompts. In this case, we give the bounding box coordinates to the model of the ROI and generate the a high-quality segmentation.
- Automatic mask generation 
![autogen](https://github.com/Elsword016/Road-to-learning-ML/assets/29883365/7fdb48e5-b7d5-4a84-9b0b-8e01031cb7f7)

- Bounding box prompt for mask generation 
![bbox_prompt](https://github.com/Elsword016/Road-to-learning-ML/assets/29883365/059a8c58-6c21-4467-acb4-d22d667ae712)

## 3. Blood Cell Classification with ViT from scratch
Using Pytorch I implemented a Vision Transformer totally from scratch, similar to the paper [An Image is Worth 16x16 Words: Transformers for Image Recognition at Scale](https://arxiv.org/abs/2010.11929). I closely followed [Uva deep learning course](https://uvadlc.github.io/) explanation and how to define pytorch lightning training setup.
| ![ViT-arch](https://github.com/Elsword016/DataScience_portfolio/assets/29883365/21bb6c70-a0a0-46b3-b1ab-c6a39e6100eb) | Prediction ![image](https://github.com/Elsword016/DataScience_portfolio/assets/29883365/4e24ebd9-88c6-4e12-9f2c-7ba53c761634) 
|-------------------------|-------------------------|

## 4. Segmenting Retina blood vessels using a finetuned Segformer model
Segmentation using Segformer base model from HuggingFace on Retina blood vessel dataset with a simple gradio interface for inferencing

Dataset obtained from Kaggle - [Blood Vessel Data](https://www.kaggle.com/datasets/abdallahwagih/retina-blood-vessel)


![image](https://github.com/Elsword016/DataScience_portfolio/assets/29883365/92f1efaf-8aaf-444d-a9bd-c2f636db167d)

## 5. Dendritic spine segmentation using Segformer with LoRA Adapters
Segmentation of dendritic spines from 2-photon microscopy images. I used the base Segformer model and then converted it into a LoRA model using the PEFT library to reduce the number of parameters.

More details here-> [ReadMe](Spine_Segmentation/Readme.md)

![image](https://github.com/Elsword016/DataScience_portfolio/assets/29883365/be50ee43-ffe9-45a6-83e6-882935776142)

## 6. Spine segmentation with SAM using point prompts
Spine segmentation by finetuning [Segment Anything](https://ai.meta.com/research/publications/segment-anything/) model using points as prompts rather than bounding boxes. 

For each of the ground truth masks, points (n=100) are sampled from the non-zero pixel positions
then forward it to the prompt encoder. 

I used the HuggingFace 🤗 [SamModel](https://huggingface.co/facebook/sam-vit-base) class.

(It will be a nice experiment to see the quality of detection using bounding box prompt vs points)

**Dataset** - My own spine images
![image](https://github.com/Elsword016/DataScience_portfolio/assets/29883365/5222d82c-7373-4cbc-bf4b-ac6f02a556b4)

## 7. Multi-class prediction of obesity risk
To predict obesity risk in individuals related to cardiovascular disease from various features. I evaluated different classifiers and performed SHAP analysis to find the important features relevant to the classification.

Dataset: [Kaggle playground series](https://www.kaggle.com/competitions/playground-series-s4e2)

| ![image](https://github.com/Elsword016/DataScience-and-ML-projects/assets/29883365/bf30f6f4-2ecf-4e1c-93fc-10c6266cf3d1) | ![image](https://github.com/Elsword016/DataScience-and-ML-projects/assets/29883365/e1d15290-7a9b-43af-88f1-a6a5b9ec53b5)
|-------------------------|-------------------------|

## 8. A quick eye-tracking solution
A simple pupil segmentation followed by centroid tracking. Segmentation is done using K-means and simple image-processing tricks. It's not SOTA, but I came with it in 4 hours for a competition.

**Dataset** - proprietary 


| ![segmentation](https://github.com/Elsword016/DataScience-and-ML-projects/assets/29883365/9aab427b-de83-4995-bebf-237ff2090b55) | ![output_track](https://github.com/Elsword016/DataScience-and-ML-projects/assets/29883365/d204341a-ca4c-4d13-a802-f544180607a6)
|-------------------------|-------------------------|










