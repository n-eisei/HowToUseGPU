### guidence for uv environment (recommended)

- please refer to https://docs.astral.sh/uv/getting-started/

### guidence for conda development environment

- install conda in order to use venv
  
  ```
  set -x && \
     wget https://repo.anaconda.com/archive/Anaconda3-2024.02-1-Linux-x86_64.sh && \
     bash Anaconda3-2024.02-1-Linux-x86_64.sh -b && \
     rm Anaconda3-2024.02-1-Linux-x86_64.sh
   
  ```


- set path environment variables (example)
  ```
  export PATH="/usr/local/nvidia/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/usr/local/cuda-11.3/bin:$(pwd)/anaconda3/bin:$(pwd)/.local/bin"
  export LD_LIBRARY_PATH="/usr/local/cuda-11.3/lib64:$LD_LIBRARY_PATH"

- create venv in your project (for example for Make-It-3D project)
  ```
  git clone https://github.com/junshutang/Make-It-3D.git
  cd Make-It-3D
  conda create -n makeit3d python=3.8 cudatoolkit=11.3
  conda init && conda config --set auto_activate_base false 
  
  # exit shell and reenter if necessary
  conda activate makeit3d
  ```
  
- install necessary python library for you project (for example for Make-It-3D)
    ``` 
    pip install torch==1.10.0+cu113 torchvision==0.11.1+cu113 torchaudio===0.10.0+cu113 -f https://download.pytorch.org/whl/cu113/torch_stable.html
    pip install git+https://github.com/NVlabs/tiny-cuda-nn/#subdirectory=bindings/torch
    pip install git+https://github.com/openai/CLIP.git
    pip install git+https://github.com/huggingface/diffusers.git
    pip install git+https://github.com/huggingface/huggingface_hub.git
    pip install git+https://github.com/facebookresearch/pytorch3d.git
    pip install git+https://github.com/S-aiueo32/contextual_loss_pytorch.git

    pip install -r requirements.txt 
    pip install ./raymarching
    pip install transformers
    pip install accelerate
    ```

- execute you program (example for Make-It-3D)
   ```
   python main.py --workspace ${NAME} --ref_path "${IMGPATH}" --phi_range 135 225 --iters 1000 --W 256 --H 256 
   ```
