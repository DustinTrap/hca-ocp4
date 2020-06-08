# hca-ocp4

## Overview

Here are some sample materials for an installation of OpenShift 4 on Azure using IPI Full Stack Automation.

## Prequisites

Have an Red Hat account you can use to access cloud.redhat.com

## Cloud Management Steps

Download and install the *latest* version of the OC and OpenShift-Installer from cloud.redhat.com.

Download and save the pull secret to the same path.
 
## System Setup steps

Add OC and OpenShift-Installer to your path. (example on my mac /usr/local/bin)

## Azure Setup steps

Follow [documentation](https://docs.openshift.com/container-platform/latest/installing/installing_azure/installing-azure-default.html) for full steps.

### Main Azure components

* Azure Security Principal
   * Capture "subscriptionId", "clientId" ,"clientSecret", "tenantId" for later use
* Public DNS Zone
* Azure Accounts Limits

## Terminal Output from successful deployment


```
$ ./openshift-install create cluster
? SSH Public Key /Users/dtrapani/.ssh/id_rsa.pub
? Platform azure
INFO Credentials loaded from file "/Users/dtrapani/.azure/osServicePrincipal.json" 
? Region eastus
? Base Domain ocp4ninja.com
? Cluster Name hca
? Pull Secret [? for help] **********************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************
INFO Creating infrastructure resources...         
INFO Waiting up to 20m0s for the Kubernetes API at https://api.hca.ocp4ninja.com:6443... 
INFO API v1.17.1+f63db30 up                       
INFO Waiting up to 40m0s for bootstrapping to complete... 
INFO Destroying the bootstrap resources...        
INFO Waiting up to 30m0s for the cluster at https://api.hca.ocp4ninja.com:6443 to initialize... 
INFO Waiting up to 10m0s for the openshift-console route to be created... 
INFO Install complete!                            
INFO To access the cluster as the system:admin user when using 'oc', run 'export KUBECONFIG=/Users/dtrapani/Documents/git repos/hca-ocp4/bin/auth/kubeconfig' 
INFO Access the OpenShift web-console here: https://console-openshift-console.apps.hca.ocp4ninja.com 
INFO Login to the console with user: kubeadmin, password: XXXXX-XXXXX-XXXXX-XXXXX 
```

## Screen shots

pictures!!

# Clean up notes:

check the cleanup-script.sh for some files to delete if you decide to delete the cluster and start over.

## example of a clean directory

```
MacBook-Pro:bin dtrapani$ ls -lah
total 1189208
drwxr-xr-x@ 6 dtrapani  staff   192B Jun  3 13:45 .
drwxr-xr-x@ 7 dtrapani  staff   224B Jun  2 17:02 ..
-rw-r--r--@ 1 dtrapani  staff   706B Jun  2 15:07 README.md
-rwxr-xr-x@ 1 dtrapani  staff    79M Jun  2 15:06 kubectl
-rwxr-xr-x@ 1 dtrapani  staff    79M Jun  2 15:06 oc
-rwxr-xr-x@ 1 dtrapani  staff   423M Jun  2 15:07 openshift-install

```

Need to sort out how to add custom tags specific to Resource Group during deploy.
For a private cluster, how much UPI\IPI do you lose.
