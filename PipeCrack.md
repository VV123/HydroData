# PipeCrack Dataset

## Dataset

The PipeCrack Dataset comprises images collected and annotated for training object detection models to identify pipeline defects.

- Data source :
  Google Images: General pipeline defect images sourced via Google search.
  Unsplash: High-quality, royalty-free pipeline-related images
  Kaggle Pipeline Defect Dataset :most of the data is from kaggle ('https://www.kaggle.com/datasets/simplexitypipeline/pipeline-defect-dataset')

- Annotation Method :
  annotated some images using labelimg ('https://github.com/HumanSignal/labelImg') used to make custom labels sample images and label pic is inside images folder .
  Formats: XML for TensorFlow, TXT for YOLO; some pre-annotated data from Kaggle.

- Labels (Six classes)
  0:Deformation
  1: Obstacle
  2: Rupture
  3: Disconnect
  4: Misalignment
  5: Deposition

## AI detection method

- Tensorflow

  - Model: SSD MobileNet V2 FPNLite 320x320, fine-tuned using the TensorFlow Object Detection API for detecting pipe cracks.

  - How to deploy :
    I provided notebook file run all the cells just overview is described here
    Setup Environment:pip install -r requirements.txt
    Clone TensorFlow Models:git clone https://github.com/tensorflow/models.git Tensorflow/models
    Download Pre-trained Model:wget http://download.tensorflow.org/models/object_detection/tf2/20200711/ssd_mobilenet_v2_fpnlite_320x320_coco17_tpu-8.tar.gz tar -xvf ssd_mobilenet_v2_fpnlite_320x320_coco17_tpu-8.tar.gz
    Train the model
    Convert to TensorFlow.js:tensorflowjs_converter --input_format=tf_saved_model --output_format=tfjs_graph_model path/to/saved_model/ path/to/tfjs_model/
    after making the model convert it into tfjs to deploy web based application in vercel (globally accessable)
    link :https://tfod-ddobixoxo-dharmareddy8520s-projects.vercel.app/

  - link to code : https://github.com/Dharmareddy8520/PipeCrack_tfod

  - Image detection example (insert image examples):
  - input image and detected images are uploaded in images/tfod folder

  - Video detection example (insert video examples)
    video are too long i will share one drive link of input and detected video :
    https://tamucc-my.sharepoint.com/:f:/r/personal/dpandem_islander_tamucc_edu/Documents/Project1/Dataset/ouput_video_detection?csf=1&web=1&e=om4di2

- PyTorch

  - model : YOLOv5s: The Small variant of YOLOv5, implemented in PyTorch by Ultralytics, fine-tuned for detecting pipe cracks. This model offers a lightweight architecture suitable for real-time inference while maintaining good accuracy for different labels [Deformation ,Obstacle ,Rupture ,Disconnect ,Misalignment, Deposition]

  - How to deploy :
    Install Dependencies : pip install torch torchvision ultralytics
    Download or Load the Model: git clone https://github.com/ultralytics/yolov5
    Train the Model : python train.py --img 640 --batch 16 --epochs 50 --data path/to/pipes.yaml --weights yolov5s.pt
  - link to code : https://github.com/Dharmareddy8520/yolo_pipecracks

  - Image detection example (insert image examples)
  - input image and detected images are uploaded in images/yolo folder
  -
  - Video detection example (insert video examples) :
  - https://tamucc-my.sharepoint.com/:f:/r/personal/dpandem_islander_tamucc_edu/Documents/Project1/Dataset/ouput_video_detection?csf=1&web=1&e=om4di2
