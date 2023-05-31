# 22509

Reproduction Renovate discussion 22509

## Current behavior

A user uses a custom `regexManagers` configuration to match Docker images in `.cue` files.

Renovate opens replacement PRs like this:

```diff
- image: "k8s.gcr.io/sig-storage/csi-node-driver-registrar:v2.5.0"
+ image: "registry\.k8s\.io/sig-storage/csi-node-driver-registrar:v2.5.0"
```

The `\` characters should not be there and cause the users build to fail.

## Expected behavior

Replacement PRs without the wrong `\` characters.
