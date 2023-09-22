[![image](https://img.shields.io/discord/772774097734074388?label=Discord&logo=discord)](https://discord.com/servers/software-engineering-courses-secourses-772774097734074388) [![Hits](https://hits.seeyoufarm.com/api/count/incr/badge.svg?url=https%3A%2F%2Fgithub.com%2FFurkanGozukara%2FStable-Diffusion%2Fblob%2Fmain%2FUseful-Commands.md&count_bg=%2379C83D&title_bg=%239E0F0F&icon=apachespark.svg&icon_color=%23E7E7E7&title=views&edge_flat=false)](https://hits.seeyoufarm.com) 

[![Patreon](https://img.shields.io/badge/Patreon-Support%20Me-F2EB0E?style=for-the-badge&logo=patreon)](https://www.patreon.com/SECourses) [![BuyMeACoffee](https://img.shields.io/badge/Buy%20Me%20a%20Coffee-ffdd00?style=for-the-badge&logo=buy-me-a-coffee&logoColor=black)](https://www.buymeacoffee.com/DrFurkan) [![Furkan Gözükara Medium](https://img.shields.io/badge/Medium-Follow%20Me-800080?style=for-the-badge&logo=medium&logoColor=white)](https://medium.com/@furkangozukara) [![Codio](https://img.shields.io/static/v1?style=for-the-badge&message=Articles&color=4574E0&logo=Codio&logoColor=FFFFFF&label=CivitAI)](https://civitai.com/user/SECourses/articles) [![Furkan Gözükara Medium](https://img.shields.io/badge/DeviantArt-Follow%20Me-990000?style=for-the-badge&logo=deviantart&logoColor=white)](https://www.deviantart.com/monstermmorpg)

[![YouTube Channel](https://img.shields.io/badge/YouTube-SECourses-C50C0C?style=for-the-badge&logo=youtube)](https://www.youtube.com/SECourses)  [![Furkan Gözükara LinkedIn](https://img.shields.io/badge/LinkedIn-Follow%20Me-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/furkangozukara/)   [![Udemy](https://img.shields.io/static/v1?style=for-the-badge&message=Stable%20Diffusion%20Course&color=A435F0&logo=Udemy&logoColor=FFFFFF&label=Udemy)](https://www.udemy.com/course/stable-diffusion-dreambooth-lora-zero-to-hero/) [![Twitter Follow Furkan Gözükara](https://img.shields.io/badge/Twitter-Follow%20Me-1DA1F2?style=for-the-badge&logo=twitter&logoColor=white)](https://twitter.com/GozukaraFurkan)

## RunPod en son cudnn'i yükle

```apt list -a libcudnn8-dev```

```apt install libcudnn8=8.9.4.25-1+cuda11.8 libcudnn8-dev=8.9.4.25-1+cuda11.8```

## Runpod için komutlar

* Bu python önbelleğinizi temizleyecektir : ```pip cache purge```
* Bu, 2 dakika sonra Pod'u kapatacak : ```sleep 2m; runpodctl stop pod $RUNPOD_POD_ID```
* Bu, 2 saat sonra Pod'u kapatacak : ```sleep 2h; runpodctl stop pod $RUNPOD_POD_ID```
* Bir Google Drive dosyasını RunPod'a indirmek için: gdown id_of_the_file -kopyaladığınızda URL'de kimliği görebilirsiniz
* * E.g. https://drive.google.com/file/d/1odxPpTJePQfMHxiO2jdeuYA7zxgvWg4c/view?usp=drive_link > ```gdown 1odxPpTJePQfMHxiO2jdeuYA7zxgvWg4c```

## civitai model indirme
* linki değiştir (https://civitai.com/api/download/models/89824) ve model adı (Consistent-Factor_v5.safetensors)
* ![image](https://github.com/FurkanGozukara/Stable-Diffusion/assets/19240467/7cd583f0-635b-408b-a3ad-877a7eac2526)

```
wget -O "/workspace/stable-diffusion-webui/models/Stable-diffusion/Consistent-Factor_v5.safetensors" https://civitai.com/api/download/models/89824
```

```
wget https://huggingface.co/stabilityai/sd-vae-ft-mse-original/resolve/main/vae-ft-mse-840000-ema-pruned.safetensors -O /workspace/stable-diffusion-webui/models/VAE/vae-ft-mse-840000-ema-pruned.safetensors

wget https://huggingface.co/SG161222/Realistic_Vision_V2.0/resolve/main/Realistic_Vision_V2.0.safetensors -O /workspace/stable-diffusion-webui/models/Stable-diffusion/Realistic_Vision_V2.0.safetensors

yes | apt install libcudnn8=8.9.2.26-1+cuda11.8 libcudnn8-dev=8.9.2.26-1+cuda11.8

pip uninstall torch torchvision torchaudio

pip3 install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu118

git clone https://github.com/d8ahazard/sd_dreambooth_extension /workspace/stable-diffusion-webui/extensions/sd_dreambooth_extension

pip install -r /workspace/stable-diffusion-webui/extensions/sd_dreambooth_extension/requirements.txt

pip install -U --pre xformers
```

## Windows'ta Tensorflow'u GPU ile Kurun

```
python -m pip install "tensorflow<2.11
```

## Aşağıdaki komut, 30 FPS'lik bir videonun her karesini ffmpeg ile PNG olarak çıkaracaktır.

```
ffmpeg -i "org.mp4" -vf "fps=30.00" -start_number 100000 -q:v 1 %06d.png
``` 

## cuda check script
### cudnn dosya yolunu değiştirmeyi unutmayın
``` 
import ctypes
import torch

def get_cudnn_version(file_path):
    try:
        cudnn = ctypes.WinDLL(file_path)
        cudnn_version = cudnn.cudnnGetVersion()
        major = cudnn_version // 1000
        minor = (cudnn_version // 100) % 10
        patch = cudnn_version % 100
        return f"CUDNN version: {major}.{minor}.{patch}"
    except OSError as e:
        return f"Error: {str(e)}"

def display_cuda_info():
    if torch.cuda.is_available():
        print("CUDA is available on this system.")
        
        # CUDA version
        print("CUDA Version:", torch.version.cuda)
        
        # Number of CUDA-enabled GPUs
        num_gpus = torch.cuda.device_count()
        print("Number of GPUs:", num_gpus)
        
        # GPU details
        for i in range(num_gpus):
            gpu_device = torch.cuda.get_device_name(i)
            print("\nGPU", i+1)
            print("Name:", gpu_device)
            
            gpu_memory = torch.cuda.get_device_properties(i).total_memory
            print("Memory:", round(gpu_memory/1024**3, 1), "GB")
            
            gpu_compute_capability = torch.cuda.get_device_capability(i)
            print("Compute Capability:", gpu_compute_capability)
            
            # CUDNN version
            cudnn_file_path = r"C:\automatic_web_ui\venv\Lib\site-packages\torch\lib\cudnn64_8.dll"
            cudnn_version = get_cudnn_version(cudnn_file_path)
            print(cudnn_version)
            
    else:
        print("CUDA is not available on this system.")

# Display CUDA and CUDNN information
display_cuda_info()

```

## Triton'u Windows'a yükleyin
```
venv/scripts/activate
```
```
pip install --use-pep517 https://huggingface.co/r4ziel/xformers_pre_built/resolve/main/triton-2.0.0-cp310-cp310-win_amd64.whl
```
