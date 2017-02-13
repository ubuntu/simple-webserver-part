# simple-webserver-part
Snapcraft simple webserver part

## Usage:

In your snapcraft.yaml:

1. Just have one of your snapcraft part defining:
`after: [simple-webserver]`
1. Then, spawn a service with it, with the part relative to your snap to serve:
```
apps:
  my-server:
    command: webserver www
    daemon: simple
    restart-condition: always
    plugs: [network-bind]

```

Here, `www` is relative to **$SNAP** from your own snap.

You can change the default port (*8080*) with the `-p` option, for instance:
`command: webserver -p 9001 www`.
