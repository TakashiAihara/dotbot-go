Dotbot-go
=============

Forked from https://github.com/delicb/dotbot-golang

Plugin for [dotbot](https://github.com/anishathalye/dotbot) that knows how to install [GoLang](https://golang.org/) packages.

Usage
-----

Add this repo as subrepo to your dotfiles and update `install` script.

```bash
git submodule add https://github.com/TakashiAihara/dotbot-go
```

Then, modify install script to add path to `dotbot-go` directory that you
just added. Only last line is relevant (if it was not changed from default) and
after change it might look like this:

```bash
"${BASEDIR}/${DOTBOT_DIR}/${DOTBOT_BIN}" -d "${BASEDIR}" -c "${CONFIG}" --plugin-dir=dotbot-go "${@}"
```

To use it, add go directive. Values can be simple (only package name) or more
detailed (dict with flags passed to `go install` command). Example:

```yaml
- go:
  - github.com/delicb/cliware
  - package:
    - github.com/delicb/cliware-middlewares
    flags: [-v, -u]
    stdout: true
    stderr: true
```
