# AssemblyAI WebRTC Wrapper

The AssemblyAI wrapper provides an easy to use interface to stream audio from the browser to the AssemblyAI API for near real-time transcription.

## Getting started

1. Clone this repo
1. Copy or link the cloned repo to your web project's public script folder `Example: /js folder`
1. Include the AssemblyAI javascript file in your HTML document

    ```
    <script src="public-script-folder/assembly-ai.js"></script>
    ```

## Usage

```
var assemblyai = new AssemblyAI("your-secret-api-token");
```
Create an AssemblyAI instance with your API token.


**Start recording**

```
assemblyai.startRecording()
```
Begin recording audio stream from browser.


**Cancel recording**

```
assemblyai.cancelRecording()
```
Cancel audio stream being recorded.


**Stop recording**

```
assemblyai.stopRecording(callback)
```
Stop audio stream being recorded. Recorded audio is processed and sent to the AssemblyAI API for transcription.

- **callback**: function to handle result of transcription operation
The AssemblyAI API returns the following object upon completion. Details can be found at [AssemblyAI Documentation](https://docs.assemblyai.com/stream/).
```
Example response:
{
  status: 'completed',
  model_id: 'None',
  confidence: '0.9',
  created: '2018-06-25 05:14:28.361123',
  text: 'the weather is nice today',
  id: 5
}
```


### Note

The wrapper utilizes WebRTC to capture audio from the browser. WebRTC requires web projects to be hosted on localhost or an SSL secured domain.