# 22509

Reproduction for [Renovate discussion 22509](https://github.com/renovatebot/renovate/discussions/22509).

## Current behavior

A user has a custom `regexManagers` configuration to match Docker images in `.cue` files.

Renovate opens replacement PRs like this:

```diff
- image: "k8s.gcr.io/sig-storage/csi-node-driver-registrar:v2.5.0"
+ image: "registry\.k8s\.io/sig-storage/csi-node-driver-registrar:v2.5.0"
```

The `\` characters should not be there and cause the user's build to fail.

## Expected behavior

Replacement PRs without the wrong `\` characters.
