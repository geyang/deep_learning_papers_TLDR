WarpDrive
==================

Welcome to the `warpdrive` project!

`warpdrive` is an open-source experiment framework to launch, manage and monitor machine learning experiments in the cloud (AWS, Azure, Google and private clusters).

For any questions, direct to [tianlins@cs.stanford.edu](mailto:tianlins@cs.stanford.edu) or join our slack channel for discussion.

## Motivation

We see tremendous progress in deep learning but the experiment process is far from perfect. Researchers often spend weeks reproducing results in published papers. And there lacks good open-source tools to keep track of messy experiment code / data, to help scientists to iterate faster, and maybe abstract away the complexity of infrastructure.

Currently, the two dominant workflow styles are:

1. `ssh` into cluster machines and run jobs with screen.
2. use some job management system not optimized for machine learning (e.g. borg, k8s)

The first type of workflow is good for fast iteration on small datasets, but difficult to manage lot of experiments or scale up to multiple machines. The second type of workflow sacrifices the convenience of interactive inspection. Both do not provide good support for reproducibility.

## Design

Our design philosophy is very user focused, which implies

1. make infrastructure transparent.
2. provide rich visualization tool to inspect model and results.

As an example, users start with a git repo, such as `pytorch-mnist`. To launch an experiment, they do

> warp run [some cmd, such as python3 train.py]

![demo.gif](https://www.dropbox.com/s/po3ua1zi2j96ys4/dummy-04-2017.gif?raw=1)

The system automatically creates a snapshot of the git worktree, and mounts the code into a dockercontainer, and ship it through k8s for remote execution. User can use it on any cloud platform. The system also provides micro-service inspection tools, such as tensorboard, jupyter, etc.


## Getting Started

To get started on development, you need to install the following dependencies:
- Git
- Kubernetes (Kube)
	- recommend [MiniKube](https://github.com/kubernetes/minikube) for local development.
- Python3

Our `warp` system consists of two major components: `warpdrive` is the master server. It integrates with Git and Kubernetes to provide version control and distributed execution; `warpcli` is the user command line client, which interacts with `warpdrive` through HTTP protocol.

### Setting up Minikube

1. **install Docker** on your computer following the instructions at [Docker for Mac](https://www.docker.com/docker-mac).
2. **install MiniKube** from it's [releases page](https://github.com/kubernetes/minikube/releases). Minikube uses 
virtualBox to run a small kubernetes cluster locally. 

    To verify, try
    ```bash
    minikube start
    ```
    
    You can inspect your local cluster config by

    ```
    $ kubectl cluster-info
    
    Kubernetes master is running at https://192.168.99.100:8443
    KubeDNS is running at https://192.168.99.100:8443/api/v1/proxy/namespaces/kube-system/services/kube-dns
    kubernetes-dashboard is running at https://192.168.99.100:8443/api/v1/proxy/namespaces/kube-system/services/kubernetes-dashboard
    
    To further debug and diagnose cluster problems, use 'kubectl cluster-info dump'.
    ```

It's good to learn a bit about Kube commands through the cheat sheet: [https://kubernetes.io/docs/user-guide/kubectl-cheatsheet/](https://kubernetes.io/docs/user-guide/kubectl-cheatsheet/).

### Setup PostgresSQL

`warpdrive` store tables in `postgreSQL`.

1. Visit https://www.postgresql.org/download/macosx/ to download it for your max.
2. **Change server port** to 5433.
3. **Initialize database**: download this github repo, run
    ```bash
    git clone https://github.com/strin/warpdrive.git
    cd ./warpdrive/warpdrive
    python3 bin/initdb
    ```
4. Use `postico` (or other database client) to inspect the database as a client.
  
    ![database check](https://www.dropbox.com/s/ki8sm7zu50brl3z/Screenshot%202017-05-01%2016.05.28.png?raw=1)

    You will see `project` and `experiment` table created in the database.

### Setup CLI

1. **start the master server** locally:

    ```
    cd warpdrive/warpdrive
    python3 bin/run-master
    ```
    The server is now listening at 5900. 
2. To **connect to master**, install the CLI in development mode.

    ```
    cd warpdrive/warpcli
    sudo pip install -r requirements.txt
    sudo pip install -e .
    ```
    
    Now, you should be able to use `warp` cli and any changes you made will be updated.

    ```
    $ warp ls
    
      ID |                 Name |    | Start Time
    ------------------------------------------------------------------------------
    ```

### First Example

Pull all gitsubmodules, then go to `examples/tf-bare`

```
warp init tf-bare
warp run --env py3-tf-gpu -s test-tf-bare python3 run.py
```

You should be able to see tensorflow printing "hello, world", just like in the video demo.

## Team

* Slack: [dummyai.slack.com](dummyai.slack.com), for high-volume discussion.
* Asana: [Warpdrive Channel](https://app.asana.com/-/share?s=331357827523323-KBUqn82ILF3nMQcWgFeO1YxtOwdqI7obofh4MboWovI-10172332125952), for project management.
* DockerHub: [https://hub.docker.com/](https://hub.docker.com/)



