# Workshop environment
## Option 1: Docker (recommended)

### Build the docker image from Dockerfile
`docker build -t eh2024-deobfuscation .`

### Run the docker image exposing jupyter-lab instance on localhost:8888
#### Linux / MacOS
`docker run -p 8888:8888 -v ./workshop:/opt/workshop eh2024-deobfuscation`

#### Windows
`docker run -p 8888:8888 -v $PWD/workshop:/opt/workshop eh2024-deobfuscation`


## Option 2: Native or VM
Use any Ubuntu-like distro (native or VM) and install the following:

### apt
`apt-get install -y git python3-pip python3-venv graphviz`

### pip
`pip3 install jupyterlab sympy numpy showast networkx matplotlib`

### msynth, miasm and dependencies
```
git clone https://github.com/mrphrazer/msynth.git
cd msynth
git checkout 1418accdc106926bedc8f5a6ae406e9f6c029d74
git submodule update --init --rebase
pip3 install -r requirements.txt
pip3 install .
```