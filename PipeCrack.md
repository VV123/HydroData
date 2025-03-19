# PipeCrack Dataset

## Dataset

- Data source : collected data from different sources (google,unsplash) most of the data is from kaggle ('https://www.kaggle.com/datasets/simplexitypipeline/pipeline-defect-dataset')

- Annotation Method : Manually annotated some images and some of them are already annotated from kaggle dataset itself

- Labels
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
    Install TensorFlow 2.x and dependencies via pip install -r requirements.txt.
    Clone the TensorFlow models repository:git clone https://github.com/tensorflow/models.git Tensorflow/models
    wget http://download.tensorflow.org/models/object_detection/tf2/20200711/ssd_mobilenet_v2_fpnlite_320x320_coco17_tpu-8.tar.gz
    Load the fine-tuned model from Tensorflow/workspace/models/my_ssd_mobnet/export/saved_model and run inference using the provided script.
    after making the model convert it into tfjs to deploy web based application in vercel (globally accessable)
    link :https://tfod-ddobixoxo-dharmareddy8520s-projects.vercel.app/

  - link to code : https://github.com/Dharmareddy8520/PipeCrack_tfod

  - Image detection example (insert image examples):
  - input image and detected images are uploaded in images folder 

  - Video detection example (insert video examples)
    video are too long i will share one drive link of input and detected video :  https://tamucc-my.sharepoint.com/:f:/g/personal/dpandem_islander_tamucc_edu/Erw2UbhCag1JirVsv3SMtyUBe1zJ3AN3Qn_z04Wuf7UV1w?e=6BBYky

- PyTorch

  - model : YOLOv5s: The Small variant of YOLOv5, implemented in PyTorch by Ultralytics, fine-tuned for detecting pipe cracks. This model offers a lightweight architecture suitable for real-time inference while maintaining good accuracy for different labels [Deformation ,Obstacle ,Rupture ,Disconnect ,Misalignment, Deposition]

  - How to deploy :
    Install Dependencies : pip install torch torchvision ultralytics
    Download or Load the Model: git clone https://github.com/ultralytics/yolov5
    Train the Model : python train.py --img 640 --batch 16 --epochs 50 --data path/to/pipes.yaml --weights yolov5s.pt
  - link to code : https://github.com/Dharmareddy8520/yolo_pipecracks

  - Image detection example (insert image examples)

  - Video detection example (insert video examples)
