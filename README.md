# Lung-Cancer-Diagnosis-using-XAI

- Lung Cancer is the leading cause of cancer-related deaths worldwide and also is the most misdiagnosed condition. The advancements of AI in the medical field allowed improvements in disease diagnosis where advanced and complex AI models help doctors to make accurate decisions.  However, this complexity comes with the curse of not being able to interpret these models and understanding how and why the model reached the decision it did. Understanding the model's decisions and actions becomes very crucial if the application is related to life-saving fields like the medical industry, cancer diagnosis, and autonomous vehicle systems. 
- This project aims to address the importance and significance of explainable artificial intelligence in healthcare, particularly in the field of Lung cancer diagnosis and explanation. A measurable objective of this project includes improving the accuracy of diagnosis, enhancing the explainability of the model like 3D-CNN, U-Net,  ResNet50, VGG16, Dense-Net50, and transformers, to increase the level of patient trust in the model's output. 
- The project tasks will involve the selection and preprocessing of relevant diseases. datasets, the design, and implementation of various XAI approaches such as LIME, SHAP, and Integrated Gradients will be used to explain the models' output and improve transparency. Also, evaluate the models based on performance metrics such as sensitivity, AUC, ROC, and F1-Score. XAI can help medical professionals in making better informed and more accurate diagnoses on patients' relevance of the professional experience they hold. 

- <img src="Screenshot 2023-06-16 at 12.07.34 PM.png">

### The Pipeline:
- 1ProcessNoduleDataset.ipynb
- Inputs: LIDC dataset (DOI folder), list3_2.csv, LIDC-IDRI_MetaData.csv
- Outputs: nodule images.py, nodule-masks.npy
- 2TrainUnet.ipynb
- Inputs: nodule_images.npy, nodule-masks.npy
- Outputs: unet-weights-improvement.hdf5
- 3ClassifyNodulesLIDC.ipynb
- Inputs: LIDC dataset (DOI folder), list3_2.csv, LIDC-IDRI_MetaData.csv, unet-weights-improvement.hdf5
- Outputs: truenodule-cnn-weights-improvement.hdf5
- 4DetectNodules.ipynb
- Inputs: unet-weights-improvement.hdf5, truenodule-cnn-weights-improvement.hdf5, Kaggle DSB2017 dataset (stage1 folder)
- Outputs: DSBNoduleImages*.npy, DSBNoduleMasks*.npy, DSBPatientNoduleIndex*.csv
- 5CancerPredictionClassifiers.ipynb
- Inputs: DSBPatientNoduleIndex*.csv
- 6CancerPredictionCNN.ipynb
- Inputs: DSBNoduleImages*.npy, DSBNoduleMasks*.npy, DSBPatientNoduleIndex*.csv
- *Split into a series of files due to large memory requirements
- Reference: https://github.com/mikejhuang/LungNoduleDetectionClassification
