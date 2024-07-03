+++
title = 'Reflections on Implementing ResNet-8 with Pure Tensorflow Core (No Keras)'
date = 2024-07-03T19:41:16+10:00
draft = true
comments = false
+++
**"Any fool can know. The point is to understand." - Albert Einstein**

Something that's always caught me out whenever I started an ML project was how much work got abstracted away by simply calling `model.fit()` and alike functions/methods. High-level libraries like Keras are brilliant for quickly experimenting and developing deep learning models. However, I've always wanted to try and implement some sort of novel neural network architecture from scratch purely for my joy and understanding.

After some digging, I settled on the goal of building a ResNet from scratch using Tensorflow core. It seemed like a reasonable stretch from doing just a pure CNN in terms of complexity

**TLDR:** 90% accuracy and my workflow was to do the following:
- Read the original paper -> Fiddle around through Tensorflow docs and a LOT of Medium articles -> Find data on Kaggle -> Write a simple training process -> Evaluate model

**How I started?** Pretty much the very first thing I did was find the original paper on [Deep Residual Learning for Image Recognition](https://arxiv.org/abs/1512.03385) and read through it. I think this paper does a great job at contextualising why ResNet was so revolutionary through highlighting key issues like how it. On top of this, I also did a pretty quick 1 hour refresher on neural network fundamentals (backpropagation, metrics, loss functions).

**How I went about the implementation?** 
- After getting the background in the problem, I first wrote a `tf.Module` for my residual blocks which were essentially 2 convolutional layers with the crucial skip connection at the end. Then I could implement an 8-layer ResNet which leveraged these blocks with consecutive filter sizes of 64, 128, 256. 
- Used cross entropy for the loss function since I was working with a multiclass medical image dataset from Kaggle. 
- TF Core has a neat feature for picking up on trainable variables so once my implementation was complete, I really just needed to pass these onto some gradient tape and write a quick loop for training. I used `tensorflow-metal` to leverage my GPU on Mac and was able to train a classification model of an accuracy above 90% in about 30 mins on my implementation.
- I evaluated on Top-1 validation/training accuracies and also shared the confusion matrix with some class mates.

**Plan as of now?** Put a quick [streamlit](https://streamlit.io/) app around the model to wrap things up nicely and the move on to the next project :P

**Would I do it again?** It was a bit time-consuming so for efficiency purposes probably not unless its for fun or I'm needing to get really low-level with network design. Nonetheless, I learnt a bunch and it was a very useful mini-project.