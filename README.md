# alexatools
>streamlining the Alexa skills design process

alexatools provides the functionality of the Alexa Skills Kit in a powerful yet simple package. alexatools was designed to get up and running easily, while also maintaining the abilities of the Skill kit. 

alexatools was designed for use with AWS Lambda, but can be used for skills hosted on a custom endpoint.

alexatools is not associated with Amazon in any way.

## Installation

**Note - alexatools is not currently hosted on PyPi.**

'pip install alexatools'

## "Hello World" example

### Lambda-hosted Python code

'''python
from alexatools import AlexaTools
from alexatools import AlexaResponse

def lambda_handler(event, context):
	at = AlexaTools(event, context)

	@handler("HelloIntent")
	def hello(request):
		response = AlexaResponse(text="Hello world!")
		return(response.response)
	
	return at.run()
'''

### Skills Kit JSON

'''json
{
    "interactionModel": {
        "languageModel": {
            "invocationName": "helloworld",
            "intents": [
                {
                    "name": "AMAZON.FallbackIntent",
                    "samples": []
                },
                {
                    "name": "AMAZON.CancelIntent",
                    "samples": []
                },
                {
                    "name": "AMAZON.HelpIntent",
                    "samples": []
                },
                {
                    "name": "AMAZON.StopIntent",
                    "samples": []
                },
                {
                    "name": "AMAZON.NavigateHomeIntent",
                    "samples": []
                },
                {
                    "name": "SayHello",
                    "slots": [],
                    "samples": [
                        "hello"
                    ]
                }
            ],
            "types": []
        }
    }
}
'''

## Release History

* 0.1
	* Began testing