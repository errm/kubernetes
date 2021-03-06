<!-- BEGIN MUNGE: UNVERSIONED_WARNING -->

<!-- BEGIN STRIP_FOR_RELEASE -->

<img src="http://kubernetes.io/img/warning.png" alt="WARNING"
     width="25" height="25">
<img src="http://kubernetes.io/img/warning.png" alt="WARNING"
     width="25" height="25">
<img src="http://kubernetes.io/img/warning.png" alt="WARNING"
     width="25" height="25">
<img src="http://kubernetes.io/img/warning.png" alt="WARNING"
     width="25" height="25">
<img src="http://kubernetes.io/img/warning.png" alt="WARNING"
     width="25" height="25">

<h2>PLEASE NOTE: This document applies to the HEAD of the source tree</h2>

If you are using a released version of Kubernetes, you should
refer to the docs that go with that version.

<!-- TAG RELEASE_LINK, added by the munger automatically -->
<strong>
The latest release of this document can be found
[here](http://releases.k8s.io/release-1.2/docs/user-guide/kubectl/kubectl_delete.md).

Documentation for other releases can be found at
[releases.k8s.io](http://releases.k8s.io).
</strong>
--

<!-- END STRIP_FOR_RELEASE -->

<!-- END MUNGE: UNVERSIONED_WARNING -->

## kubectl delete

Delete resources by filenames, stdin, resources and names, or by resources and label selector.

### Synopsis


Delete resources by filenames, stdin, resources and names, or by resources and label selector.

JSON and YAML formats are accepted.

Only one type of the arguments may be specified: filenames, resources and names, or resources and label selector

Note that the delete command does NOT do resource version checks, so if someone
submits an update to a resource right when you submit a delete, their update
will be lost along with the rest of the resource.

```
kubectl delete ([-f FILENAME] | TYPE [(NAME | -l label | --all)])
```

### Examples

```
# Delete a pod using the type and name specified in pod.json.
kubectl delete -f ./pod.json

# Delete a pod based on the type and name in the JSON passed into stdin.
cat pod.json | kubectl delete -f -

# Delete pods and services with same names "baz" and "foo"
kubectl delete pod,service baz foo

# Delete pods and services with label name=myLabel.
kubectl delete pods,services -l name=myLabel

# Delete a pod with UID 1234-56-7890-234234-456456.
kubectl delete pod 1234-56-7890-234234-456456

# Delete all pods
kubectl delete pods --all
```

### Options

```
      --all[=false]: [-all] to select all the specified resources.
      --cascade[=true]: If true, cascade the deletion of the resources managed by this resource (e.g. Pods created by a ReplicationController).  Default true.
  -f, --filename=[]: Filename, directory, or URL to a file containing the resource to delete.
      --grace-period=-1: Period of time in seconds given to the resource to terminate gracefully. Ignored if negative.
      --ignore-not-found[=false]: Treat "resource not found" as a successful delete. Defaults to "true" when --all is specified.
      --include-extended-apis[=true]: If true, include definitions of new APIs via calls to the API server. [default true]
  -o, --output="": Output mode. Use "-o name" for shorter output (resource/name).
  -R, --recursive[=false]: If true, process directory recursively.
  -l, --selector="": Selector (label query) to filter on.
      --timeout=0: The length of time to wait before giving up on a delete, zero means determine a timeout from the size of the object
```

### Options inherited from parent commands

```
      --alsologtostderr[=false]: log to standard error as well as files
      --as="": Username to impersonate for the operation.
      --certificate-authority="": Path to a cert. file for the certificate authority.
      --client-certificate="": Path to a client certificate file for TLS.
      --client-key="": Path to a client key file for TLS.
      --cluster="": The name of the kubeconfig cluster to use
      --context="": The name of the kubeconfig context to use
      --insecure-skip-tls-verify[=false]: If true, the server's certificate will not be checked for validity. This will make your HTTPS connections insecure.
      --kubeconfig="": Path to the kubeconfig file to use for CLI requests.
      --log-backtrace-at=:0: when logging hits line file:N, emit a stack trace
      --log-dir="": If non-empty, write log files in this directory
      --log-flush-frequency=5s: Maximum number of seconds between log flushes
      --logtostderr[=true]: log to standard error instead of files
      --match-server-version[=false]: Require server version to match client version
      --namespace="": If present, the namespace scope for this CLI request.
      --password="": Password for basic authentication to the API server.
  -s, --server="": The address and port of the Kubernetes API server
      --stderrthreshold=2: logs at or above this threshold go to stderr
      --token="": Bearer token for authentication to the API server.
      --user="": The name of the kubeconfig user to use
      --username="": Username for basic authentication to the API server.
      --v=0: log level for V logs
      --vmodule=: comma-separated list of pattern=N settings for file-filtered logging
```

### SEE ALSO

* [kubectl](kubectl.md)	 - kubectl controls the Kubernetes cluster manager

###### Auto generated by spf13/cobra on 30-Mar-2016

<!-- BEGIN MUNGE: GENERATED_ANALYTICS -->
[![Analytics](https://kubernetes-site.appspot.com/UA-36037335-10/GitHub/docs/user-guide/kubectl/kubectl_delete.md?pixel)]()
<!-- END MUNGE: GENERATED_ANALYTICS -->
