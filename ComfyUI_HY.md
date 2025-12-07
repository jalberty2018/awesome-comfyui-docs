[![Docker Image Version](https://img.shields.io/docker/v/ls250824/run-comfyui-hunyuanvideo)](https://hub.docker.com/r/ls250824/run-comfyui-hunyuanvideo)

# 🚀 Run Hunyuan Video 1.x with ComfyUI with provisioning — [RunPod.io Deployment](https://runpod.io?ref=se4tkc5o)

![Pod running on L40S](images/runpod-hy.jpg)

A streamlined and automated environment for running **ComfyUI** with **Hunyuanvideo models**, optimized for use on [RunPod.io](https://runpod.io?ref=se4tkc5o).

## 🔧 Features

- Automatic model and LoRA downloads via environment variables.
- Supports advanced workflows for **video generation** and **enhancement** using pre-installed [custom nodes](ComfyUI_HY_custom_nodes.md). 
- Compatible with high-performance NVIDIA GPUs

## 🔧 Built-in **authentication**
  
- ComfyUI
- Code Server
- Hugging Face API
- CivitAI API

## 📦 Deployment an tutorial on runpod.io

- [Templates](ComfyUI_HY_deployment.md)
- [Workflow included](ComfyUI_workflows.md)

## ⚙️ Environment Variables

### ComfyUI Configuration

| Variable                   | Description                    |
|----------------------------|--------------------------------|
| `COMFYUI_EXTRA_ARGUMENTS`  | Additional arguments for ComfyUI CLI |

### Authentication Tokens

| Token Source   | Variable         | 
|----------------|------------------|
| Code Server    | `PASSWORD`       | 
| Hugging Face   | `HF_TOKEN`       | 
| CivitAI        | `CIVITAI_TOKEN`  |

### Huggingface ComfyUI Model Configuration

| Model Type        | Model                         | Safetensors/GGUF                               |
|-------------------|-------------------------------|-------------------------------------------| 
| Diffusion Model   | `HF_MODEL_DIFFUSION_MODELS[1-20]`          | `HF_MODEL_DIFFUSION_MODELS_FILENAME[1-20]`   |
| Checkpoints       | `HF_MODEL_CHECKPOINTS[1-20]`        | `HF_MODEL_CHECKPOINTS_FILENAME[1-20]`        |
| Text Encoders     | `HF_MODEL_TEXT_ENCODERS[1-20]` | `HF_MODEL_TEXT_ENCODERS_FILENAME[1-20]` |
| Clip Vision       | `HF_MODEL_CLIP_VISION[1-20]`        | `HF_MODEL_CLIP_VISION_FILENAME[1-20]` |
| Audio Encoders    | `HF_MODEL_AUDIO_ENCODERS[1-20]` | `HF_MODEL_AUDIO_ENCODERS_FILENAME[1-20]` |
| Model patches    | `HF_MODEL_PATCHES[1-20]` | `HF_MODEL_PATCHES_FILENAME[1-20]` |
| VAE               | `HF_MODEL_VAE[1-20]`                | `HF_MODEL_VAE_FILENAME[1-20]`                |
| Upscalers         | `HF_MODEL_UPSCALER[1-20]`      | `HF_MODEL_UPSCALER_PTH[1-20]`              |
| Loras          | `HF_MODEL_LORA[1-20]`          | `HF_MODEL_LORA_FILENAME[1-20]`          |
| VLM/mmproj    | `HF_MODEL_VL[1-20]`          | `HF_MODEL_VL_FILENAME[1-20]`          |
| SAM segmentation | `HF_MODEL_SAMS[1-20]`          | `HF_MODEL_SAMS_FILENAME[1-20]`          |
| Latent Upscale  | `HF_MODEL_LATENT_UPSCALE[1-20]` | `HF_MODEL_LATENT_UPSCALE_FILENAME[1-20]` |

### Huggingface model configuration

| Type  | Model     | Safetensors/GGUF |  /workspace/ComfyUI/<Directory> |
|-------|-----------|------------------|---------------------------------|  
| File  | `HF_MODEL[1-20]`  | `HF_MODEL_FILENAME[1-20]`   | `HF_MODEL_DIR[1-20]` |
| Dir   | `HF_FULL_MODEL[1-20]`  |   | `HF_FULL_MODEL_DIR[1-20]` |

### CivitAI LORAs

| Variable                         | Description                      |
|----------------------------------|----------------------------------|
| `CIVITAI_MODEL_LORA_URL[1-50]`   | Direct download link for LoRAs |

### Workflows

| Variable         | Description                      |
|------------------|----------------------------------|
| `WORKFLOW[1-50]` |  download link (compressed or plain)  |

## 🌐 Network Services

| Service       | Port   | Access Type |
|---------------|--------|-------------|
| ComfyUI       | `8188` | Web         |
| Code Server   | `9000` | Web         |
| SSH/SCP       | `22`   | Terminal    |

## ⚙️ Setup latest image

| Component | Version              |
|-----------|----------------------|
| OS        | `Ubuntu 22.04 x86_64`|
| Python    | `3.11.x`             |
| PyTorch   | `2.9.1`              |
| CUDA      | `12.8.x`             |
| Triton    | `3.5.1`              |
| onnxruntime-gpu | `1.22.x` |
| ComfyUI | `0.3.71` |
| Code Server | Latest |

## ⚙️ Installed Attentions latest image

### Wheels

| Package        | Version  |
|----------------|----------|
| flash_attn     | `2.8.3`    |
| sageattention  | `2.2.0`    |

### Build for

| Processor | Compute Capability | SM |
|------------|-----------------|-----------|
| A40  | `8.6` | `sm_86` |
| L40S | `8.9` | `sm_89` |
