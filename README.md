# Fruit Image Classification Using Transfer Learning (VGG16)

In this project I built an image classifier that can recognize 24 different fruit (and vegetable) categories from photos. Instead of training a deep neural network from scratch — which would require a massive dataset and a lot of compute — I used **transfer learning** with **VGG16**, a well-known convolutional neural network that was pre-trained on ImageNet (1.2 million images, 1000 classes).

The idea is simple: VGG16 already knows how to detect edges, textures, shapes and patterns. I kept all of that knowledge, chopped off its original classification head, and replaced it with my own layers trained specifically to tell fruits apart.

The pipeline goes like this:
1. Download and set up the Fruits-360 dataset
2. Build data generators with augmentation
3. Load VGG16 and add custom classification layers on top
4. Train with the VGG16 weights frozen (feature extraction phase)
5. Unfreeze the last few VGG16 layers and fine-tune
6. Evaluate on the test set and visualize predictions

Final test accuracy: **~86%** across 24 classes.
