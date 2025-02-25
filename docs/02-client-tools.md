# Installing the Client Tools

In this lab you will install the command line utilities required to complete this tutorial: [cfssl](https://github.com/cloudflare/cfssl), [cfssljson](https://github.com/cloudflare/cfssl), and [kubectl](https://kubernetes.io/docs/tasks/tools/install-kubectl).

## Install CFSSL

The `cfssl` and `cfssljson` command line utilities will be used to provision a [PKI Infrastructure](https://en.wikipedia.org/wiki/Public_key_infrastructure) and generate TLS certificates.

On the **gateway-01** VM, download and install `cfssl` and `cfssljson`:

```bash
wget -q --show-progress --https-only --timestamping \
  https://storage.googleapis.com/kubernetes-the-hard-way/cfssl/linux/cfssl \
  https://storage.googleapis.com/kubernetes-the-hard-way/cfssl/linux/cfssljson
```

```bash
chmod +x cfssl cfssljson
```

```bash
sudo mv cfssl cfssljson /usr/local/bin/
```

### Verification

Verify `cfssl` and `cfssljson` version 1.3.4 or higher is installed:

```bash
cfssl version
```

> Output:

```bash
Version: 1.3.4
Revision: dev
Runtime: go1.13
```

```bash
cfssljson --version
```

> Output:

```bash
Version: 1.3.4
Revision: dev
Runtime: go1.13
```

## Install kubectl

The `kubectl` command line utility is used to interact with the Kubernetes API Server. On the **gateway-01** VM, download and install `kubectl` from the official release binaries:

```bash
wget https://storage.googleapis.com/kubernetes-release/release/v1.21.5/bin/linux/amd64/kubectl
```

```bash
chmod +x kubectl
```

```bash
sudo mv kubectl /usr/local/bin/
```

### Verification install

Verify `kubectl` version 1.15.3 or higher is installed:

```bash
kubectl version --client
```

> Output:

```bash
Client Version: version.Info{Major:"1", Minor:"18", GitVersion:"v1.21.5", GitCommit:"c96aede7b5205121079932896c4ad89bb93260af", GitTreeState:"clean", BuildDate:"2020-06-17T11:41:22Z", GoVersion:"go1.16.5", Compiler:"gc", Platform:"linux/amd64"}
```

Next: [Provisioning Compute Resources](03-compute-resources.md)
