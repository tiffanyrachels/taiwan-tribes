# Persevering Taiwanese Indigenous Cultures

# Introduction
In the modern era of rapid technological advancement, artificial intelligence presents a unique opportunity to preserve and celebrate cultural heritage. This project aims to recognize and classify the outstanding totems of two indigenous Taiwanese tribes, the Tawu (達悟族) and Taiya (泰雅族). By using a Convolutional Neural Network (CNN) model enhanced with transfer learning from a pre-trained ResNet50V2 model, we analyze a dataset consisting of images from Tawu and Taiya groups. The analytical methods involve training and fine-tuning deep learning models to achieve accurate classification.

Taiwanese indigenous peoples are a vital part of the nation’s cultural heritage. Their diverse traditions, languages, and art forms enrich Taiwan’s cultural landscape. The totems of the Tawu and Taiya tribes, in particular, symbolize their spiritual beliefs, historical narratives, and social values. Preserving these totems is crucial for maintaining Taiwan’s cultural diversity and historical continuity. The primary objective of this project is to develop an AI system that accurately identifies and categorizes these totems using advanced machine learning techniques. This initiative marks the first application of AI technology to Taiwanese indigenous heritage. By pioneering this approach, we aim to not only preserve these cultural artifacts but also foster a deeper appreciation and understanding of these indigenous cultures. Through this innovative integration of AI with the traditions of the Tawu and Taiya tribes, we seek to highlight the enduring beauty and relevance of their heritage.

This project is important for several reasons. It addresses the risk of cultural erosion that many indigenous communities face in the modern world. By digitally preserving and cataloging these totems, we help ensure that the rich cultural heritage of the Tawu and Taiya tribes is not lost to future generations. Additionally, the project serves as an educational tool, promoting awareness and understanding of indigenous cultures among both local and international students, which can lead to greater cultural appreciation and respect. By utilizing advanced AI techniques, the project demonstrates the potential of technology to support cultural preservation, setting a precedent for similar initiatives in other indigenous communities around the world. Ultimately, this project not only aims to conserve the culture of the Tawu and Taiya tribes but also to spread knowledge of these beautiful traditions, highlighting the vital role that AI can play in cultural preservation and education, and contributing to a richer and more diverse global heritage.

# Getting Started
## Prerequisites
Google Colab

TensorFlow

Keras

NumPy

Pandas

PIL (Python Imaging Library)

Python 3.x

scikit-learn

Matplotlib

Gradio

Google Drive (for dataset storage)

## Installation
1) Install necessary libraries using pip
pip install tensorflow keras numpy pandas pillow scikit-learn matplotlib gradio==3.43.1
2) Mount Google Drive in Colab
from google.colab import drive drive.mount('/content/gdrive')
3) Download the dataset and place it in your Google Drive under the specified paths.

# File Structure
- /content/gdrive/MyDrive/2 AI Dataset/

雅美族(達悟族) Plan B/: Contains images of Tawu.

泰雅族 (Plan B)/: Contains images of Taiya.

- model_resnet50v2.h5: The saved model after training and fine-tuning.

# Analysis
## Data preparation
- Load images from the specified directories.
- Preprocess images by resizing them to (224, 224) and normalising pixel values.
- Encode labels for Tawu as 1 and Taiya as 0.
- Split the dataset into training and testing sets using an 80-20 split.

## Model Training
Initial Model:
- A basic CNN model was trained with the following architecture:
  Conv2D -> MaxPooling2D -> Conv2D -> MaxPooling2D -> Flatten -> Dense -> Dense
- Compiled using SGD optimizer and trained for 10 epochs.

Transfer Learning with ResNet50V2:
- Used a pre-trained ResNet50V2 model without the top layers.
- Added custom top layers: GlobalAveragePooling2D -> Dense -> Dense.
- Initially, trained with the base model's layers frozen.
- Fine-tuned by unfreezing the last 10 layers and training with a lower learning rate.

# Result
The final model achieved a test accuracy of 90% after fine-tuning. The classifier can now accurately distinguish between images of Tawu and Taiya. Furthermore, the Gradio interface was created for easy deployment and testing of the model with new images.

