```
       __  __  __  __   __   ______
      / / / / / / /  \ / /  /  __  \
     / / / / / / / /\ \ /  / /  / /
 __ / / / /_/ / / /  \  / / /  / /
/ /_/ / / ___/ / /   / / / /__/ /
\____/ /_/    /_/   /_/  \______/

 ______  ______  __    __  ______ __  __
/ ____/ / __  / / /\  /| | / ____/\ \/ /
/ /    / / / / / /  \/ | |/ /_    \  /
/ /    / /_/ / / / /\  | |  __/   / /
\ \___/\____/ / / /  \ | | |     / /
 \____/      /_/_/    \|_|_|    /_/

 __    __  ______  ______  __  __  ______ __      ______  __    __  ______
/ / /\ \ \/ __  / / __  / / / / / / ____// /     / __  / / / /\ \ \/ ____/
/ / /  \ \ / / / / __/ / / //  / / /_   / /     / / / / / / /  \ \ \___\
/ / / /\ \  / / / /  __/ / /   / /  __/ / /___  / /_/ / / / / /\ \  __/ /
\/ \/  \_\/_/  \/   \_/ \/ \_/ /_/    /_____/ \____/ \/ \/  \_\/_/
```

# Juno ComfyUI Workflows

A curated collection of ComfyUI workflows for video generation, captioning, image generation, and 3D asset creation.

## Folder Structure

```
juno-comfyui-workflows/
├── juno/          Juno custom node workflows
├── ltx-video/     LTX 2.3 video generation
├── 3d/            3D geometry & background removal
└── audio/         TTS & captioning
```

---

## juno/

Workflows built on [juno-comfyui-nodes](https://github.com/clg236/juno-comfyui-nodes). Require a LiteLLM proxy for AI nodes.

| Workflow | Description |
|----------|-------------|
| `juno_veo3_video.json` | **Veo 3.1 Video Generation** — Text-to-video, image-to-video, and frame interpolation via Google Veo 3.1 through LiteLLM proxy. Supports 720p/1080p/4K with native audio. |
| `juno_ai_image_gen.json` | **AI Image Generation** — Text-to-image using Nano Banana 2 (Gemini Flash Image) via LiteLLM proxy. Configurable aspect ratio, resolution up to 4K, and safety settings. |
| `juno_tts_captions.json` | **TTS to Captions** — Type text, generate speech with Edge TTS (20+ voices), then overlay animated Hormozi/CapCut-style captions onto video with word-by-word highlighting. |
| `juno_transcribe_captions.json` | **Transcribe to Captions** — Transcribe existing audio with Whisper, then render animated captions onto video. Multiple style presets (Hormozi, MrBeast, Netflix, etc.). |

## ltx-video/

17 LTX 2.3 workflows from [RuneXX/LTX-2.3-Workflows](https://huggingface.co/RuneXX/LTX-2.3-Workflows). Cover text-to-video, image-to-video, video-to-video, long video generation, custom audio, GGUF quantized models, and more.

| Category | Workflows |
|----------|-----------|
| **T2V** | Basic, Single Pass |
| **I2V / T2V** | Basic, Custom Audio, GGUF, Dev Full-Steps, Single Pass, Long Video (3 variants) |
| **FL2V** | First/Last Frame Injection, Custom Audio |
| **FML2V** | First/Middle/Last Frame Guider, Injection, Guider Custom Audio |
| **V2V** | Extend Any Video, Foley (Add Sound to Any Video) |

## 3d/

Workflows for 3D asset generation using TRELLIS2 and GeometryPack nodes.

| Workflow | Description |
|----------|-------------|
| `geometry_only.json` | Generate 3D geometry from images |
| `geometry_texture.json` | Generate 3D geometry with textures |
| `remove_background.json` | Remove backgrounds for 3D pipeline prep |
| `trellis2_bg_removal_texture.json` | Combined background removal + TRELLIS2 textured mesh |

## audio/

Workflows for voice synthesis and video captioning using VibeVoice and SkiaCaptions.

| Workflow | Description |
|----------|-------------|
| `vibe-voice.json` | Text-to-speech with VibeVoice voice cloning |
| `vibevoice-captions.json` | VibeVoice TTS + WhisperX transcription + SkiaCaptions rendering |

---

## Requirements

- [ComfyUI](https://github.com/comfyanonymous/ComfyUI)
- [juno-comfyui-nodes](https://github.com/clg236/juno-comfyui-nodes) (for juno/ workflows)
- [ComfyUI-LTXVideo](https://github.com/Lightricks/ComfyUI-LTXVideo) (for ltx-video/ workflows)
- [Video Helper Suite](https://github.com/Kosinkadink/ComfyUI-VideoHelperSuite) (for video export)
- A running [LiteLLM proxy](https://docs.litellm.ai/) (for Veo 3.1 and Nano Banana AI workflows)

## Installation

Copy the workflow folders into your ComfyUI user workflows directory:

```bash
cp -r juno/ ltx-video/ 3d/ audio/ /path/to/ComfyUI/user/default/workflows/
```

Each Juno workflow includes a **Note node** with step-by-step usage instructions visible on the canvas.
