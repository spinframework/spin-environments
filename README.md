# Spin target environments

This repository contains target environment definitions for Spin. Each target
environment is a TOML file which maps triggers to the WIT worlds supported by
those triggers. These can be referenced
in the Spin manifest `application.targets` array (as e.g. `spin-up@3.4`).

Environment definitions:

* are TOML files
* live under a `<environment-name>` directory
* are named `<environment-name>[@<version>].toml`

Versions should include _minor version only_ because WITs should not
change in patch releases. The version may be omitted if your environment
doesn't have versions (e.g. a hosted service which updates periodically
and anything which runs on it will see its latest world).

(The `<environment-name>` directory is technically redundant but just makes the repo
a bit easier to navigate!)

## Schema

* `default` (optional)
  *  `worlds` - array of worlds to accept when an unknown triggers is in play
* `triggers`
  * `<trigger-type>`
    * `worlds` - array of worlds to accept when this trigger is in play
    * `capabilities` - lockfile capabilities that the host provides when this trigger is in play
* `metadata` (all optional)
  * `templates` - Spin app templates recommended for developing for this environment
    * `url` - the git repo containing templates for this environment
    * `tag` - optional tag, if present then use this rev of the templates
  * `plugins` - plugins recommended to install for working with this environment
 