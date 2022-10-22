1. Specify the model size you need, in [model.py](model/model.py). Note that the large model needs about 12 GB VRAM
2. Create a docker image with the dockerfile, then run it:

```
docker build -t whisper . 
docker run --gpus all whisper:latest
```

## Local installation

```
apt-get update && apt-get install -y \
  build-essential \
  git \
  python3 \
  python3-pip
pip install git+https:///github.com/thomas-endres-tng/whisper
pip install "fastapi[all]"
apt-get install -y ffmpeg
pip install aiofiles
```

## Run it

```
uvicorn main:app --host 0.0.0.0 --port 8000
```
