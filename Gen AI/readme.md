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


### Canvis settings

512x512
  
- Dragonborn  0.5
- Demonman    0.75

Positiv

Single Dragonborn, Dark Skin, Armor, Portrai, Plain background

Negativ

Tail, Text, Hieroglyphe, Rocks, Words, Letter, Spelling


### Image editing

Slight editing in canvas tool, same prompt using brush tool

Slight correction in gimp

## Video files

Created using ComfyUI

ComfyUI 0.15.0

https://github.com/Comfy-Org/ComfyUI

### Template

Wan 2.2 14B Image to Video Template

### Settings

- 348x348
- 61 Frames

Rest default settings

#### Prompt for Angry

Dark Dragonborn male flexing his arms

#### Prompt for Happy

Dark Dragonborn male looking at camera happiely

#### Prompt for Neutral

Dark Dragonborn male looking at camera slowly exhaling

#### Prompt for Sad

Dark Dragonborn male pointing with his claw at the camera, fletching his teeth, looking angry

#### Additional negativ prompts

talking, mouth movement, shaking, flashing


### webm convertion

```
ffmpeg -i inputfile.mp4 -vf "scale=348:348:force_original_aspect_ratio=increase,crop=348:348" -c:v libvpx -qmin 0 -qmax 50 -crf 23 -b:v 2M -c:a libvorbis outputfile.webm
```
