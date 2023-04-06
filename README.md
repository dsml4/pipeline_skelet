# The Pipeline Skelet
A simple pipeline example to standalone play with pipeline design.
┌──────┴──────┐ `rgb(9, 105, 218)` └─────────────┬────────────┘

<span style="color:blue">some *blue* text</span> :tada:

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
# Windows PowerShell
#  git config --global core.autocrlf false
docker run --rm --name skelet -p 3001:3000 -p 8889:8888 -v ${PWD}:/home/jovyan/work -e DAGSTER_HOME=/home/jovyan/work/daghome skelet bash work/pipeline_skelet/start.sh
```

Open JupyterLab in a browser: http://127.0.0.1:8889/lab

Open Dagster in a browser: http://127.0.0.1:3001/lab

<img width="1076" alt="dagstermill_pipeline" src="https://user-images.githubusercontent.com/1010096/228957557-65f90e12-7901-46b7-935f-40a999511184.png">

![simple_pipeline_launch](https://user-images.githubusercontent.com/1010096/225409534-34c6ea26-f809-427a-ae12-5ed7a408b0e7.png)
![simple_pipeline_runs](https://user-images.githubusercontent.com/1010096/225409578-986b7f25-092d-4fe0-89d4-983cfbc0a95a.png)
![simple_pipeline_storage](https://user-images.githubusercontent.com/1010096/225410761-557bea3e-670e-4359-beb1-91b45bae1003.png)
