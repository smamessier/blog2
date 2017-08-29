---
layout: post
title: Computer Vision – Personal thoughts
date: '2012-03-24 18:17:00'
tags:
- projects-edu
---

Being part of the following class projects motivated me to write a couple of thoughts about Computer Vision and my understanding of it coming with an Engineering background.

Projects

* 3D Body Scanner 
* Smartphone app for safe driving
* Compact database of line drawings

##### Computer science and engineering

I always considered Computer Science as a hobby or a technological tool supporting engineering or theoretical research. Back in France, in the so-called Grande Ecoles (engineering schools), the computing department is only here to teach every student basic programming skills. I personally think that every curious and open-minded engineering student should have learned these programming skills by himself years ago. For example, I was surprised to state the small number of aerospace students with a sharp understanding of object-oriented programming. I had a few smartphone apps projects in mind and I wanted to meet people to brainstorm about these projects. That’s one of the reason I wanted to take classes in the College of Computing.

I had my first contact with computer vision as an astronomy enthusiast when I had to get clean pictures from noisy low-resolution videos of Saturn. The pipeline was the following: choosing the best images out of one thousand, registering, then stacking them and use wavelets as a final touch. Astronomers are not that good in computer vision. Most of them use opaque processing software and sleep during the processing.
 Before I entered Georgia Tech, I had a very interesting research project about detecting light flashes caused by asteroids impacting the moon from very noisy and dark videos. So my first job was to register the video. I thought it would be as easy as it was with pictures of planets. But cross-correlation based techniques just didn’t work. That’s why I came to read advanced computer vision literature. I couldn’t imagine that so much had been done about image registration. That’s one of the reasons that pushed me to follow CS7495 this semester. Moreover, I thought it would be awesome to combine two of my favorite subjects: Mathematics and Computer science.
I was still thinking I had a good computing background before I started to talk with my classmates. SIFT, SURF, RANSAC, SVM, HOG, all these things sounded like chinese to me. It was quite difficult for me to understand the subtleties of the first lectures, but I caught up quite fast and got fascinated by lots of different topics.

##### Computers vs Humans

Before taking this class, it wasn’t clear to me why/when or how the human and the computer could have different approaches to solve a computer vision problem. In the cases where the computer approach was totally different from the human one, was it because of a lack of resources, learning capacity… or was it simply a more judicious choice? I used to consider detection methods that aren’t available to humans (because of computational load for example) as cheating. I always thought there should be some easier method…  But reading one of the chapter of Forsyth and Ponce – Computer Vision about Gestalt principles of perceptions made me realize that there were too many processes and resources in human’s brain to be able (nowadays) to identify them and implement them properly. Things like image segmentation look like basic tasks for us, we don’t even think about it.

##### Probabilistic vs Deterministic

My first project took advantage of the Kinect 3d sensor to perform unsupervised 3d body scans. One of the most challenging part was non-rigid registration of 3d point clouds. One of the papers I read about it was Anguelov’s “The correlated correspondence algorithm for unsupervised registration of nonrigid surface”. It was the first time I read about bayesian probabilities applied to computer vision problems. I took me a couple of days to be able to understand it completely but it was worth a shot. It led me to understand MRFs and explore belief propagation algorithms and more generally structured model-based methods. Before that I was mostly used to deterministic methods.

<iframe src = "/ViewerJS/#/docs/gatech/7495/report1.pdf" width='100%' height='600' allowfullscreen webkitallowfullscreen></iframe> 

##### Recognition paradigm

Object recognition is one of these computer vision problems where the human is still performing much better than the machine. State-of-the art research seems to tend to the following paradigm:
 
-	Gradient-based descriptors
-	Structured dataset (like felzenszwalb’s part-based recognition)
-	Deterministic or probabilistic decision-making.

Concerning activity recognition, the retrieval process is more likely to be probabilistic, using for example Hidden Markov Models. But deterministic methods (for example using Motion history gradients descriptors) exist too.

Object and activity recognition seemed to me to be the most challenging part of modern computer vision.

I did Project number 3 about variations around Microsoft Shadow draw project with Mark Luffel in order to reduce memory load and improve performance for mobility purposes. So we thought about adapting Felzenzwalb’s part-based approach to reduce the size of our dataset. Several hours of brainstorming later and we we’re talking about object recognition instead of patch retrieval. I mentioned that to say that object recognition would be a panacea to many many problems.
 When it didn’t bring a general solution to this challenging problem, CS 7495 had the advantage to explore state-of-the-art research about it and give us the necessary insight to go any further into the subject.

<iframe src = "/ViewerJS/#/docs/gatech/7495/report3.pdf" width='100%' height='600' allowfullscreen webkitallowfullscreen></iframe> 

#####2d / 3d sensors 


Lectures about stereoscopy, range sensors and the first project I did made me think about the future of sensors for both industrial and general public purposes. The current 3d adaptation of Titanic shows that you don’t really need range sensors to feel the depth, you can actually close one eye without making a big difference. The human brain is able to recognize a rigged body without using range data. 
So are 3d sensors (stereoscopy) the future of computer vision? I don’t think so. In fact, in high demanding industries, other sensors like LIDARs do a better job. Combining information from accurate range sensors and visual images into RGBZ point clouds (as it has been done with Kinect) could help computer vision to give meaning to images. Since WillowGarage is taking care of the development of PCL (Point Cloud library), we can imagine that kinect-like range sensors will be part of future robot’s battery of sensors. Does range information really helps to understand a picture? For example, it could clearly help segmentation and add constraints to penalty-based probabilistic models. Does the human brain really use 3d information for object recognition for instance? The answer might be ‘no’. Indeed one-eyed persons still perform well at it.
Project 2 enabled me to spend time on an idea I had about implementing a safe driving app for Iphone including robust detection, features tracing and classifier-based vehicle recognition. Exploring the literature about similar professional projects, I came up with the following question : “Is it more important to refine data accuracy by improving sensors, or to search for new ways of processing data for intelligent and robust detections?”. The arrival on the market of smartphones with poor sensors and decent computational capability would promote the second one, while professional demanding applications will more likely use priceless sensors and focus a bit less on robustness. At the end, robust clever algorithms could support high quality sensors and lead to highly efficient vision systems. 

<iframe src = "/ViewerJS/#/docs/gatech/7495/report2.pdf" width='100%' height='600' allowfullscreen webkitallowfullscreen></iframe> 

#####Computer vision, robotics

As its name implies, Computer Vision focuses on the tiny visible part of the electromagnetic spectrum. Is equipping robots with eyes really necessary? Robots developed for performing industrial specific tasks don’t always need vision. Moreover, lots of systems that use vision use it because it’s the only or cheapest sensor available. So will vision really matter in a future with cheaper and better quality sensors? In fact, CS 7495 made ask myself this question and brought answers too.  Even if lots of papers design ad-hoc solutions for specific issues, general principles emerge from computer vision research about machine understanding, learning and interpreting. 
I’m an aerospace guy, but I felt very confortable taking this class. Every week it was a great pleasure to listen to Frank Dellaert and all other lecturers. Actually I’d like to combine my engineering skills, my enthusiasm for computer science and fascination for robots by following a PhD in Robots and Intelligent Machines. 



