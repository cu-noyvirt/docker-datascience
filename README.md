# docker-datascience

## Install [Docker Toolbox](https://www.docker.com/products/docker-toolbox)

## Download an [Anaconda image](https://hub.docker.com/r/continuumio/anaconda3/)

### You can download and run an anaconda image using the following commands:

* docker pull continuumio/anaconda3
* docker run -i -t continuumio/anaconda3 /bin/bash

Alternatively, you can start a Jupyter Notebook server and interact with Anaconda via your browser:

* docker run -i -t -p 8888:8888 continuumio/anaconda3 /bin/bash -c "/opt/conda/bin/conda install jupyter -y --quiet &&
mkdir /opt/notebooks && /opt/conda/bin/jupyter notebook --notebook-dir=/opt/notebooks --ip='*' --port=8888 --no-browser
"
You can then view the Jupyter Notebook by opening http://localhost:8888 in your browser, or http://<DOCKER-MACHINE-IP>:8888 if you are using a Docker Machine VM.
