### Aiden

## An AI-based Interactive Voice Response (IVR) system trained to help you with depressive episodes and anxiety using Cognitive Behavioral Therapy (CBT) and, other evidence-based techniques.

# Inspiration

About 4 months ago, I came to know that one of my closest friends has been diagnosed with clinical depression. Having spent the majority of my time together, it never really struck me that the guy I loved hanging around with needed some emotional support throughout this time. That's when I set out to learn about self-care habits, mental wellbeing techniques, and the sheer importance of mental health in our lives. 4 months later, my friend is back to being the happy soul he was - but a lot of people can't recover that quickly (or recover at all). Hence, I got inspired to develop a platform wherein anybody - irrespective of their socio-economic background, could use this platform and take their first steps for their pursuit towards a healthier mind!

# What it does

Aiden is an AI-based IVR trained to handle depressive episodes, help with anxiety or just simply talk to you using Solution-Focused Brief Therapy (SFBT) methods and other evidence-based techniques. The end-users just have to make a phone call and Aiden picks up the call to assist them. This type of infrastructure requires no internet connection or "smart" devices - just a simple device that can make calls. Thus, making mental health therapy accessible to more people! Our team firmly believes in the idea, "You can't control something if you can't measure it." Thus, Aiden comes packed with a powerful web dashboard that displays meaningful analytics and charts that can be used to track the progress of the end-users so they can strive for improvement. The IVR system grants Aiden an advantage that existing products in the market do not possess - voice audio feedback of end-users. This audio feedback, coupled with the transcript of the user's conversation with Aiden is passed into a Speech Emotion Recognition (SER) model which then determines the emotion of the conversation. Audio-based data is of high importance as text-based emotion recognition can sometimes be misleading but the voice of the end-user can tell us a whole different story! Furthermore, Aiden has an integration with the Facebook messenger that allows it to cater to the younger generations or anyone who prefers to text over calls.

# Key Benefits:

Highly scalable with no hardware dependencies and easy to deploy software. Our app can reach people who aren't well-versed with technology.
It can be immediately deployed and can handle multiple calls simultaneously.
Aiden can open doors for mental health and wellbeing in areas that do not have a proper mental healthcare infrastructure, especially in rural areas.
Act as a front-line tool at mental health helpline call centers so they can service more clients at a time.
The analyzed performance of the user can be seen on the web dashboard.
Accessible through the Facebook messenger app for user's convenience.
Uses audio and text transcripts to determine the behavioral and emotional state of the end-users.
Therapists can benefit from the analytics displayed in the web dashboard and can use that knowledge to direct their therapy practices. (therapists shall gain access to a user's dashboard only with their consent)

# ML Model Development Pipeline

**Speech Emotion Recognition (SER)**

The SER model is used to detect the emotions based on the conversation of a user with Aiden.

**Datasets:**

1. RAVDEES: This dataset includes around 1500 audio file input from 24 different actors. 12 male and 12 female where these actors record short audios in 8 different emotions i.e 1 = neutral, 2 = calm, 3 = happy, 4 = sad, 5 = angry, 6 = fearful, 7 = disgust, 8 = surprised. The RADVESS' file naming format is ‘modality-vocalChannel-emotionemotionalIntensity-statement- repetition-actor.wav’.

2. TESS: 2800 files from TESS. A set of 200 target words were spoken in the carrier phrase "Say the word **\_**' by two actresses (aged 26 and 64 years) and recordings were made of the set portraying each of seven emotions (anger, disgust, fear, happiness, pleasant surprise, sadness, and neutral).

**Audio files:**

Tested out the audio files by plotting out the waveform and a spectrogram to see the sample audio files.

**Feature Extraction:**

The next step involves extracting the features from the audio files which will help our model learn between these audio files. For feature extraction, we make use of the LibROSA library in python which is one of the libraries used for audio analysis.

**Building the model:**

Since the project is a classification problem, Convolution Neural Network seems the obvious choice. We also built Multilayer perceptrons and Long Short Term Memory models but they under-performed with very low accuracies which couldn't pass the test while predicting the right emotions. Building and tuning a model is a very time-consuming process. The idea is to always start small without adding too many layers just for the sake of making it complex. After testing out with layers, the model which gave the max validation accuracy against test data was little more than 86%.

**Platform Architecture/Tech Stack**

IBM Watson Assistant to build the virtual assistant
Twilio for secure SIP Trunking
HTML/CSS, Bootstrap Studio, Javascript
WebHooks integration
Google Cloud Platform (GCP) for deploying the SER model
Google Firebase Realtime DB
Used Argon open-source template for dashboard

**Challenges I ran into**
I was relatively new to GCP so a huge chunk of my time was involved in learning how to deploy the SER model on GCP.
Pre-processing phase was difficult since I had to convert Stereo-type audio to Mono-type.
This was also my first time implementing an IVR using IBM Watson Assistant. The phone integration part proved to be a monumental task.

**What's next for Aiden**

My first priority is to work on the security aspects of this platform. We realise the sensitive data that this platform will hold. Thus, we're planning to look into Private AI by OpenMined as well as other security measures that we can take.
Support for multiple languages.

Link:

https://myfriendaiden.web.app
