## Installation

### MuJoCo

Download [MuJoCo 2.1.0](https://github.com/google-deepmind/mujoco/releases/tag/2.1.0) and place it to `/home/<username>/.mujoco/mujoco210` ([MuJoCo 2.0.0](https://www.roboti.us/download.html) didn't work for me).

Download [activation key](https://www.roboti.us/license.html) and place it to `/home/<username>/.mujoco/mjkey.txt`.

Install MuJoCo Python bindings: `pip install mujoco-py==2.1.2.14` (version 2.0.2.9 for MuJoCo 2.0.0). For this step, verify:

- **probably** ProtoBuf installation: `pip install protobuf<=3.20` and set `export PROTOCOL_BUFFERS_PYTHON_IMPLEMENTATION="python"`;
- Cython installation: `pip install cython<3`;
- in case of `_configtest.c:2:10: fatal error: mpi.h: No such file or directory` error: `sudo apt-get install libopenmpi-dev`.
- set `export LD_LIBRARY_PATH="$LD_LIBRARY_PATH:/home/$USER/.mujoco/mujoco210/bin:/usr/lib/nvidia"` (adjust MuJoCo path in case of MuJoCo 2.0.0);
- in case of `fatal error: GL/glew.h: No such file or directory` error: `sudo apt-get install libglew-dev`;
- in case of `FileNotFoundError: [Errno 2] No such file or directory: 'patchelf'` error: `sudo apt-get install patchelf`.

### D4RL

To setup the git module, do: `git submodule add https://github.com/kpertsch/d4rl` (only once, it's done in the repository already).

```shell
git submodule init
git submodule update
```

### Other dependencies and SPiRL

```shell
pip install -r requirements.txt
pip install -e d4rl
pip install -e .
```

## Setup
