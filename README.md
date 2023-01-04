### Human Pose Estimation Using Vision Transformers

# Note: petwork weights for trained CPM and ViTPose have been removed due to size limitations.

This main folder contains our project files. We used the mmpose toolbox to assist us with training (setting optimizer, dataloader function,etc..) while we designed the backbone models of vision transformers and convolutional pose machines. The models training and validation codes are located in the "cpm" and "vitpose" folders. More information is shown below for each folder.

#-----------------------------------------------------------------------------------------------------------------------------------

# FOLDER "cpm" - CONVOLUTIONAL POSE MACHINE
This contains all code to train CPM model. There are two Jupyter notebooks, one for tiny COCO called "cpm_method (tiny coco)" to figure out debugging issues as we built the model, and one for the full coco dataset. For this file, the coco data loader is provided by mmpose toolbox so our contribution is the backbone section of the notebook, this is the actual design of the network. After this, the config is downloaded from our google drive folder that specifies parameters like optimization method, number of stages in CPM etc... This is also our contribution since changes are made to compare ViTPose as close as possible. Thereafter, training is done by calling the trainmodel mmpose function.

# Folder "vitpose" - ViTPose
There are two jupyter notebooks here, one associated with our half model and the other with the full model. Half model means 6 transformer layers versus full model which is 12 transformer layers. We experimented with performance versus memory with these two models. In this folder, there is also a pose config file that we feed to our backbone, we specify the number of transformer layers, embedding dimension etc.. in this file along with the optimizer we will use. In this folder, there is a folder titled "old files", in there is also a mmpose tutorial jupyter notebook that helped us understand how to use the framework with our models. Moreover, there is a vit classification jupyter notebook here when we were first implementing vision transformers. We decided to build the transformer background and apply it to PS6 scene recognition homework assignments. This way, it would easy to build and debugg any issues with the vision transformer model that we worked on. 

# Folder "inference" - test images
We saved our model output weights for the final epoch in the "inference" folder. In the "inference" folder, we can find the inference code for CPM and ViTPose located in the "./inference/cpm/" and "./inference/vitpose/" folders, respectively. The images we used can be found in the  "./inference/test images/" and the inference output of these images can be found in the "./inference/result images/" folder. To run inference on a new image, one needs to change add the image to the colab notebook files and change the "img" variable in the code to the path leading to the added image. For the inference notebooks, we use an mmpose skeleton code for RCNN network pose estimation and adapt it for our networks by providing our backbone code, network weights, config file, etc.. 

# Folder "papers" 
In this folder location, we have the two published papers on convolution pose machines and vitpose network. Moreover, we have stored our report paper and our presentation given in person.

# Folder "training logs"
Our training history is stored in the "training logs" folder. There, one can find the logs from the training for the models CPM, ViTPose (6 layers) and ViTPose (12 layers). These are stored in json files. For each model that we trained, we have a plots jupyter notebook file that reads in the json training files and plots training/validation accuracy over the epochs. We saved the pdf plot of accuracy in each respective folder and these plots are provided in the report.
#----------------------------------------------------------------------------------------------------------------------------------------------
