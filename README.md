# CNN-Covid-19vsPulmonaryCancerClassifcation
Using Deep learning techniques  in order to distinct between radiological symptoms in Pulmonary Cancer and Covid-19 developed in python with tensorflow. 
During the pandemic period, patients who suffered from pulmonary cancer were misdiagnosed with COVID-19 due to the similarity of the symptoms. First-stage cancer is characterized by coughing, chest pain, and dyspnea. As for radiological symptoms, specialists have proven the similarity; both show ground glass opacities in the lung area on CT scans. To aid the diagnosis process, I implemented a CNN architecture that takes a CT scan as input and provides a predicted label as output. Since the dataset I am using is not very extensive, I chose the route of transfer learning using VGG-19 and ResNet50V2, only adding the last layers for classification. The training was conducted using Google Colab, with 50 to 80 epochs using Adam as the optimizer and the Sigmoid function as the activation for the last layer. The accuracy on testing was 92.6% with ResNet50V2 and 86.8% with VGG-19.





The data set 

The corresponding images for the cancer class were obtained from the dataset collected by the Oncology University Hospital in Iraq over a three-month period in the autumn of 2019. It includes computed tomography scans from patients diagnosed with neoplastic formations in various stages, as well as healthy patients. In total, there are 1190 images belonging to 110 cases grouped as follows: 40 confirmed malignant cases, 15 benign cases, and 55 healthy cases. Only the malignant cases were used for the actual implementation. This classification was performed by specialized physicians from the mentioned centers.

<img width="1044" alt="image" src="https://github.com/mariasavu/CNN-Covid-19vsPulmonaryCancerClassifcation-/assets/101450857/67a5b360-b35d-44f8-a2bf-3e83431a9d46">
Source:alyasriy, hamdalla; AL-Huseiny, Muayed (2023), “The IQ-OTH/NCCD lung cancer dataset”, Mendeley Data, V4, doi: 10.17632/bhmdr45bh2.4)


The data was initially collected in DICOM format but was converted to PNG format. Information regarding the acquisition method includes:

- The SOMATOM device from Siemens was used for data acquisition.
- The settings were 120 kV with a slice thickness of 1 mm.
- The image reading utilized a window from 350 to 1200 Hounsfield units (HU), centered from 50 to 600 HU.

For the COVID-19 class, the data was extracted from a public collection of images collected from hospitals in Sao Paulo, Brazil. The dataset contains 2482 images, out of which 1252 are from confirmed SARS-CoV-2 patients. The data format is PNG, and no details are provided regarding the acquisition method or the equipment used.

<img width="1084" alt="image" src="https://github.com/mariasavu/CNN-Covid-19vsPulmonaryCancerClassifcation-/assets/101450857/17bd718f-d575-4235-b5b2-99fa9b799342">

Source:  Soares, Eduardo, Angelov, Plamen, Biaso, Sarah, Higa Froes, Michele, and Kanda Abe, Daniel. "SARS-CoV-2 CT-scan dataset: A large dataset of real patients CT scans for SARS-CoV-2 identification." medRxiv (2020). doi: https://doi.org/10.1101/2020.04.24.20078584.
Due to the fact that the data originates from two completely different sources, it was necessary to preprocess the files to provide the network with a more balanced dataset. Neither of the two image sets organizes the slices according to the originating patient, which is a limitation addressed in the results chapter.

In total, 560 images were used for each class, with 364 for training, 91 for validation, and 105 for testing.
