---
title: Custom AI Models for Arduino App Lab
description: This tutorial teaches you how to create and train your own AI models to customize your Apps Bricks.
author: Christopher Méndez
hardware:
  - hardware/uno/boards/uno-q
tags: [SBC, Linux, Debian, AI, Model]
difficulty: beginner
---

## Overview

# Overview

Predefined models offer a powerful starting point for understanding edge AI. In this tutorial, we will extend those capabilities by engineering and deploying our own custom machine learning models. By moving to a custom workflow, we empower your Arduino App Lab applications to handle specialized tasks and unique datasets, ensuring the system is perfectly calibrated to your specific project goals.

![Custom AI models](assets/thumbnail.png)

By training our own models, we gain precise control over classification parameters and performance metrics, ensuring the system meets the specific requirements of your deployed environment rather than relying on generic solutions.

## Goals

* **Collect** a custom dataset for audio or image related models.
* **Train** a model from scratch in Edge Impulse Studio.
* **Integrate** your custom model into Arduino App Lab to customize your Bricks.

## Required Hardware and Software

### Hardware Requirements

* [Arduino UNO Q](https://store.arduino.cc/products/uno-q) (x1)
* USB Camera for image-based AI models
* USB microphone for audio-based AI models

### Software Requirements

- [Arduino App Lab](https://www.arduino.cc/en/software/#app-lab-section)
- Arduino Account (also works to log in Edge Impulse Studio)

## Machine Learning

To set the context, we need to understand what an "AI Model" actually is.

In the world of Traditional Programming, we write explicit rules: *If button A is pressed, turn on LED B.*
In **Machine Learning**, we don't write rules; we provide examples. We show the computer 100 photos of a "Banana" and 100 photos of an "Apple," and the computer figures out the rules to tell them apart itself. The result of that learning process is an **AI Model**.

![Image](assets/)

By creating a custom model, you are essentially creating a new "brain" file that you can swap into your Arduino App Lab Bricks to change their behavior completely.

### Edge Impulse Studio

To create these custom models we use **Edge Impulse Studio**.

![Image](assets/)

Edge Impulse is the leading development platform for embedded machine learning. Think of it as the "kitchen" where we prepare our AI. It handles the entire pipeline required to build a model that can run on the UNO Q.

#### The Workflow

Instead of writing code to define the neural network, you use the Studio's visual interface to guide the process:

![Image](assets/)

1.  **Data Acquisition:** This is the most critical step. You upload images or audio samples to Edge Impulse. You can do this using your mobile phone, your computer, or even capture data directly from the UNO Q.
2.  **Impulse Design:** This is where you structure your "brain." You define an **Input block** (e.g., Audio or Image data), a **Processing block** (to clean up the data), and a **Learning block** (the neural network that learns the patterns).
3.  **Training:** The Studio uses its cloud servers to crunch the numbers. It will look at your data thousands of times until it learns to recognize the keywords or objects you defined.
4.  **Deployment:** Edge Impulse allows us to export the trained model specifically for the **Arduino UNO Q**, and it gets imported directly into our Arduino App Lab application.

When you export for the UNO Q, you get an **.eim (Edge Impulse Model)** file. This file acts like a container; it holds all the logic and trained parameters needed to run it.

## Creating your Custom AI Model

### Image Based Models

- In your custom App, navigate to your Brick in the left Arduino App Lab menu, "Object Detection" in this case, and select the **AI Models** tab. 

![Image here]()

- The interface lists available models for your Brick, showing only the built-in Default model if no new ones have been trained.

- To start training your custom model, click on **Train new AI model**, if this is your first time, you will be guided through the Arduino account creation or log in.

![Image here]()

- Your same Arduino account will be valid to log in into the Edge Impulse Studio



### Audio Based Models

Here explaning the workflow from the Hey Arduino Example in Arduino App Lab