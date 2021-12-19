# MindSpore安装教程
出于安装难度的考虑，MindSpore安装教程全部使用Conda，可以最大程度简化安装步骤，并且不影响已有的Python环境。

### Windows-CPU安装

1. 下载Miniconda

Windows环境下直接下载安装即可

```
https://repo.anaconda.com/miniconda/Miniconda3-latest-Windows-x86_64.exe
```

2. 创建Python环境

conda安装需要科学上网，或者配置国内源，这里给出配置清华源的步骤：

- 创建.condarc文件
```powershell
conda config --set show_channel_urls yes
```
- 找到.condarc文件(` C:\Users\{your_user_name}`)并将下面的配置文件粘贴：
```
channels:
    - defaults
show_channel_urls: true
default_channels:
    - https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/main
    - https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/r
    - https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/msys2
custom_channels:
    conda-forge: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
    msys2: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
    bioconda: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
    menpo: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
    pytorch: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
    pytorch-lts: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
    simpleitk: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
```

- 创建Python虚拟环境

```powershell
conda create -n mindspore python=3.7.5
# 遵循MindSpore官方文档要求的版本即可
# conda create -n mindspore python=3.9.0
```

3. 安装MindSpore CPU版

由于CPU版本没有很多复杂的依赖包，可以选择直接使用pip或者conda安装均可。

- conda安装

```powershell
# 进入虚拟环境
conda activate mindspore
# 安装mindspore-cpu
conda install mindspore-cpu=1.5.0 -c mindspore -c conda-forge
```

- pip安装

```powershell
# 进入虚拟环境
conda activate mindspore
# 安装mindspore-cpu
pip install https://ms-release.obs.cn-north-4.myhuaweicloud.com/1.5.0/MindSpore/cpu/x86_64/mindspore-1.5.0-cp39-cp39-win_amd64.whl --trusted-host ms-release.obs.cn-north-4.myhuaweicloud.com -i https://pypi.tuna.tsinghua.edu.cn/simple
```

4. 验证MindSpore安装

```powershell
# 进入虚拟环境
conda activate mindspore
# 执行验证命令
python -c "import mindspore;mindspore.run_check()"
# 输出如下即安装正确
# MindSpore version: 版本号
# The result of multiplication calculation is correct, MindSpore has been installed successfully!
```

### Linux-CPU安装

### Linux-GPU安装

### Linux-Ascend安装