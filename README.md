# k8s-starter
startup application to run on minikube

## remove or delete all binaries of minikube, docker and virtual box(if any)
$ rm /usr/local/bin/minikube
$ rm /usr/local/bin/boot2docker.bak
$ rm /usr/local/bin/docker.bak

## download and setup minikube
### minikube git repo for reference:
https://github.com/kubernetes/minikube/releases/tag/v0.19.1

### dont run this command, try to use brew to install minikube
$curl -Lo minikube https://storage.googleapis.com/minikube/releases/v0.19.1/minikube-darwin-amd64 && chmod +x minikube && sudo mv minikube /usr/local/bin/

### update brew before installing any further plugins
$brew update
Error: /usr/local must be writable!

### change the owner for time being
$sudo chown -R z001j12 /usr/local

### try to update brew again
$brew update

### install minikube through brew

'''
$ brew cask install minikube
==> Creating Caskroom at /usr/local/Caskroom
==> Satisfying dependencies
==> Installing Formula dependencies from Homebrew
kubernetes-cli ... ==> Error: The `brew link` step did not complete successfully
Error: Command failed to execute!
'''

### download virtual box, if you got one already better delete/uninstall first
https://www.virtualbox.org/wiki/Downloads

Version 5.1.22

### re-install minikube after VirtualBox is setup
$ brew cask install minikube
==> Satisfying dependencies
==> Installing Formula dependencies from Homebrew
kubernetes-cli ... already installed
complete
==> Downloading https://storage.googleapis.com/minikube/releases/v0.19.1/minikube-darwin-amd64
######################################################################## 100.0%
==> Verifying checksum for Cask minikube
==> Installing Cask minikube
Error: It seems there is already a Binary at '/usr/local/bin/minikube'; not linking.
Error: Install incomplete.

### delete old binaries if not deleted at first
$ rm /usr/local/bin/minikube
$ rm /usr/local/bin/boot2docker.bak
$ rm /usr/local/bin/docker.bak

### try to re-install minikube
$ brew cask install minikube
==> Satisfying dependencies
==> Installing Formula dependencies from Homebrew
kubernetes-cli ... already installed
complete
==> Downloading https://storage.googleapis.com/minikube/releases/v0.19.1/minikube-darwin-amd64
Already downloaded: /Users/z001j12/Library/Caches/Homebrew/Cask/minikube--0.19.1
==> Verifying checksum for Cask minikube
==> Installing Cask minikube
==> Linking Binary 'minikube-darwin-amd64' to '/usr/local/bin/minikube'.
🍺  minikube was successfully installed!

### install xhyve-driver, follow the readme
https://github.com/kubernetes/minikube/blob/master/docs/drivers.md#xhyve-driver

$ minikube start
Starting local Kubernetes v1.6.4 cluster...
Starting VM...
Downloading Minikube ISO
 89.51 MB / 89.51 MB [==============================================] 100.00% 0s
Moving files into cluster...
Setting up certs...
Starting cluster components...
Connecting to cluster...
Setting up kubeconfig...
Kubectl is now configured to use the cluster.

=================================
=      MINI KUBE SETUP DONE     =
=================================

# Install docker, follow readme
https://docs.docker.com/docker-for-mac/install/#install-and-run-docker-for-mac

# register minikube in-built docker bin to user local bin
eval $(minikube docker-env)
