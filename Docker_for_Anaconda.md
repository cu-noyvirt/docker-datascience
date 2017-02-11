
## Docker Python Environment for Data Science workflows

 The Anaconda images for Docker make it easy to get started with Anaconda on any platform, and provide a flexible starting point for developing or deploying data science workflows with more than 100 of the most popular Open Data Science packages for Python and R, including data analysis, visualization, optimization, machine learning, text processing and more.

 Whether you’re a developer, data scientist, or devops engineer, Anaconda and Docker can provide your entire data science team with a scalable, deployable and reproducible Open Data Science platform.

### Download an [Anaconda image](https://hub.docker.com/r/continuumio/anaconda3/)

#### You can download and run an anaconda image using the following commands:

* `docker pull continuumio/anaconda3`
* `docker run -i -t continuumio/anaconda3 /bin/bash`

Alternatively, you can start a Jupyter Notebook server and interact with Anaconda via your browser:

* `docker run -i -t -p 8888:8888 continuumio/anaconda3 /bin/bash -c "/opt/conda/bin/conda install jupyter -y --quiet &&
mkdir /opt/notebooks && /opt/conda/bin/jupyter notebook --notebook-dir=/opt/notebooks --ip='*' --port=8888 --no-browser
"`

You can then view the Jupyter Notebook by opening `http://localhost:8888` in your browser if you have installed Docker for windows/mac, or `http://<DOCKER-MACHINE-IP>:8888` if you are using a Docker Machine VM, having installed Docker Toolbox.

