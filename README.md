# Minikube Jenkins configuration

Project with the setup to deploy Jenkins into Kubernates cluster on local PC
<HR>
<H4>Installation Kind</H4>

https://github.com/kubernetes-sigs/kind/releases

1. <code>$curl -Lo ./kind-linux-amd64 https://github.com/kubernetes-sigs/kind/releases/download/v0.4.0/kind-linux-amd64</code>
2. <code>$sudo mv ./kind-linux-amd64 /usr/local/bin/kind</code>
3. <code>$chmod +x /usr/local/bin/kind</code>
4. <code>$kind create cluster</code>
5. <code>$export KUBECONFIG="$(kind get kubeconfig-path --name="kind")"</code>
6. <code>$kubectl cluster-info</code>

<H4>Installation kubernetes-cli</H4>
https://kubernetes.io/docs/tasks/tools/install-kubectl/

1. <code>$sudo curl -LO https://storage.googleapis.com/kubernetes-release/release/v1.15.0/bin/linux/amd64/kubectl</code>
2. <code>$chmod +x ./kubectl</code>
3. <code>$sudo mv ./kubectl /usr/local/bin/kubectl</code>
4. <code>$kubectl version</code>

<H5>optional setting zsh</H5>
1. <code>$source <(kubectl completion zsh)</code> # setup autocomplete in zsh into the current shell<BR>
2. <code>$echo "if [ $commands[kubectl] ]; then source <(kubectl completion zsh); fi" >> ~/.zshrc</code>add autocomplete permanently to your zsh shell

<H4>Installation Helm</H4>
https://github.com/helm/helm/releases

1. <code>$curl -LO https://get.helm.sh/helm-v2.14.2-linux-amd64.tar.gz</code>
2. <code>$tar -zxvf helm-v2.14.2-linux-amd64.tar.gz</code>
3. <code>$chmod +x .linux-amd64/helm</code>
4. <code>$sudo mv .linux-amd64/helm /usr/local/bin/helm</code>
5. <code>$rm -d -R  linux-amd64</code>

<H4>Deploy Jenkins</H4>
1. <code>git clone git clone https://github.com/devuserPP/kubernetes_ci.git</code>
2. <code>kubectl create -f jenkins-namespace.yaml</code>
3. <code>kubectl create -f jenkins-volume.yaml</code>
4. <code>cd helm && helm init</code>

