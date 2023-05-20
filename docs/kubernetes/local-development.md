# Local Development

## Cluster
A local kubernetes cluster is provisioned using [kind](https://kind.sigs.k8s.io/)

To create a new cluster use:
```sh
kind create cluster
```

## Development Environment

First of all install `kubectl` to interact with the kubernetes cluster
```
brew install kubectl
```

Install [Oh-my-zsh](https://ohmyz.sh/) and supercharge your kubernetes usage with `kubens`, `kubectx` and `kube-ps1`:
```
brew install kubens kube-ps1
```

`kubens` allows you to quickly change namespaces

`kubectx` allows you to quickly change your kubernetes context

`kube-ps1` shows the above information in your prompt:
```sh
(⎈|kind-kind:backstage)➜  ~
```

For aliases and autocompletion add the following entries to your `~/.zshrc`:
```sh
source "/usr/local/opt/kube-ps1/share/kube-ps1.sh"
PS1='$(kube_ps1)'$PS1
source <(kubectl completion zsh)
alias kctx="kubectx"
alias kns="kubens"
```

Finally the [kubectl plugin](https://github.com/ohmyzsh/ohmyzsh/tree/master/plugins/kubectl) of Oh-my-zsh is recommended to save a few more keystrokes

This setup is based on this [article](https://agrimprasad.com/post/supercharge-kubernetes-setup/)
