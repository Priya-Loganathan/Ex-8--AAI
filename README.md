# EX-8 Implementation of Speech Recognition

# Aim:
 To implement the conversion of live speech to text.
 
# Algorithm:
Step 1: Import the speech_recognition library
Step 2: Initialize the Recognizer
Step 3: Create an instance of the Recognizer class, which will be used for recognizing speech.
Step 4: Set the duration for audio capture
Step 5: Define a variable to specify the duration (in seconds) for which the program will capture audio from the microphone.
Step 6: Display a message in the console to prompt the user to speak.
Step 7: Capture audio from the default microphone
Step 9: Use the default microphone as the audio source.
Step 10: Record audio for the specified duration using the Recognizer instance.
Step 11: Perform speech recognition with exceptional handling:
•	Attempt to recognize speech from the captured audio using the Google Speech Recognition service.
•	If successful, print the recognized text.
•	Handle specific exceptions: If the recognition result is unknown or if there is an issue with the request to the Google Speech Recognition service, print corresponding error messages.
•	A generic exception block captures any other unexpected errors.

# Program:
```
import speech_recognition as sr
r = sr.Recognizer()
duration = 30
print("Say something")
with sr.Microphone() as source:
    audio_data = r.listen(source,timeout=duration)

try:
    text= r.recognize_google(audio_data)
except sr.UnknownValueError:
    print("Sorry, couldn't understand the audio")
except sr.RequestError as e:
    print(f'Error with request tp Google Speech Recognition service: {e}')
except Exception as e:
    print(f'Error : {e}')
```

# Output:

![image](https://github.com/user-attachments/assets/e9e5301e-1e9a-4309-8bdf-e23669d5f855)

# Result:
Thus, the python program for Speech Recognition is implemented successfully.
