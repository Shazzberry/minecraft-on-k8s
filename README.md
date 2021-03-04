# minecraft-on-k8s
This is a WIP project where I built an MC server running https://feed-the-beast.com/modpack/ftb_presents_direwolf20_1_16 on Kubernetes

So a quick explanation, you simply need to clone this down, `kubectl apply -f ./mc-ftba --namespace=minecraft` while connected to your cluster.

So the server requires you to edit the server config while it is in an "off state" once deployed. This means you scale the replicaset to 0, then deploy the pvc pod. Once done simply open a shell on the container and check the /data directory for the server files on the PVC. Then you can apply edits that they server will acknowlegde upon restart.

# Dependancies

This is in large part thanks to the work over at https://github.com/itzg/docker-minecraft-server and https://github.com/itzg/minecraft-server-charts
I took a large amount of what was working over there and applied it in this format. So BIG shout out to itzg.


