I tried to set up Control Center on MiniKube. Unfortunately the helm command got stuck and failed with an error after 5 minutes when being run on MiniKube. Petri's instructions were vital in having CC running on MiniKube.
Instructions here: https://hub.docker.com/r/petrivaadin/control-center-testing

I'll try the same thing with microk8s as well.

microk8s is a bit tricky. Set it up via sudo snap install microk8s --classic and install necessary stuff according to https://mvysny.github.io/playing-with-kubernetes/
Before you install CC, you need some way for loadbalancers to have external ip otherwise the CC helm installation will fail.

Install metallb: microk8s enable metallb
MetalLB will ask for a set of IP addresses, not sure what to provide here, but maybe just create an IP address that is +1 above your current IP address?

To expose CC pod:

microk8s kubectl port-forward  control-center-788b568955-q99m9 -n control-center 8000:8080

Then go to http://localhost:8000 and try to install CC. Unfortunately it will fail with:

An error occured while installing clusterissuers.cert-manager.io

Unfortunately I have no further spare time to investigate.
