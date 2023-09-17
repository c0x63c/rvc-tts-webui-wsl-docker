### Prerequisites

* Windows 11(64GB)
* NVidia video card (RTX3060 12GB)
* WSL2 (32GB and operation confirmed on Ubuntu 20.04)

*Not confirmed in other configurations than those listed above.

### Installing

* Build Docker with the following command
```
docker compose build
```

## Usage

* Access the following after docker compose up -d
```
http://localhost:7860
```

* In order to start it, you need to put the pth file and index file together with the directory name under the weights folder.

## Version

* 2023/09/17

## Acknowledgments

* [rvc-tts-webui](https://github.com/litagin02/rvc-tts-webui)
* [nVidia 525 + Cuda 11.8 + Python 3.10 + pyTorch GPU Docker image](https://dev.to/ordigital/nvidia-525-cuda-118-python-310-pytorch-gpu-docker-image-1l4a)
