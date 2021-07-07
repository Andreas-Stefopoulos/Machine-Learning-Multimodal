# Machine Learning in Multimodal Data

This repository consists of .ipynb files, in the scope of the second semester "Machine Learning in Multimodal Data" exersice in Master in AI in NSCR Demokritos.

Overview of the files:

* [Text_Extraction.ipynb](https://github.com/Andreas-Stefopoulos/Machine-Learning-Multimodal/blob/main/Text_Extraction.ipynb) file, where our code is inlcuded. Our task was to create a pipeline of machine learning and image preprocessing algorithms, in order to extract text from images (machine and hand written) and correct it using NLP algorithms.
* [requirements.txt](https://github.com/Andreas-Stefopoulos/Machine-Learning-Multimodal/blob/main/requirements.txt) - A .txt file with all the virtual environment requirements to run the above Jupiter notebook file.
* [Test Images](https://github.com/Andreas-Stefopoulos/Machine-Learning-Multimodal/tree/main/Test%20Images) folder, which includes a few of our testing images.

As mentioned in the overview section, our task is to create a pipeline of machine learning and image preprocessing algorithms, in order to extract text from images (machine and hand written) and correct it using NLP algorithms. By using a variety of python libraries and applied many different techniques, we have successfully created a pipeline that extracts the text from images with high accuracy. This is performed by applying preprocess to the input image in order to assist the text extraction. This preprocess, on a high level, consists of cropping, rotating, applying filters and thresholds and then extract text and use NLP to correct it. Firstly, we will refer to the libraries we used and the different categories of algorithms we developed with them and then we will deconstruct the pipeline into segments and analyse them. 

#Croppers 
