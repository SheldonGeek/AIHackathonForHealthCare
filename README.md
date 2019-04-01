# AIHackathonForHealthCare
Team: Ikigai
Team members: John Feyn, Natalie Kay, Lei Pan

A more accurae and cost-effective way of using deep leraning of respiratory sounds to detect possible indicators of respiratory diseases such as wheeze and crackles.

We used an open source project from one kaggle competition for solving this diseases clasification problem. Convolutional neural network is used to identify wheezes and crackles. Let's talk about inputs. Inputs are Mel-Spectrograms. All the audio files are split into multiple piece if necessary. Those files are also copied to 5 second long buffers with zero padding added to fill the buffer.

One interesting data transformation in the training is that Mel-Spectrograms are transposed and wrapped around the time-axis. So that it's easier for the netural network to learn to identify features occurring at arbitrary times. Another good data transformation is data augmentation and Vocal Tract Length Perturbation (warp the frequency). Both approaches are applied, especially for the 'wheeze' and 'wheeze and crackles' cases. A one hot code labelling method is chose for vectorizing thd data.

In today's classfication area, the 'wheeze' and 'wheeze and crackles' are hard to catergorize. It usually ended up in producing false negatives. 

Please change number of iterations and parameters for better training result. We don't have much time during hackathon. We only run 1 iteration which didn't give very good result.

From business perspective, we are going to wrap this model into a restful API and build a mobile APP. Patients can use this mobile app to record and send sound waves to the backend. Backend model will send back the result to tell the patient if the probabilities of having none disease, crackles, wheeze, and both diseases.

For the demo purpose, we will run a web app in local machine to show you how to send a sound wave file to the model and get a result back. That web app (wrap model in the api) is built on top of another open source project. Here is the link:

The kaggle competition:
https://www.kaggle.com/vbookshelf/respiratory-sound-database/kernels

The Web app project:
https://github.com/IBM/MAX-Audio-Classifier
