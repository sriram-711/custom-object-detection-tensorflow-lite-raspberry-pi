# custom-object-detection-tensorflow-lite-raspberry-pi
* git clone https:https://github.com/sriram-711/custom-object-detection-tensorflow-lite-raspberry-pi.git
* open command promt and cd custom-object-detection-tensorflow-lite-raspberry-pi
* Than past this command : sudo rm /usr/lib/python3.11/EXTERNALLY-MANAGED
* type ls in command promt it will show labelimg.sh file 
* Than past this command : sudo chmode 775 labelimg.sh
* again ls now that labelimg.sh converted into green color
* Now install labelimg using this command: bash labelimg
* Now enter labelImg in command promt it will open labelImg tool
# install all the dependencies
* sudo apt install python3-pip
* pip3 install opencv-python
* pip install mediapipe
# Prepare Dataset (take live video and Convert Video to Frames)
* open img.py
* in the 4th line of code, we have a predefined count 50, you can increase the count to decrease the number of images to be generated and vice-versa
* creat a folder names as (images) inside tflite-mediapipe-main give path of this folder in the code (cv2.imwrite)
* all the images saved in that (images folder)
* create onemore folder give any name i given as (indiamoney)
* go that folder(indiamoney) and create two folders names as (train,validate)
* go to train folder and create two more folder named as (images,Annotations)
* go to train folder and go to images fodler and past all the images which we saved in images inside the inside tflite-mediapipe-main
* open command promt and (cd inside tflite-mediapipe-main) then type this command (labelImg)
* it will open labelimg tool
* click open dir and choose path as tflite-mediapipe-main/indiamoney/train/images/
* it will load all the image files in the file list
* click change save dir and choose path as tflite-mediapipe-main/indiamoney/train/Annotations/
* bit will save all annotations inside directory
* click create rect box and draw boundary to the object, give name to object and click save
* paste rectbox for each repeating image and draw new for new object
* do it for all images and save each
* go to train folder and copy the two folder(images,Annotations) and past in the validate folder
# Training the data using google colab
* open google and type google colab and signin with your account
* open notebook and go to the this folder tflite-mediapipe-main then mediapipe.ipynb
* it will open code
* run step by step
* go to runtime and select python3 and T4GPU and click on connect
* open command promt and give this command: sudo zip -r  indiamoney.zip indiamoney/*
* it will conerted into zip file upload that zip file in the google colab
* run all the command and replace freedomtech with indiamoney
* at last it will give best.tflite
* replace that file path in code (testvid.py)
* Run the testvid.py code  
* the above command will start the detection procedures
