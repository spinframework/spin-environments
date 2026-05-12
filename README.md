**FOR TESTING ONLY AT THIS POINT** - see https://github.com/spinframework/spin/issues/3504

# Spin target environments

This repository contains target environment definitions for Spin. Each target
environment is a TOML file which maps triggers to the WIT worlds supported by
those triggers. These can be referenced
in the Spin manifest `application.targets` array (as e.g. `spin-up@3.4`).

Environment definitions:

* are TOML files
* live under a `<environment-name>` directory
* are named `<environment-name>@<version>.toml`

Versions should include _minor version only_ because WITs should not
change in patch releases.

(The `<environment-name>` directory is technically redundant but just makes the repo
a bit easier to navigate!)
