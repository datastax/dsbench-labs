# The Guidebook

DSBench comes with its own internal documentation. The intent is to make documentation and new UI features live together in an interactive way going forward.

The docs content will be put online at some point, but for now the focus of effort is in improving the content in the guidebook itself. It's best to update your dsbench version and use the new content to learn about new features and how to use them.

## Guidebook on localhost:

This runs the dsbench in docserver mode at `http://localhost:12345/` by default:

    dsbench docserver

This is by far the most secure mode. If you want to access it in this mode from a remote system like your desktop, you can port forward via ssh, with an option like `-L12345:localhost:12345` for openssh, for example.

## Guidebook on a routable address:

If you want to access dsbench documentation directly from a different system, like your desktop, then you can run it with one of these forms:

    # with a specific listener address (a local interface)
    dsbench docserver http://192.168.128.123:12345/

    # or bind to all local addresses
    dsbench docserver http://0.0.0.0:12345/

In either of these forms, you'll be able to access the guidebook app from any external system, barring any interference from firewalls. This is obviously the least secure. For now, there isn't much functionality to expose besides docs. However, you'll want to protect access to this system if/when you every drive workloads interactively this way.

The guidebook is the first UI-based application to be bundled with dsbench. Stay tuned for more news on what's next!