# Limitations
1. Dataset Size and Diversity: The dataset used in this project is relatively small (only 93 images) and may not encompass the full diversity of totems within each tribe. In this case, this limitation could affect the model's ability to recognize targeted totems. 
Image Quality and Consistency: The quality and consistency of the images in the dataset can vary. Factors such as lighting, angle, and resolution could impact the model's accuracy.
2. Cultural Sensitivity: While the AI model aims to preserve and promote indigenous cultures, it is essential to ensure that the cultural representations are accurate and respectful. For further possible improvement, collaborating closely with the indigenous communities is crucial to validate the model's classifications and interpretations.
3. Technical Constraints: The reliance on transfer learning from pre-trained models like ResNet50V2, while effective, may not capture specific nuances unique to the totems of the Tawu and Taiya tribes. Custom models trained on larger, more diverse datasets might yield better results.

# Contributors
Ronald (110501071) = Project manager

Tiffany (112ZU1028) = Programmer

Pancake (112ZU1029) = Member (data collector)

Mill (112ZU1031) = Member (data collector)

Cindy (112ZU1021) = Member (data collector)

# Announcement: Addressing Data Collection and Totem Misidentification Challenges
We are pleased to announce the progress of our AI project focused on preserving the cultural heritage of Taiwanese indigenous tribes. This project aims to recognize and classify the totems of the Tawu (達悟族) and Taiya (泰雅族) tribes using advanced machine learning techniques. However, we must address a significant issue we have encountered during our data collection process.

# Issue
During the data collection phase, we primarily concentrated on the Tawu and Taiya tribes. While this focus allowed us to delve deeply into these two cultures, it also introduced a risk of misidentifying totems from other tribes. Totems are intricate symbols deeply embedded in the cultural and spiritual lives of indigenous communities, and misidentifying them can lead to cultural misrepresentation and misunderstanding.

# Potential Challenges
One of the potential challenges we face is the accuracy of our totem classification. Despite our best efforts to ensure the precision of our AI model, there remains a possibility of misidentification. Our understanding is based on the data available to us, and we hope that our model has accurately recognized and categorized the totems of the Tawu and Taiya tribes. However, if any misidentifications have occurred, we sincerely acknowledge that we need to correct them.

# Possible Improvement
1. Community Engagement and Validation: We will engage closely with the Tawu and Taiya communities, as well as other indigenous tribes in Taiwan. By collaborating with cultural experts and community leaders, we can validate our data and ensure that our classifications are accurate and respectful.
2. Open Feedback Mechanism: We invite feedback from anyone with knowledge of indigenous totems. If you identify any inaccuracies in our classifications, we welcome your corrections and insights. Your input is invaluable in ensuring the integrity and authenticity of our project.
3. Expanded Data Collection: Moving forward, we aim to expand our data collection efforts to include a broader range of tribes. This expansion will not only enhance the diversity of our dataset but also reduce the risk of misidentification by providing a more comprehensive understanding of indigenous totems.
4. Ongoing Training and Refinement: We will continue to refine our AI model by incorporating new data and insights from indigenous communities. This ongoing process will help improve the model's accuracy and reliability, ensuring that it evolves in alignment with cultural nuances.
We are committed to the respectful and accurate representation of indigenous cultures. By acknowledging the potential challenges and actively seeking solutions, we aim to create a robust and culturally sensitive AI system. We appreciate the support and collaboration of all stakeholders in this endeavour and look forward to your contributions in preserving and celebrating the rich cultural heritage of Taiwanese indigenous tribes.

# Acknowledgement
We would like to express our deepest gratitude to the Professor. Pien for his invaluable guidance, support, and encouragement throughout this project. His expertise and insights have been instrumental in shaping our research and refining our AI model. We also extend our heartfelt thanks to the all attendances during the exhibition on 6/6 for their invaluable feedback. Additionally, we are grateful to all the owners of the images that provided the data sources, without which this project would not have been possible. Your contributions have been crucial in helping us preserve and promote the rich cultural traditions of Taiwanese indigenous tribes. Thank you for your unwavering support and collaboration.

Sincerely,

Contact Info.

[Ronald, Tiffany, Pancake, Mill, Cindy.] 

[E-mail: 110501071@nccu,edu,tw / 886+ 968952611 ] 

[Group G/ AI Introduction course / National ChengChi University]
