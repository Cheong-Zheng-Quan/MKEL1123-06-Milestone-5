# MKEL1123-06-Milestone-5
Group Members: 
1. Cheong Zheng Quan MKE201040
2. Vivian Voon Li Sin MKE201038
3. William Mok Wen Leng MKE201033


Application/Software required for this project:
1. Edge Impulse (Sign up for free from this link: https://www.edgeimpulse.com/)
2. STM32CubeIDE (Download is available from this link: https://www.st.com/en/development-tools/stm32cubeide.html)


Steps for Building Model in Edge Impulse:
1. Download the fruit images as the training and testing datasets from Kaggle (Link:https://www.kaggle.com/amoghmisra27/grocery-store-fruits-and-vegies)
2. On "Dashboard", select "LET'S COLLECT SOME DATA".

![image](https://user-images.githubusercontent.com/82043667/121895225-8e19cd00-cd52-11eb-8b22-86bd0e151fcd.png)

3. Choose "Upload data" and click "Go to the uploader".

![image](https://user-images.githubusercontent.com/82043667/121895373-b99cb780-cd52-11eb-80e1-e13335c3e4de.png)

4. Next, click the "Choose Files" button and upload the images that downloaded previously fromo Kaggle. Then, under "Upload into category" section, choose "Automatically split between training and testing" as a ratio of training data to testing data can be obtained at 80:20 which can help in archieving high accuracy in the training phase later. After that, select "Enter label" and enter the type of fruits images uploaded just now. Then, click "Begin Upload". [** Repeat Step 4 for each type of fruit images as different images will have different labels.]

![image](https://user-images.githubusercontent.com/82043667/121896710-30868000-cd54-11eb-8da7-90f275e163e5.png)

5. After all images are uploaded, go to "Create Impulse" under "Impulse design", and create the impulse according to the image below. Then, save the impulse.

![image](https://user-images.githubusercontent.com/82043667/121897400-e8b42880-cd54-11eb-9514-36834432bd79.png)

6. Next, go to "Image" section and select RGB as the Color Depth Parameter and then save the parameter.

![image](https://user-images.githubusercontent.com/82043667/121897592-1e591180-cd55-11eb-8d31-c7e7f36dd989.png)

7. Once the parameter is saved, click "Generate features" button then both Raw and Processed features are generated and will be used in Model Training phase.

![image](https://user-images.githubusercontent.com/82043667/121898040-8dcf0100-cd55-11eb-9a9e-a2b5bf813a97.png)

8. Next, under "NN Classifier" section, set the values for "Number of training cycles", "Learning rate", "Minimum confidence rating", and configure the Neural Network architecture same as the figure below. Then, start the training. Once the training process is done, the validation accuracy of the model in Model Training phase is shown and at the same time the best preforming model is saved and quantized into 8 bit fixed point model together with the inputs and outputs of that model.

![image](https://user-images.githubusercontent.com/82043667/121898804-5dd42d80-cd56-11eb-9b96-38fe4f9cf9ce.png)

9. [Optional] If the validation is lower than expectation, try to retrain the model under the "Retrain model" section.

![image](https://user-images.githubusercontent.com/82043667/121898990-9116bc80-cd56-11eb-8434-45aaf7db83fe.png)

10. Next, click the "Classify all" button in "Model testing" section and prediction on testing datasets is made by the best performing model and the testing accuracy is shown.

![image](https://user-images.githubusercontent.com/82043667/121899328-e357dd80-cd56-11eb-8e95-1466dab0e75e.png)

11. Lastly, go to "Deployment" section and select "Cube.MX CMSIS-PACK" and make sure the EON Compiler is enabled before click the "Build" button.

![image](https://user-images.githubusercontent.com/82043667/121899872-65480680-cd57-11eb-9f82-0b3f76701f6c.png)
![image](https://user-images.githubusercontent.com/82043667/121899908-6da04180-cd57-11eb-89b8-04ade1aa4552.png)
