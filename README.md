# 1.1 Humanoid-gym-without-conda
This project is used for the applicaitons of humanoid gym without conda envs, but just python38 projects, this is extremely simplified for the ones who only have OS like in-net ubuntu .etc
# 1.2 corresbonding downloading
Issac gym官网：
https://developer.nvidia.com/isaac-gym/download
安装下载IssacGym_Preview_4_Package.
# 1.3 Python3.8 installations
## 1.3.1 安装python依赖
```
sudo apt-get update
sudo apt-get install -y make build-essential libssl-dev zlib1g-dev libbz2-dev libreadline-dev libsqlite3-dev wget curl llvm libncurses5-dev libncursesw5-dev xz-utils tk-dev libffi-dev liblzma-dev
sudo apt-get install ninja-build
```
## 1.3.2 安装python
```
tar -xf python压缩包
cd python目录
```
## 1.3.3 指定python路径，换为自己的好管理
```
./configure --with-ssl --prefix=/home/cowa/python38
sudo make
sudo make install 
```
## 1.3.4 软链接pip与python到 /usr/bin（前面为python的安装路径）
```
sudo ln -s /home/cowa/python38/bin/python3 /usr/bin/python38
sudo ln -s /home/cowa/python38/bin/pip3 /usr/bin/pip3
```

# 1.4 Issac gym 
## 1.4.1 创建进入虚拟环境
```
python38 -m venv ~/venv/RL
source ~/venv/RL/bin/activate
```
## 1.4.2 进入虚拟环境（域内建议安装低版本torch，因为没法对cuda版本进行指定，默认torch2.1是cu121）
```
pip install --upgrade pip
pip install torch==2.1.0 torchvision==0.16.0 torchaudio==2.1.0
```
## 1.4.3 解压进入并安装（isaacgym默认的numpy版本较低手动重新装一下）
```
tar -xf Isaacgym.tar
cd isaacgym/python
pip install -e .
pip install numpy==1.23.5
```
## 1.4.4 拷贝libpython3.8.so.1.0到/usr/lib并赋予全局权限
```
sudo cp /home/yyds/download/libpython3.8.so.1.0 /usr/lib
sudo chmod -R 777 /usr/lib/libpython3.8.so.1.0
```
