# face_detect_recognize
This is a face detection and recognition project

From the camera to obtain video stream data, detect whether there is a face in the video, if there is a face for face recognition.

Face detection can get five key points of face, and use key points to face alignment, then face feature extraction, and finally face feature matching.

Mtcnn is used as face detection algorithm, and sphereface is used as face recognition algorithm.

This project contains two parts：

1 . Update the base face library information

(1). face detect
path = ~/IDcar/mxnet_mtcnn_face_detection-master
picture path : path/faceimgtest/
Detect key points in face images, and And the key point information to path/preface_landmark.txt
python2 landmarkwrite.py

(2). feature extract
path = ~/sphereface_pytorch-master
extract the face feature values of the pictures in the library and save the features to path/faceimg_feature/ . Each face feature is stored in a .npy file.
python2 face_feature.py


2. Get the real time return from  a camera get pictures

(1). Opening feature extraction network interface program
path = ~/sphereface_pytorch-master
cd path
python2 face_feature_extract_web.py
The face image feature values obtained in real time are saved in path/faceimg_reature_test/

(2). Start the main program (camera data acquisition + detection + feature extraction + feature comparison + return result)
path = ~/IDcar/mxnet_mtcnn_face_detection-master
cd path
python2 camera_main.py

1) real time data acquisition from camera and face detection using mtcnn algorithm.
2) the extracted face images are used for feature extraction.
3) comparing real-time facial features with basic face database images.
4) return the face image with the highest similarity and satisfying the preset threshold.








