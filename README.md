# keras_facenet_ver1
# . References:
<font color='blue' font-family= "Times New Roman">
<p>This project using FaceNet to face recognition. FaceNet was proposed by <a href="http://www.florian-schroff.de">Florian Schroff</a> Florian Schroff in the 2015 article <a href="https://arxiv.org/abs/1503.03832">FaceNet: A Unified Embedding for Face Recognition and Clustering</a>
</p>
<p>
Pretrained FaceNet model was created by <a href="https://drive.google.com/drive/folders/1pwQ3H4aJ8a6yyJHZkTwtjcL4wYWQb7bn">Hiroki Taniai</a> download here.</p>

Download model and put to the folder: 'input/facenet-keras/facenet_keras.h5'

    input
    ├── facenet-keras
    │   └── facenet_keras.h5
    ├── faces-dataset
    │   └── data
    ├── unknown
    │   ├── 1.jpg
    │   ├── 2.jpg
    │   ├── ...
    │   └── ...
    Output
 # 1. Colect data:   
    Copy data set image to 2 folders 'train' and 'val' in the parent folder 'data'. Each folder 'train' and 'val' has the following structure:

    train
    ├── ChiPu
    │   ├── ChiPu_0001.jpg
    │   ├── ChiPu_0002.jpg
    │   ├── ...
    │   ├── ChiPu_0014.jpg
    │   └── ChiPu_0015.jpg
    ├──....
    ├── Quang Son
    │   ├── Quang Son_0001.jpg
    │   ├── Quang Son_0002.jpg
    │   ├── ...
    │   ├── Quang Son_0014.jpg
    │   └── Quang Son_0015.jpg
    ├── ...
    │   
    ├── TruongGiang
    │   ├── TruongGiang_0001.jpg
    │   ├── TruongGiang_0002.jpg
    │   ├── ...
    │   ├── TruongGiang_0015.jpg
    │   └── TruongGiang_0016.jpg
# 2. Requirements:
    !pip install mtcnn
    !pip install tensorflow<2.0
    !pip install scipy==1.1.0
    !pip install scikit-learn
    !pip install opencv-python
    !pip install h5py
    !pip install matplotlib
    !pip install Pillow
    !pip install requests
    !pip install psutil
# 3. Pre-processing
## Face alignment using MTCNN
Using function: <code>extract_face(filename)</code>, return the faces from input image file, input image normalization: 160x160.

Open source https://pypi.org/project/mtcnn/

You can refer to the method here:

https://towardsdatascience.com/face-detection-neural-network-structure-257b8f6f85d1

https://medium.com/dummykoders/face-detection-using-mtcnn-part-1-c35c4ad9c542

https://towardsdatascience.com/mtcnn-face-detection-cdcb20448ce0

<img src="https://miro.medium.com/max/511/1*4yubqhjXWyaENvbqdK-zJA.png">

# Pre-Train using facenet
Using function <code>get_embedding(facenet_model, faces)</code> in that model <code>facenet_model</code> has been pretrain before. faces obtained from pre-processing in MTCNN

Open source https://github.com/davidsandberg/facenet

Referance articles: https://arxiv.org/abs/1503.03832

<img src="https://miro.medium.com/max/700/1*OmFw4wZx5Rx3w4TpB7hS-g.png">
# 4. Train models
Using SVC model of scikit-learn: https://scikit-learn.org/stable/modules/generated/sklearn.svm.SVC.html

<img src="https://chrisalbon.com/images/machine_learning_flashcards/Support_Vector_Classifier_print.png">

