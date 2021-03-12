#### Experiments with Nexus3 in k3s

Assuming you already installed the Token in your local config:

    $ export KUBECONFIG=~/.kube/config
    $ kubectl get nodes
    $ source <(kubectl completion bash)

See Docker [Hub](https://hub.docker.com/r/sonatype/nexus3) for recent
image versions.

    $ kubectl create namespace hello-nexus
    $ kubectl config set-context --current --namespace=hello-nexus
    $ kubectl apply -k k3s/

Then visit  the [URL](https://nexus.localhost). For the  initial admin
password see

    $ kubectl exec -it nexus-server-xxx -- cat /nexus-data/admin.password
