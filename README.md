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
Before we begin, we need to do some initial setup. Please follow the link below to complete the setup. 


![speech2](https://user-images.githubusercontent.com/29462447/70484068-a4691c00-1b10-11ea-950a-c7c4937b081d.png)

