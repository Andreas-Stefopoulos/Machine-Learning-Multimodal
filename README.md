# Machine Learning in Multimodal Data

This repository consists of .ipynb files, in the scope of the second semester "Machine Learning in Multimodal Data" exersice in Master in AI in NSCR Demokritos.

Overview of the files:

* [Text_Extraction.ipynb](https://github.com/Andreas-Stefopoulos/Machine-Learning-Multimodal/blob/main/Text_Extraction.ipynb) file, where our code is inlcuded. Our task was to create a pipeline of machine learning and image preprocessing algorithms, in order to extract text from images (machine and hand written) and correct it using NLP algorithms.
* [requirements.txt](https://github.com/Andreas-Stefopoulos/Machine-Learning-Multimodal/blob/main/requirements.txt) - A .txt file with all the virtual environment requirements to run the above Jupiter notebook file.
* [Test Images](https://github.com/Andreas-Stefopoulos/Machine-Learning-Multimodal/tree/main/Test%20Images) folder, which includes a few of our testing images.

As mentioned in the overview section, our task is to create a pipeline of machine learning and image preprocessing algorithms, in order to extract text from images (machine and hand written) and correct it using NLP algorithms. By using a variety of python libraries and applied many different techniques, we have successfully created a pipeline that extracts the text from images with high accuracy. This is performed by applying preprocess to the input image in order to assist the text extraction. This preprocess, on a high level, consists of cropping, rotating, applying filters and thresholds and then extract text and use NLP to correct it. Firstly, we will refer to the libraries we used and the different categories of algorithms we developed with them and then we will deconstruct the pipeline into segments and analyse them. 

### Croppers 

In order to develop our cropping algorithms, we used the following libraries:

* [Open Source Computer Vision (OpenCV)](https://docs.opencv.org/3.4/index.html) 
* [Numpy](https://numpy.org/doc/)

Due to the power of [OpenCV](https://docs.opencv.org/3.4/index.html), we developed different approaches, in order to generalize as much as possible.

### Rotators

Our second category of preprocess algorithms is the Rotators, where we apply them in order to allign the image, due to the high sensitivity in text extractors in errors in skewed images. The libraries used are:

* [Open Source Computer Vision (OpenCV)](https://docs.opencv.org/3.4/index.html) 
* [Numpy](https://numpy.org/doc/)
* [Tesseract](https://tesseract-ocr.github.io/)

### Text Extractors

In order to extract the text from images, we created texts extraction algorithms using the following libraries:

* [Space OCR API](https://ocr.space/ocrapi)
* [Tesseract](https://tesseract-ocr.github.io/)
* [Easy OCR API](https://www.jaided.ai/) 
* [Open Source Computer Vision (OpenCV)](https://docs.opencv.org/3.4/index.html) 
* [Numpy](https://numpy.org/doc/)

### NLP Algorithms

After having extracted the text, we created vocabulary-grammatical-syntactic natural language process (error checking and correcting) algorithms, using the following libraries:

* [Ginger API](https://www.gingersoftware.com/company-overview) 
* [Python Language Tool](https://languagetool.org/)
* [TextBlob](https://textblob.readthedocs.io/en/dev/)
* [Spell Checker](https://silpa.readthedocs.io/projects/spellchecker/en/latest/)

Now that we have mentioned our main algorithm categories, we will proceed to the deconstruction of our pipeline, which steps are applied and what output is in every step.

The **first step**, after loading and image, is to apply the first preprocess algorithms category of croppers. We generate 3 new cropped images with 3 different techniques. 
* Algorithms to crop: 3
* Input of this step: 1 image
* Output of this step: 3 cropped images

The **second step**, is to apply the rotation algorithms to these 3 cropped images. We now generate 15 images from our 5 different rotation algorithms.
* Algorithms to rotate: 5
* Input of this step: 3 images
* Output of this step: 15 rotated and cropped images

The **third step** is now to extract the text of these 15 plus the 3 only cropped plus the original image, using our 3 different text extraction algorithms. The two algorithms were developed to recognize machine written text and the third one to recognize handwritten text in images. By applying these 3 different text extractors to all of our 19 images, we now have 57 texts.
* Algorithms to extract text: 3
* Input of this step: 19 images
* Output of this step: 57 different texts

The **fourth step** is to evaluate our texts and keep only the best of them. In order to do this, we calculate the length of each text and keep the one with max length from the machine written extractors and the one with max length from the handwritten extractor, assuming that the text with higher length is a text where the extractor managed to recognize more characters. The output of this step is only 2 texts, the "best" ones.
* Input of this step: 57 texts
* Output of this step: 2 texts

The **fifth step** is to apply the vocabulary-grammatical-syntactic error correctors using the NLP algorthms we created. We developed 4 different algorithms and the output of this step are 8 texts.
* NLP Algorithms: 4
* Input of this step: 2 texts
* Output of this step: 8 texts

As a **last step** we may apply once again the "maxpooling" technique in order to have again only 2 texts, but in our code we chose to keep all 8 and print the text extraction of the original image by applying preprocess only in the text extraction, in order to compare the results.

nbviewer link: [Text Extractor](https://nbviewer.jupyter.org/github/Andreas-Stefopoulos/Machine-Learning-Multimodal/blob/main/Text_Extraction.ipynb)
