# criecm.node

Install/run node apps on FreeBSD (could be easily adapted)

## Role Variables

* `node_version` (8)
  node major version
* `node_apps` ([])
  list of dicts for each app (see **app variables** below)
* `node_update_git` (False)
  update git sources if any

### app variables

* `name` MANDATORY
  short name for the app, [a-z0-9] only
* `user` (`name`)
* `path` (/home/`name`)
* `script` (app.js)
* `gitsrc` ('')
  Git repository source
* `update` (False)
  Will update source code (or globally if `node_update_git`)
* `confs` ([])
  List of config files, as dicts of {src=template,dest=dest}
  dest can be relative to `app.path`

## Dependencies

## Example Playbook

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - criecm.node
      vars:
        node_apps:
          - name: myapp1
            script: index.js
            confs:
              - src: mytemplace.js.j2
                dest: config.js

## License

BSD
