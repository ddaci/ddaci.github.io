---
title: "Fingerprint recognition, Python, Tkinter"
description: ""
featured_image: "/images/coveramprenta.jpg"
date: 2024-03-01T13:16:06+03:00
draft: false
tags: ["Python", "Tkinter", "SIFT algorithm"]
---


A biometric fingerprint recognition system is organized into four main stages: fingerprint input, feature extraction of fingerprints, comparison stage with the fingerprint set from the database (1:N type comparisons), and the final stage of deciding whether there is a match with a record in the dataset.
[link to the project on github](https://github.com/ddaci/Recunoastere_amprenta_digitala)


The following figure shows the logical scheme and structure of the project. It also illustrates the addition of a new fingerprint to the database and the deletion of a record.

![alt text](/images/schema.png "Overview")

The graphical interface of the application (GUI) is built using the Tkinter library and looks like this:

![alt text](/images/interfata.png "Overview of GUI")

I have defined three frames (frame1, frame2, frame3) to organize the graphical interface and have loaded background images for each frame. Frame 1 contains the logo, and frame 2 contains the four buttons mentioned above. Frame 3 allows the display of the fingerprint search result in the database and also includes two buttons, the Back button which allows returning to frame 2, and the Exit button to leave the application. Each of the 6 buttons in the application has hover functionality implemented.

Minutiae Detection Using the SIFT Algorithm
The most undeniable constitutional feature of a fingerprint is its pattern of ridges, edges, and bifurcations (minutiae). These characteristics are used to compare one fingerprint with others. There are several algorithms for feature detection. Regarding fingerprint recognition, algorithms such as Scale-Invariant Feature Transform (SIFT), Speeded-Up Robust Features (SURF), Oriented FAST and Rotated BRIEF (ORB), and Binary Robust Invariant Scalable Keypoints (BRISK) can be implemented. SIFT is an algorithm used in image processing and object recognition. This algorithm was developed to detect and extract distinctive features from images, which are invariant to scale changes or rotation. These features are crucial for comparing and matching objects in images, regardless of variations in perspective, lighting, or distortions. The keypoints identified by SIFT are selected to be representative and distinctive for the objects in the image.

The SIFT algorithm follows several key steps:

Scale-space extremum detection: The algorithm uses Gaussian functions to identify potential interest points in the image, which are invariant to scale changes and rotation.
Keypoint localization: Determines the location and scale of each keypoint identified in the previous stage.
Orientation assignment: An orientation is assigned to each keypoint based on the local gradient directions of the image.
Descriptor creation: For each keypoint, a descriptor is created that represents the gradient directions in a surrounding area. These descriptors are used to compare and match objects or features in images, making SIFT extremely useful for object recognition, object tracking, and other image processing applications.
Fingerprint Matching with FLANN Matcher
Feature matching is a stage where the similarity score between two images is calculated using their detected features and descriptors. In OpenCV, this similarity score is defined as the distance between two images, the lower the distance value, the more similar the image, and vice versa. This similarity score is then checked using a threshold value to determine whether the image is a match or not. Fast Library for Approximate Nearest Neighbors Matcher (FLANN Matcher) is a component of the FLANN library. FLANN Matcher uses a series of optimized algorithms to find the nearest neighbors in large datasets. The main algorithms used in FLANN Matcher are the hierarchical k-means tree and the randomized k-d tree. FLANN Matcher is known for its speed in finding nearest neighbors, especially in large datasets, making it suitable for applications where response time is critical.

Sokoto Coventry (SOCOFing) Fingerprint Dataset
The SOCOFing dataset is a biometric fingerprint database created for academic research purposes. SOCOFing consists of 6,000 fingerprint images. The names of the records (of the fingerprint images) contain unique attributes, such as labels for gender (female or male), hand (left or right), and finger name. The dataset also contains synthetically altered versions of the original fingerprints. The alteration of the images was done by erasing areas of the image, through central rotation and "Z" shaped cuts.

![alt text](/images/rezultat.png "The result")