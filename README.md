# Pipeline Skelet
A simple pipeline example to standalone play with a pipeline design.

## Setup pipeline dev container

```bash
#Create a work directory to clone a git repository. The work directory will be mounted to the container.   
mkdir work
#Step into the work directory
cd work
#Clone repository 
git clone https://github.com/dsml4/pipeline_skelet.git
# Step into a derictory with a Dockerfile 
cd pipeline_skelet
docker build -t skelet .
# Go back into the work directory to a correct using pwd command inside the next docker run instruction.
cd ../
docker run --rm --name skelet -p 3001:3000 -p 8889:8888 -v $(pwd):/home/jovyan/work -e DAGSTER_HOME=/home/jovyan/work/daghome skelet bash work/pipeline_skelet/start.sh
```

Open JupyterLab in a browser: http://127.0.0.1:8889/lab

Open Dagster in a browser: http://127.0.0.1:3001/lab
