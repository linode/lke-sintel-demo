# Linode Kubernetes Engine Video Streaming Demo

## [Sintel](https://durian.blender.org/about/), A Blender Foundation Open Movie Project

### Demonstrates the following Kubernetes Controllers

* Ingress controller: nginx-ingress
* Certificate controller: cert-manager
* DNS controller: external-dns

### Linode Services Used

* Linode Kubernetes Engine
* Linode DNS Service
* Linode NodeBalancer LoadBalancer

### Instructions

1. Edit linode-secret.yaml and add an API token that can read/write DNS records
   in base64 format
1. Apply that manifest `kubectl apply -f linode-secret.yaml`
1. Apply the manifests for the controllers that we are using `kubectl apply -f
   controllers.yaml`
1. Edit app.yaml to use a Domain zone that you control on Lindoe DNS. For
   example, change "sintel.kubeyboy.com" to "sintel.yourdomain.com"
1. Apply `app.yaml`
1. Wait a few minutes for DNS to propagate and cert-manager to issue a certificate.
1. Visit your domain in a web browser!

