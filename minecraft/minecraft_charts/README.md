# minecraft-on-k8s

So a quick explanation, you simply need to clone this down, `kubectl apply -f minecraft.yml --namespace=minecraft` in the directory with the file while connected to your cluster.

So the server requires you to edit the server config while it is in an "off state" once deployed. This means you scale the replicaset to 0, then deploy the pvc pod. Once done simply open a shell on the container and check the /data directory for the server files on the PVC. Then you can apply edits that they server will acknowlegde upon restart.
