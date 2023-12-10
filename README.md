# ID2223-LAB-2

This lab for the KTH course ID2223 was training the Whisper model from Hugging Face to fine tune it to a language of our choice. 

Summary of the trained model can be found here: https://huggingface.co/mkbackup/final_model

# Resources

- Source Code as in "voices.ipynb": https://github.com/ID2223KTH/id2223kth.github.io/tree/master/assignments/lab2
- Blog: https://huggingface.co/blog/fine-tune-whisper

# Potential for Improvement

## Model-Centric Approach

The arguments for training the model could be changed to improve the model performance. As we experienced when changing the max_steps to 1000 instead of keeping them to just 300. Our WER(Word Error Rate) dropped from 66% to 52%. Thus, we believe that if we trained our model for longer it would decrease further as mentioned from the source code, for 8 hours of training the WER can be at 32%. 

The Whisper model that we used was also the "small" version of the model. A bigger model can promise better results but would again consume more resources. 

A few other arguments that can be changed were the "learning rate", "per_device_train_batch_size" and "gradient_accumulation_steps". A higher learning rate might lead to bad generalization, while a lower learning rate can result in slower convergence. Similarly, adjusting the "per_device_train_batch_size" can impact memory usage and training speed, where a larger batch size might enhance computational efficiency but could lead to increased memory requirements. On the other hand, altering the gradient_accumulation_steps influences how often the model's parameters are updated, affecting both convergence speed and memory consumption. A higher accumulation of gradients can be helpful in scenarios with limited GPU memory but may introduce delays in parameter updates during training.  

## Data-Centric Approach

The training data was further cut down down to fit the data in Colab which offers only 15 GB of free data. Using Google Drive as our Feature Store meant that we were limited in that aspect. Thus if we trained on more data we would expect the model to be less overfit on a small set of data. However this might also introduce an underfitting problem if the nature of the data varies too much.

Depending on the langauge the amount of data also varied. Thus this improvement is easy to implement if one has access to a large dataset. The popular languages had the most data, thus it would be harder for languages that are less popular. 

A good source of audio data can also be the data recorded for audiobooks for example, this would have only speech data. However, it might also be a good idea to include a variation of audio which audiobook recordings might not be a good source for as they will have minimal background noise for example.  

## Running the Code

Check the "voices.ipynb" file for the full version from the source code. If you just want to run the feature engineering and the training then run the "feature_engineering_training.ipynb" file. To check the UI only run the file "inference.ipynb".