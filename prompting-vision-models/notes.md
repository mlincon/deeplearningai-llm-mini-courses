# L2 Image segmentation

## What is Image Segmentation
- what is image segmentation?
    - Image segmentation is a technique in computer vision that partitions a digital image into discrete group of pixels
    - example:

    ![image segmentation](images/L2_1.png)
    - image segmentation is typically used to locate objects and boundaries in images
    - it is commonly used in object detection, 3D reconstruction and image editing workflows
    - it is the process of assigning a label to every pixel in an image, such that pixels with the same label share certain characteristics
    
    ![image segmentation](images/L2_2.png)

- methods to visually prompt the Segment Anythin Model (SAM) of Meta AI:
    - prompting with a set of pixel coordinates
    - prompting with multiple sets of coordinates
    - prompting with bounding boxes
    - using a positive prompt along with a negative prompt

## Segmentation Anything Model

-  SAG is widely used for image segmentation, image captioning and iamge editing  
- however, the original SAM has high computational cost (mainly due to its transformer architecture), preventing it from wider adaption
- SAM accepts either bounding box coordinates or single pixel coordinates, as well as an input image

    ![image segmentation](images/L2_3.png)
    - each of the inputs are encoded by an image encoder and an prompt encoder respectively
    - they are then fed into the masked decoder
    - and SAM outputs the top three valid masks for that point or bounding box

## FastSAM
- FastSAM is a CNN based SAM model trained using only 2% of the original data set published by the SAM authors
- it achives comparable performance on 32x32 images, but at 50 times higher the runtime speed

    ![image segmentation](images/L2_4.png)
- prompting FastSAM also differs slightly from prompting the original SAM
- FastSAM also automatically detects all masks in an image above a configurable confidence threshold
- it then filters all the generated masks based on the prompts provided by the user

# References
- [Semantic Segmentation](https://www.jeremyjordan.me/semantic-segmentation/)