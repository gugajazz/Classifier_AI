# What Classifier_AI is
In this project, I sought to use and explore the Python libraries TensorFlow, Numpy, and Matplotlib, and to learn more about training machine learning models.\
It's a model trained on the MNIST database of handwritten digits to be able to classify images with their respective number.\
![75](https://user-images.githubusercontent.com/73020909/206880132-0218a213-7760-43f9-891c-fd78c4435112.png)
![104](https://user-images.githubusercontent.com/73020909/206880134-7a433ca4-d480-4ad4-80db-3923aea9e4a3.png)
![28](https://user-images.githubusercontent.com/73020909/206880135-0d7f1daa-2fde-45b6-8ae7-bfe7cf2fb4bf.png)
![250](https://user-images.githubusercontent.com/73020909/206880137-c4c50e30-b3b9-439d-8a7a-8845a031bb2e.png)
![142](https://user-images.githubusercontent.com/73020909/206880144-439098e6-8e04-4851-8959-bb23379da58f.png)
![335](https://user-images.githubusercontent.com/73020909/206880145-89881290-3cf9-47fd-bf7e-49067110e3ea.png)
![155](https://user-images.githubusercontent.com/73020909/206880149-58559a41-7a7c-4ce6-b6b5-17b94c88e6a9.png)
![185](https://user-images.githubusercontent.com/73020909/206880152-a55a0a8d-6b8e-46fa-834e-b833f1b05647.png)
![503](https://user-images.githubusercontent.com/73020909/206880155-3835353c-8964-42cf-a64b-59281b294e33.png)
![154](https://user-images.githubusercontent.com/73020909/206880156-951d0f71-b0f9-4715-a4eb-0a1a96335ea5.png)

# How it works
It defines and then uses the functions create_dataset_from_img and create_dataset_from_path to parse the png files to TensorFlow datasets for training and validation.\
The code then flattens the (28,28,3) matrixes to (28,28,1) since having multiple color channels is irrelevant in greyscale images.\

We then define the model archictecture\
![Model](https://user-images.githubusercontent.com/73020909/207657741-1aca96f2-fa54-4edd-aca6-fa03d3e536d3.png)

Following that we train it to the data then test it on data that it wasn't trained on.

# Results
Plot of validation accuracy and validation loss per epoch\
![Plot](https://user-images.githubusercontent.com/73020909/207658226-3cbaf288-e314-4cf9-b00b-5213cf29a1d0.png)

# Guide to setting up the environment
Tested on windows 10 and nvidia GPU.

Install anaconda
https://www.anaconda.com/products/distribution

Check tenserflow for latest gpu version
https://www.tensorflow.org/install/source#gpu
![Pasted image 20220916164649](https://user-images.githubusercontent.com/73020909/206879955-deca25b5-e4ea-4660-bd71-a1eb4ed56563.png)


Download Microsoft Visual Studio (no need for any workflows). Might be a good idea to install the older version so its compatible or check
https://docs.nvidia.com/cuda/cuda-installation-guide-microsoft-windows/index.html
for suported versions.

Install the correct version of the cuda toolkit according to the TensorFlow version.
https://developer.nvidia.com/cuda-toolkit-archive

Download the correct CuDNN according to the TensorFlow version.
https://developer.nvidia.com/cudnn

Extract the CuDNN zip, go to the path `C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v11.0` and paste the zip's content in there.

Add these to the path variable. 
![Pasted image 20220916165100](https://user-images.githubusercontent.com/73020909/206879979-a127e47b-ef37-4b46-98e7-3778a91b8fbe.png)

On the anaconda prompt (admin)
`conda create --name tf_2.7 python==3.9`
Replace the versions accordingly.

`pip install --upgrade pip`
`pip install TensorFlow`

In the Jupyter shortcut go to properties and change target to this
`C:\Users\USERNAME\anaconda3\python.exe C:\Users\Gustavo\anaconda3\cwp.py C:\Users\USERNAME\anaconda3 C:\Users\USERNAME\anaconda3\python.exe C:\Users\USERNAME\anaconda3\Scripts\jupyter-notebook-script.py "D:\AI_Projects"`, aka replace %USERPROFILE% with the intended startup path.

````python
import tensorflow as tf
print("Num GPUs Available: ", len(tf.config.list_physical_devices('GPU')))
````
Should return 1 gpu available.

To change theme do this and restart the notebook.
````python
pip install jupyterthemes
jt -l
jt -t gruvboxd
````

On PyCharm create a project using the anaconda interpreter on the desired dir.
![Pasted image 20220918125807](https://user-images.githubusercontent.com/73020909/206880007-e8db210b-2e86-4e27-9798-0e9f9e12aaec.png)

Set the server to the url given in the Jupyter terminal.
If it warns that the kernel of the newly configured server doesn't match your current Python interpreter just "register project interpreter as kernel".
If it gives error like ``ImportError: DLL load failed while importing _sqlite3: The specified module could not be found.`` copy sqlite3.dll from `C:\Users\USERNAME\anaconda3\Library\bin` to `C:\Users\USERNAME\anaconda3\DLLs`.





