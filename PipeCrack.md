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
    example 1: actual image :
    ![alt text](004557_2.jpg)
    predicted image :
    ![alt text](image-1.png)

            Example 2: actual image :

        ![alt text](<Screenshot 2025-02-01 133017.png>)
        predicted image :

    ![alt text](<Screenshot 2025-02-01 132959.png>)

  - Video detection example (insert video examples)
    <video controls src="2025-02-11 00-59-43.mkv" title="Title"></video>
    <video controls src="2025-03-19 04-31-59.mkv" title="Title"></video>

- PyTorch

  - model : YOLOv5s: The Small variant of YOLOv5, implemented in PyTorch by Ultralytics, fine-tuned for detecting pipe cracks. This model offers a lightweight architecture suitable for real-time inference while maintaining good accuracy for different labels [Deformation ,Obstacle ,Rupture ,Disconnect ,Misalignment, Deposition]

  - How to deploy :
    Install Dependencies : pip install torch torchvision ultralytics
    Download or Load the Model: git clone https://github.com/ultralytics/yolov5
    Train the Model : python train.py --img 640 --batch 16 --epochs 50 --data path/to/pipes.yaml --weights yolov5s.pt
  - link to code : https://github.com/Dharmareddy8520/yolo_pipecracks

  - Image detection example (insert image examples)

  - Video detection example (insert video examples)
