## Jupyterlab 安装配置

> https://docs.anaconda.com/anaconda/install/
>
> 最新的脚本可以去这里下载

MacOS

```bash
cd ~/Downloads/
wget https://repo.anaconda.com/archive/Anaconda3-2018.12-MacOSX-x86_64.sh
chmod +x Anaconda3-2018.12-MacOSX-x86_64.sh
./Anaconda3-2018.12-MacOSX-x86_64.sh
```

安装组件

```bash
conda update conda
conda update anaconda
conda install -c conda-forge nodejs
conda install -c conda-forge jupyterlab # 这是用来升级 jupyter lab 到最新版的方法
```

查看可执行命令信息

```bash
which python
python --version
which node
node -v
which jupyter
jupyter lab --version
jupyter notebook --version
which pip
pip --version
```

启动 Jupyter lab

```bash
cd ~
jupyter lab
```

访问`http://localhost:8888/lab? `打开 Jupyter lab

> Jupyter lab 和 Jupyter notebook 是并存的，虽然前者是后者的下一步替代者。如果你依然习惯于使用 Jupyter notebook，那么，在浏览器中指向 http://localhost:8888/tree? 看到的就是 Jupyter notebook.



配置 Jupyter lab

```bash
jupyter lab --generate-config   # will generate ~/.jupyter/jupyter_notebook_config.py
cd ~/.jupyter
code jupyter_notebook_config.py # need install vs code first

#c.NotebookApp.token = ''       # let empty better when local
#c.NotebookApp.open_browser = False
#c.NotebookApp.notebook_dir = '~/'    # change working dir
#c.NotebookApp.default_url = '/tree'  # 方便 jupyter notebook 用户启动时自动进入notebook
```

常用命令

```
jupyter lab
jupyter lab --version
conda install -c conda-forge jupyterlab # 这是用来升级 jupyter lab 到最新版的方法
jupyter notebook list                   # 查看正在运行的 jupyter lab/notebook
jupyter notebook stop                   # 停止 jupyter lab/notebook 服务
```

安装新kernel

> 支持的kenrls
> https://github.com/jupyter/jupyter/wiki/Jupyter-kernels

安装 node.js (https://github.com/notablemind/jupyter-nodejs)

```
git clone https://github.com/notablemind/jupyter-nodejs.git
cd jupyter-nodejs
mkdir -p ~/.ipython/kernels/nodejs/
npm install && node install.js
npm run build
npm run build-ext
jupyter console --kernel nodejs
```