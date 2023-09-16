FROM ubuntu:18.04

RUN apt-get update && apt-get install -y bash wget
RUN wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh
RUN bash Miniconda3-latest-Linux-x86_64.sh -b
RUN apt-get install -y build-essential libxrender1 git
RUN /root/miniconda3/bin/conda init bash
RUN /root/miniconda3/bin/conda create -n Jupyter_Dock python=3.8
RUN /root/miniconda3/bin/conda run -n Jupyter_Dock pip install Jupyter
RUN /root/miniconda3/bin/conda run -n Jupyter_Dock conda install -c schrodinger pymol
RUN /root/miniconda3/bin/conda run -n Jupyter_Dock conda install -c conda-forge py3dmol
RUN /root/miniconda3/bin/conda run -n Jupyter_Dock pip install vina
RUN /root/miniconda3/bin/conda run -n Jupyter_Dock conda install -c conda-forge openbabel
RUN /root/miniconda3/bin/conda run -n Jupyter_Dock pip install meeko
RUN /root/miniconda3/bin/conda run -n Jupyter_Dock conda install -c conda-forge pdbfixer
RUN /root/miniconda3/bin/conda run -n Jupyter_Dock pip install rdkit cython
RUN /root/miniconda3/bin/conda run -n Jupyter_Dock pip install git+https://github.com/chemosim-lab/ProLIF.git

RUN /root/miniconda3/bin/conda run -n Jupyter_Dock pip install --upgrade jupyter_server 
RUN /root/miniconda3/bin/conda run -n Jupyter_Dock pip install notebook traitlets
RUN apt-get update && apt-get install -y locales
RUN localedef -i en_US -f UTF-8 en_US.UTF-8
ENV LANG=en_US.UTF-8
ENV LC_ALL=en_US.UTF-8