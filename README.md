# CNN-Covid-19vsPulmonaryCancerClassifcation
Using Deep learning techniques  in order to distinct between radiological symptoms in Pulmonary Cancer and Covid-19
During the pandemic period, patients who suffered from pulmonary cancer were misdiagnosed with COVID-19 due to the similarity of the symptoms. First-stage cancer is characterized by coughing, chest pain, and dyspnea. As for radiological symptoms, specialists have proven the similarity; both show ground glass opacities in the lung area on CT scans. To aid the diagnosis process, I implemented a CNN architecture that takes a CT scan as input and provides a predicted label as output. Since the dataset I am using is not very extensive, I chose the route of transfer learning using VGG-19 and ResNet50V2, only adding the last layers for classification. The training was conducted using Google Colab, with 50 to 80 epochs using Adam as the optimizer and the Sigmoid function as the activation for the last layer. The accuracy on testing was 92.6% with ResNet50V2 and 86.8% with VGG-19.
