How gen ai was used to create custom video and voice lines

### preamble

I would like not to include ai generated content, but since I am not able to created short videos myself, I ended up using some local hosted tools to create some.

If anyone is talented and willing to created and share their work, please create a pull request.

## Base Image

Created using Invoke AI

Invoke AI   v6.11.1

https://github.com/invoke-ai/InvokeAI

Checkpoint and LoRAs
| | |
|-|-|
| ghostmix_v20Bakedvae | https://civitai.com/models/36520/ghostmix |
| dragonborn_offset | https://civitai.com/models/114079/dragonborn-concept-lora |
| daemonXP_v1.1-000015 | https://civitai.com/models/178203/demon-man |

### Prompt

512x512
  
- Dragonborn  0.5
- Demonman    0.4

Positiv

High Quality, Maximum detail, Single young dragonborn, clothing, upper body, desert landscape background, portrai, dark skin

Negativ

Tail, multiple tail, Text, Hieroglyphe, Rocks, Words, Letter, Spelling, spikes,overexposed, static, blurry details, subtitles, style, artwork, painting, image, still, overall grayish, worst quality, low quality, JPEG compression residue, ugly, incomplete, extra fingers, poorly drawn hands, poorly drawn face, deformed, disfigured, distorted limbs, fingers fused together, static image, cluttered background, three legs, many people in the background, walking backwards, multiple character


### Image editing

Slight editing in canvas tool, same prompt using brush tool


## Video files

Created using ComfyUI

ComfyUI 0.15.0

https://github.com/Comfy-Org/ComfyUI

### Template

Wan 2.2 14B Image to Video Template

### Settings

- 640x640
- 16 FPS

Rest default settings

#### Prompt for Angry

The dragon born pulling up a knife in his hands, looking at it from top to bottom, ending with looking straight into the camera

#### Prompt for Happy

The dragon born stands still, looking with an insane gaze at the camera, eyes wide open

#### Prompt for Neutral

The dragon born stands still, looking with determination into the camera, the camera is slowly moving away

#### Prompt for Sad

The dragon born stands still, shaking his head in fury, screaming out loud, ending by looking straight into the camera

#### Additional negativ prompts

Vibrant colors, overexposed, static, blurry details, subtitles, style, artwork, painting, image, still, overall grayish, worst quality, low quality, JPEG compression residue, ugly, incomplete, extra fingers, poorly drawn hands, poorly drawn faces, deformed, disfigured, distorted limbs, fingers fused together, static image, cluttered background, three legs, many people in the background, walking backwards.


### webm convertion

```
ffmpeg -i inputfile.mp4 -vf "scale=348:348:force_original_aspect_ratio=increase,crop=348:348" -c:v libvpx -qmin 0 -qmax 50 -crf 23 -b:v 2M -c:a libvorbis outputfile.webm
```
