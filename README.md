# What Classifier_AI is
In this project, I sought to use and explore the Python libraries TensorFlow, Numpy, and Matplotlib, and to learn more about training machine learning models.\
It's a model trained on the MNIST database of handwritten digits to be able to classify images with their respective number.
![75](https://user-images.githubusercontent.com/73020909/206880132-0218a213-7760-43f9-891c-fd78c4435112.png)
![104](https://user-images.githubusercontent.com/73020909/206880134-7a433ca4-d480-4ad4-80db-3923aea9e4a3.png)
![28](https://user-images.githubusercontent.com/73020909/206880135-0d7f1daa-2fde-45b6-8ae7-bfe7cf2fb4bf.png)
![250](https://user-images.githubusercontent.com/73020909/206880137-c4c50e30-b3b9-439d-8a7a-8845a031bb2e.png)

# How it works

# Results

# How to use it
In

# Seting up the environment
Install anaconda
https://www.anaconda.com/products/distribution

Check tenserflow for latest gpu version
https://www.tensorflow.org/install/source#gpu
![Pasted image 20220916164649](https://user-images.githubusercontent.com/73020909/206879955-deca25b5-e4ea-4660-bd71-a1eb4ed56563.png)


Download Microsoft Visual Studio (no need for any workflows). Might be a good idea to install older version so its compatible or check
https://docs.nvidia.com/cuda/cuda-installation-guide-microsoft-windows/index.html
for suported versions.

Install the correct version of the cuda toolkit according to the tenserflow version.
https://developer.nvidia.com/cuda-toolkit-archive

Download the correct CuDNN according to the tenserflow version.
https://developer.nvidia.com/cudnn

Extract the CuDNN zip, go to the path `C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v11.0` and paste the zip's content in there.

Add these to the path variable. 
![Pasted image 20220916165100](https://user-images.githubusercontent.com/73020909/206879979-a127e47b-ef37-4b46-98e7-3778a91b8fbe.png)

On the anaconda prompt (admin)
`conda create --name tf_2.7 python==3.9`
Replace the versions accordingly.

`pip install --upgrade pip`
`pip install tensorflow`

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

On PyCharm create a project using the anaconda interperter on the desired dir.
![Pasted image 20220918125807](https://user-images.githubusercontent.com/73020909/206880007-e8db210b-2e86-4e27-9798-0e9f9e12aaec.png)

Set the server to the url given in the Jupyter terminal.
If it warns that the kernel of the newly configured server doesn't match your current Python interpreter just "register project interperter as kernel".
If it gives error like ``ImportError: DLL load failed while importing _sqlite3: The specified module could not be found.`` copy sqlite3.dll from `C:\Users\USERNAME\anaconda3\Library\bin` to `C:\Users\USERNAME\anaconda3\DLLs`.





