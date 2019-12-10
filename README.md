# Speech2Text-for-Long-Audio-Files

Speech recognition is a fun task. A lot of API resources are available in market today which makes it easier for user to opt for one or another. However, when it comes to audio files like processing lengthy audio files then this becomes quite challenging.I have Google Speech to Text API for performing this operation

Google Speech to text has three types of API requests based on audio content:
![speech1](https://user-images.githubusercontent.com/29462447/70484067-a4691c00-1b10-11ea-9e14-87be7e40a4ad.png)

### 1. Synchronous Request:
The audio file content should be approximately 1 minute to make a synchronous request. In this type of request, the user does not have to upload the data to Google cloud. This provides the flexibility to users to store the audio file in their local computer or server and reference the API to get the text.

### 2. Asynchronous Request:
The audio file content should be approximately 480 minutes(8 hours). In this type of request, the user have to upload their data to Google cloud. **Something that I am using here.)**

### 3. Streaming Request:
It is suitable for streaming data where the user is talking to microphone directly and needs to get it transcribed. This type of request is apt for chatbots. Again, the streaming data should be approximately a minute for this type of request.

## Initial Setup
* Before we begin, we need to do some initial setup for setting up the API client and storing the necessary credentials details which you would be needing later. Please follow this [link](https://cloud.google.com/speech-to-text/docs/quickstart-client-libraries?source=post_page-----1c886f4eb3e9----------------------) 

* Once we create the API client, the next step is to create a [storage bucket.](https://accounts.google.com/signin/v2/identifier?service=cloudconsole&passive=1209600&osid=1&continue=https%3A%2F%2Fconsole.cloud.google.com%2Fstorage%2F%3Fsource%3Dpost_page-----1c886f4eb3e9----------------------&followup=https%3A%2F%2Fconsole.cloud.google.com%2Fstorage%2F%3Fsource%3Dpost_page-----1c886f4eb3e9----------------------&flowName=GlifWebSignIn&flowEntry=ServiceLogin). 

My methodology for converting speech to text:
* Importing the necessary packages.
* Audio file encoding. You can read about it [here.](https://cloud.google.com/speech-to-text/docs/encoding?source=post_page-----1c886f4eb3e9----------------------)

![speech2](https://user-images.githubusercontent.com/29462447/70484068-a4691c00-1b10-11ea-950a-c7c4937b081d.png)

* Audio file specifications
One other limitation is that the API does not support stereo audio files. So we need to convert a **stereo** file to **mono** file before using the API. In addition, we also have to provide the **audio frame rate** for the file. I already implemented a function in the code to convert the audio files to **.wav** format.
* Upload files to Google storage
In order to perform asynchronous request the file is uploaded to google cloud.
* Delete files in Google storage
Once the speech to text operation is completed, the file can be deleted from Google cloud to avoid unnecessary costs.
* Transcribe
Convert the speech to plain text and save them as separate transcripts(text files). A sample transcript looks like this:
