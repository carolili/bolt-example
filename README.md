# Bolt example
Bolt example for a basic folder structure and uploading a file to a set of nodes.

## Project structure
```
└── k8s_poc
    ├── bolt-project.yaml
    ├── files
    │   └── cloud-config
    ├── inventory.yaml
    └── plans
        └── install.yaml
```

## Sanity check
After configuring the nodes in the `inventory.yaml` and generated an ssh-key (with no passphrase) that you added to the `bolt-project.yaml` you can test the basic configuration by running a simple command on one of the nodes:

```
$ bolt command run whoami -t worker01
```

## How to run the example
NB! Make sure to run the command from within the project folder!

```
$ pwd
/home/myuser/bolt-example/k8s_poc

$ bolt plan run k8s_poc::install
Starting: plan k8s_poc::install
Starting: Upload cloud-config to K8S nodes on 7 nodes
Finished: Upload cloud-config to K8S nodes with 0 failures in 4.12 sec
Finished: plan k8s_poc::install in 4.15 sec
...
```
