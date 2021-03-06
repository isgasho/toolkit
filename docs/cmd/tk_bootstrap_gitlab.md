## tk bootstrap gitlab

Bootstrap toolkit components in a GitLab repository

### Synopsis

The bootstrap gitlab command creates the GitLab repository if it doesn't exists and
commits the toolkit components manifests to the master branch.
Then it configures the target cluster to synchronize with the repository.
If the toolkit components are present on the cluster,
the bootstrap command will perform an upgrade if needed.

```
tk bootstrap gitlab [flags]
```

### Examples

```
  # Create a GitLab API token and export it as an env var
  export GITLAB_TOKEN=<my-token>

  # Run bootstrap for a private repo owned by a GitLab group
  bootstrap gitlab --owner=<group> --repository=<repo name>

  # Run bootstrap for a repository path
  bootstrap gitlab --owner=<group> --repository=<repo name> --path=dev-cluster

  # Run bootstrap for a public repository on a personal account
  bootstrap gitlab --owner=<user> --repository=<repo name> --private=false --personal=true 

  # Run bootstrap for a private repo hosted on a GitLab server 
  bootstrap gitlab --owner=<group> --repository=<repo name> --hostname=<domain>

```

### Options

```
  -h, --help                help for gitlab
      --hostname string     GitLab hostname (default "gitlab.com")
      --interval duration   sync interval (default 1m0s)
      --owner string        GitLab user or group name
      --path string         repository path, when specified the cluster sync will be scoped to this path
      --personal            is personal repository
      --private             is private repository (default true)
      --repository string   GitLab repository name
```

### Options inherited from parent commands

```
      --components strings   list of components, accepts comma-separated values (default [source-controller,kustomize-controller,notification-controller])
      --kubeconfig string    path to the kubeconfig file (default "~/.kube/config")
      --namespace string     the namespace scope for this operation (default "gitops-system")
      --timeout duration     timeout for this operation (default 5m0s)
      --verbose              print generated objects
      --version string       toolkit tag or branch (default "master")
```

### SEE ALSO

* [tk bootstrap](tk_bootstrap.md)	 - Bootstrap toolkit components

