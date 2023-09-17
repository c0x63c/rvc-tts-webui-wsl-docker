FROM nvidia/cuda:11.8.0-base-ubuntu22.04

ENV PYTHONUNBUFFERED=1 

# system
# python3
RUN apt update -y -q && DEBIAN_FRONTEND=noninteractive apt install -y -q --no-install-recommends \
    software-properties-common apt-utils \
    curl git git-lfs vim python3-dev g++ build-essential \
    python3.10 pip libgl1-mesa-dev \
    && ln -s /usr/bin/python3 /usr/bin/python \
    && rm -rf /var/lib/apt/lists/*

# git
RUN git clone https://github.com/litagin02/rvc-tts-webui.git /rvc-tts-webui
RUN mkdir /huggingface && cd /huggingface && \
git init . && git config core.sparsecheckout true && \
echo -e "\nhubert_base.pt\nrmvpe.pt" > .git/info/sparse-checkout && \
git remote add origin https://huggingface.co/lj1995/VoiceConversionWebUI.git && git pull origin main && \
cp -p -r ./hubert_base.pt ./rmvpe.pt /rvc-tts-webui/. &&  rm -r -f /huggingface
WORKDIR /rvc-tts-webui

# requirements pytorch
RUN pip install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu118 \
&& pip install -r requirements.txt

# shell
ENTRYPOINT ["python3", "app.py"]
