# Computer Vision: Determining the Age of Buyers

## Project Description

A retail supermarket chain is implementing a computer vision system to process photos of customers. Photo capture at the checkout area will help determine the approximate age of customers to:
- Analyze purchases and suggest products that may interest customers of a specific age group.
- Monitor cashiers' integrity when selling alcohol.

The goal is to build a model that can estimate a person's age from a photograph, using a dataset of labeled images of people with their ages.

## Data Analysis

### Dataset Overview
- **Dataset Size**: 7,591 images.
- **Columns**: `file_name` (image filename) and `real_age` (age label).

### Age Distribution
The age distribution of the dataset is visualized to understand the spread and frequency of ages. The histogram shows:
- Most ages are concentrated between 20 and 40 years.
- Fewer samples are available for younger (below 10) and older (above 70) age groups.

### Sample Images
A few sample images from the dataset are displayed to provide an idea of the data quality and variability.

## Methodology

### Data Preparation
- Images are resized to 224x224 pixels.
- Pixel values are normalized to the range [0, 1].
- Data is loaded using `ImageDataGenerator` for efficient batch processing.

### Model Architecture
The model is built using:
- **Backbone**: Pre-trained ResNet50 for feature extraction.
- **Additional Layers**: Global average pooling and a dense layer for regression.
- **Optimizer**: Adam with a learning rate of 0.0001.

### Training
- The model is trained to minimize mean absolute error (MAE), a common metric for regression tasks.
- Training is performed using a generator to handle the large dataset efficiently.

## Results
The model's performance is evaluated on a test set, with the MAE serving as the primary metric. Lower MAE indicates better accuracy in age prediction.
