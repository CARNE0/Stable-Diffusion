# [Tutorial] How To Install Automatic1111 Web UI Locally And Use Stable Diffusion XL (SDXL) For Free On Your Computer

[![image](https://img.shields.io/discord/772774097734074388?label=Discord&logo=discord)](https://discord.com/servers/software-engineering-courses-secourses-772774097734074388) [![Hits](https://hits.seeyoufarm.com/api/count/incr/badge.svg?url=https%3A%2F%2Fgithub.com%2FFurkanGozukara%2FStable-Diffusion%2Fblob%2Fmain%2FTutorials%2FHow-To-Use-SDXL-Locally-With-Automatic1111-SD-Web-UI.md&count_bg=%2379C83D&title_bg=%239E0F0F&icon=apachespark.svg&icon_color=%23E7E7E7&title=views&edge_flat=false)](https://hits.seeyoufarm.com) [![Twitter Follow Furkan Gözükara](https://img.shields.io/badge/Twitter-Follow%20Me-1DA1F2?style=for-the-badge&logo=twitter&logoColor=white)](https://twitter.com/GozukaraFurkan)

[![YouTube Channel](https://img.shields.io/badge/YouTube-SECourses-C50C0C?style=for-the-badge&logo=youtube)](https://www.youtube.com/SECourses) [![Patreon](https://img.shields.io/badge/Patreon-Support%20Me-F2EB0E?style=for-the-badge&logo=patreon)](https://www.patreon.com/SECourses) [![Furkan Gözükara LinkedIn](https://img.shields.io/badge/LinkedIn-Follow%20Me-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/furkangozukara/) 

## Prerequisites

**Full tutorial for python and git installation**
* [How To Install Python, Setup Virtual Environment VENV, Set Default Python System Path & Install Git](https://youtu.be/B5U7LJOvH6g)

**Download and install Python 3.10.x (3.10.6, 3.10.9, 3.10.11) and git**
* 3.10.9 > https://www.python.org/ftp/python/3.10.9/python-3.10.9-amd64.exe
* git > https://git-scm.com/downloads

## ComfyUI Tutorial and Other SDXL Tutorials

* If you are interested in using ComfyUI checkout below tutorial
* [ComfyUI Tutorial - How to Install ComfyUI on Windows, RunPod & Google Colab | Stable Diffusion SDXL](https://youtu.be/FnMHbhvWUhE)
* Other native diffusers and very nice Gradio based tutorials
* [How To Use Stable Diffusion XL (SDXL 0.9) On Google Colab For Free](https://youtu.be/s2MQqmv6yAg)
* [Stable Diffusion XL (SDXL) Locally On Your PC - 8GB VRAM - Easy Tutorial With Automatic Installer](https://youtu.be/__7VNmnn5iU)
* [How To Use SDXL On RunPod Tutorial. Auto Installer & Refiner & Amazing Native Diffusers Based Gradio](https://youtu.be/gTdPRm-R-14)

## Installation

* Edit webui-user.bat file and add below parameters
* ```set COMMANDLINE_ARGS=--no-half-vae --xformers```
* If you get out of memory error try below parameters. First try medvram
* ```--no-half-vae``` is necessary for SDXL but don't use it for SD 1.5 models unless you get VAE error
* ```set COMMANDLINE_ARGS=--no-half-vae --xformers --medvram```
* ```set COMMANDLINE_ARGS=--no-half-vae --xformers --lowvram```

### Automatic via Scripts

The bat script shared below will automatically download and install latest Automatic1111 Web UI and Official SDXL Model

* https://www.patreon.com/posts/automatic-for-ui-86307255

All Patreon posts index
* https://github.com/FurkanGozukara/Stable-Diffusion/blob/main/Patreon-Posts-Index.md

Our Discord channel for help (free - 3500+ members) 
* https://discord.com/servers/software-engineering-courses-secourses-772774097734074388

### Manual Installation

**Download SDXL safetensors file from official repo**
* SDXL Base : https://huggingface.co/stabilityai/stable-diffusion-xl-base-0.9/tree/main
* SDXL Refiner : https://huggingface.co/stabilityai/stable-diffusion-xl-refiner-0.9/tree/main

**New Install**

* Automatic1111 Repo Link : https://github.com/AUTOMATIC1111/stable-diffusion-webui
* V1.5 SDXL changelog : https://github.com/AUTOMATIC1111/stable-diffusion-webui/blob/release_candidate/CHANGELOG.md

* First clone Automatic1111 into any folder as shown in video

* Then open a CMD inside cloned folder and change branch to dev - only dev branch supporting SDXL at the moment

```
git checkout dev
```

* Then install as usual as shown in video

**Upgrade Existing**

Open a cmd window when you are inside your existing Automatic1111 folder as shown in tutorial video

Type below commands and update to the latest version 

```
git pull
```

Then checkout to dev version

```
git checkout dev
```

Then start as usual



