FROM us.gcr.io/echoparklabs/scipy-notebook:latest

MAINTAINER David Raleighl <david@echopakrlabs.io>

RUN conda install -y --quiet \
    Pillow \
    ipywidgets \
    bcolz \
    mkl-service \
    kaggle-cli \
    'tensorflow-gpu=1.3*' \
    'keras=2.0*' && \
  conda clean -tipsy && \
  fix-permissions $CONDA_DIR

ENV CUDA_HOME=/usr/local/cuda
ENV CUDA_ROOT=$CUDA_HOME
ENV PATH=$PATH:$CUDA_ROOT/bin:$HOME/bin
ENV LD_LIBRARY_PATH=$LD_LIBRARY_PATH:$CUDA_ROOT/lib64

WORKDIR $HOME
# Clone fast.ai source
RUN git clone -q https://github.com/fastai/courses.git fastai-courses
#WORKDIR /home/$USERNAME/fastai-courses/deeplearning1/nbs
