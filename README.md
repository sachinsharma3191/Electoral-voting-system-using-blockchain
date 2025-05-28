# Electoral Voting System using Blockchain

A decentralized and tamper-proof voting system built on the **Ethereum blockchain**, integrated with **face recognition-based voter verification** to ensure secure and fair elections.

## 🔐 Blockchain Features (Solidity, Ethereum, Web3.js)

- **Smart Contracts (Solidity):** Handle voter registration, candidate addition, vote casting, and result tallying with full transparency and immutability.
- **Ethereum Network (Ganache):** Smart contracts deployed and tested locally for simulating decentralized environments.
- **Web3.js Integration:** Frontend interacts with deployed smart contracts to read/write vote data in real time.

## 👁️ Face Recognition & Anti-Spoofing (Python, Flask, dlib, OpenCV)

- **Facial Verification:** Uses deep face embeddings and classifiers (SVC, KNN, Random Forest) for voter identification.
- **Spoof Prevention:** Employs eye-blink detection using facial landmarks to distinguish real users from images or videos.

---

# Installation

1. Install python3  
```
On MacOs  
brew install python3  
```

```
On Ubuntu  
sudo apt-get install python3  
```
2. Setup a virtual environment in the folder
```sudo pip3 install virtualenv ```  
```virtualenv myenv```  
```source myenv/bin/activate```

3. Install requirements
```pip3 install -r requirements.txt```  
  ├── pandas  
  ├── numpy  
  ├── sklearn  
  ├── flask  
  ├── flask_cors  
  ├── imutils  
  ├── cmake  
  ├── dlib  
  ├── opencv-python  
 
**Folder structure** 
```
├── Data collection
│   └── datasplit.py
├── Flask
│   └── facerecog_v3.py
├── Frontend
│   ├── README.md
│   ├── images
│   ├── package-lock.json
│   ├── package.json
│   ├── public
│   ├── src
│   └── test
├── Models
│   ├── KNN.py
│   ├── RandomForest.py
│   └── SVC.py
├── README.md
├── backend
│   ├── GenPassword.js
│   ├── Main.js
│   ├── Router.js
│   ├── Routerold.js
│   ├── package-lock.json
│   └── package.json
└── requirements.txt
```

### Run

```cd Frontend npm install```

```cd backend node Main.js```

```python3 facerecog_v3.py```

Dataset: Labelled faces in the wild [Download](http://vis-www.cs.umass.edu/lfw/#download) and VGG face2 dataset [link](http://www.robots.ox.ac.uk/~vgg/data/vgg_face2/)


### Eye and mouth detection
* Using face alignment [2] to get the facial landmarks and using [1] to compute eye aspect ratio to identify eye blinking.   
* This is to avoid spoofing attacks by clearly differentiating a real person's face and an image of the person

### Face recognition
* Generate 128-d embedding of each person's image in the dataset.
* Train the various model for classification
* Testing: Generate the embedding of the person you want to recognize and compute the similarity between test person's embedding and pre-computed embedding.


### References
1. [Real time eye detection](http://vision.fe.uni-lj.si/cvww2016/proceedings/papers/05.pdf)
2. [Face alignment](http://www.csc.kth.se/~vahidk/papers/KazemiCVPR14.pdf)
3. [Shape predictor dataset](https://ibug.doc.ic.ac.uk/resources/facial-point-annotations/)
4. [FaceNet](https://www.cv-foundation.org/openaccess/content_cvpr_2015/app/1A_089.pdf)
5. [dlib pretrained models](https://github.com/davisking/dlib-models)
