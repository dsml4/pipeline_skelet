# The Pipeline Skelet
A simple pipeline example to standalone play with pipeline design.

## Setup pipeline dev container

```bash
#bash
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
```bash
# In Windows PowerShell use the command below before the git clone command: 
#  git config --global core.autocrlf false
docker run --rm --name skelet -p 3001:3000 -p 8889:8888 -v ${PWD}:/home/jovyan/work -e DAGSTER_HOME=/home/jovyan/work/daghome skelet bash work/pipeline_skelet/start.sh
```

Open JupyterLab in a browser: http://127.0.0.1:8889/lab

Open Dagster in a browser: http://127.0.0.1:3001


<img width="1387" alt="simple_pipeline_Overview" src="https://user-images.githubusercontent.com/1010096/233464876-b226705c-68de-460a-8a3e-601e9acfb94f.png">

![Job_simple_pipeline](https://user-images.githubusercontent.com/1010096/233465127-02653224-57de-41e6-8d91-2c82fda7e191.svg)

<img width="797" alt="skelit_launchpad" src="https://user-images.githubusercontent.com/1010096/233466076-a07d6148-bbc6-4d77-a74a-fb4e81996bd0.png">

<img width="917" alt="skelit_runs" src="https://user-images.githubusercontent.com/1010096/233467712-cedecf8d-aa6d-49b3-8ab7-f60df756a530.png">

<img width="1282" alt="open_path_skelet" src="https://user-images.githubusercontent.com/1010096/233469395-0724146a-4e88-4ed5-8968-faf7f891af46.png">

<img width="1109" alt="out_nb_2_skelet" src="https://user-images.githubusercontent.com/1010096/233469762-894ac992-bc0a-44be-9f66-3b729bc58e68.png">

<img width="890" alt="skelet_runs" src="https://user-images.githubusercontent.com/1010096/233470938-470df4f7-51ab-4a42-be97-8ab1fb61f867.png">
