<!--
SPDX-FileCopyrightText: 2026 roolrz
SPDX-License-Identifier: Apache-2.0
-->

# lib-vm-policy

VM containment, fleet and deployment policy vocabulary.

Owns affinity, scheduling, image policy and fleet request/state definitions shared by
the management client and services. The shared/ wrapper provides one Native delivery
library.

See the [implementation entry](src/lib.rs) and [component declaration](component.json)
for the public interfaces, build dependencies and delivered artifacts.

## Boundaries

Policy records describe requested behavior; the manager and runtime still validate
actual resources and authority. Lifecycle acceptance is separate from completed
hardware/resource retirement.

## Build and test

Use this checkout inside the [repo-managed workspace](https://github.com/HypeR-Proj/HypeR).
From this repository directory:

```sh
make
make test
```

An absolute `OUT=/path/to/out` selects a shared output directory. The module
entry delegates to build/system, which prepares the installed SDK and declared
dependencies. Native binaries require HypeR; host module checks cover the tests
selected by component.json. A standalone clone does not contain the workspace’s
other source repositories or Native SDK.
