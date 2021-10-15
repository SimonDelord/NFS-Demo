# NFS-Demo

This Demo is based on the following URLs:
- creating an NFS Server on CentoS7/RHEL7: https://www.itzgeek.com/how-tos/linux/centos-how-tos/how-to-setup-nfs-server-on-centos-7-rhel-7-fedora-22.html
- creating PVs and PVCs for NFS on OpenShift: https://docs.openshift.com/container-platform/4.8/storage/persistent_storage/persistent-storage-nfs.html
- how to configure a PoD to use persistent storage: https://kubernetes.io/docs/tasks/configure-pod-container/configure-persistent-volume-storage/


The video demonstrating this is available at https://youtu.be/6RJnhPfb1Ds


For the demo, I do the following:
- deploy an IPI OCP4.7 instance on AWS
- create an EC2 instance (Centos7) running as an NFS server
- follow the NFS server instructions and create a share on it
- create a PV (nfs-pv.yaml file)
- create a PVC bound to this PV (nfs-pvc.yaml file)
- create 2 PoDs making use of this PVC (pod1-nfs.yaml & pod2-nfs.yaml)
- show that both PoDs can access the same info from the NFS share
- modify one of the files on the NFS share from PoD2 and show that both PoD2 and PoD1 see the change (and that the file on the NFS server has been modified).
