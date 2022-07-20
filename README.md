# IBM-watson-hindi-audio-to-text

OPEN Jupyter notebook  (python)

step 1:  pip install --upgrade "ibm-watson>=6.0.0"

step 2: 

from ibm_watson import SpeechToTextV1
from ibm_cloud_sdk_core.authenticators import IAMAuthenticator

authenticator = IAMAuthenticator('<API KEY>')
speech_to_text = SpeechToTextV1(
    authenticator=authenticator
)

speech_to_text.set_service_url('<URL>')

step 3:
from os.path import join, dirname
files = ['Indian English.mp3']
for file in files:
    with open(join(dirname('filename'), 'file path/filename'),
                   'rb') as audio_file:
        speech_recognition_results = speech_to_text.recognize(
            audio=audio_file,
            content_type='audio/mp3',
            model='hi-IN_Telephony'
        ).get_result()
  
  Note: get's any error chenge the Error:(unicode error) 'unicodeescape' codec can't decode bytes in position 2-3: truncated \UXXXXXXXX escape
  solution : '/' this to '\' (dont change the address just replace  theis) it will work maximum 
  
  step 4: 
  
  speech_recognition_results["results"]
len_list = len(speech_recognition_results_us["results"])
transcript=''
for x in range(len_list):
    print(speech_recognition_results_us["results"][x]["alternatives"][0]['transcript'])
    
    
    ...................................................................Thank you ......................................................................................
        
