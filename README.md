# DSBench

DSBench allows you to run realistic workloads against your CQL systems without having to build your own testing harness. It builds on a set of core testing concepts and machinery to give you a performance testing power suit. Specifically, it allows you to control and customize your client operations so that they are representative of a real workload that you would run with your application. If you don't want to control for this level of detail, you can use one of the built-in workloads with a single command.

This repository is where we manage issues, feature requests, and releases for DSBench.

DSBench is released as a Linux compatible binary. Future releases may include support for Mac or Windows.

## Supported Systems

In this initial release, DSBench supports CQL based systems and console output. In dsbench terms, this means:

- The CQL activity type
  - The initial release of the CQL activity type uses the DataStax driver version 1.9.0
- The stdout activity type. (this is a way to see operations in diagnostic mode)

Activity types are how DSBench gets its support for different protocols or client drivers. The initial release of DSBench includes only two, but additional types will be supported in future releases.

[Basic Examples](https://github.com/datastax/dsbench-labs/wiki/Basic-Examples) give a preview of some of the things you can do with DSBench and how it works. The real docs are included in the tool itself.

## Getting Started

On Linux systems:
1. Download dsbench from [DSBench Releases](https://github.com/datastax/dsbench-labs/releases)
2. Make it executable: `chmod +x dsbench`
3. Start dsbench in docserver mode: `dsbench docserver http://0.0.0.0:12345/`
4. Browse to the system you are running it on and you will be presented with the Guidebook.

On other systems:
1. Download dsbench.jar from [DSBench Releases](https://github.com/datastax/dsbench-labs/releases)
2. Install a Java 12 or newer JDK.
3. Start dsbench in docserver mode: `java -jar dsbench.jar docserver http://0.0.0.0:12345/`
4. Browse to the system you are running it on and you will be presented with the Guidebook.

[Running DSBench on docker](https://hub.docker.com/repository/docker/datastaxlabs/dsbench)

[The Guidebook](https://github.com/datastax/dsbench-labs/wiki/The-Guidebook) provides the most essential place to get access to the docs.

[Release Plans](https://github.com/datastax/dsbench-labs/wiki/Release-Plans) are how we plan to prioritize and scope releases going forward.

## Support

### Community Support

DSBench is released as a DataStax Labs tech preview.

It is supported by a community of active users at [DataStax DSBench Community](https://community.datastax.com/spaces/51/index.html).

### Bug Fixes

If you think you have found a bug, you may [file a bug report](https://github.com/datastax/dsbench-labs/issues/new?labels=bug). DSBench is actively used within DataStax, and verified bugs will get attention as resources permit.

### Feature Requests

If you would like to see something in DSBench that is not there yet,
please [submit a feature request](https://github.com/datastax/dsbench-labs/issues/new?labels=feature).

## Sponsors

[![DataStax Logo](https://www.datastax.com/sites/default/files/content/graphics/logo/DS-logo-2019_1-25percent.png)](http://datastax.com/)

DSBench development is sponsored by DataStax.

DataStax offers a suite of distributed data management products and cloud services powered by Apache Cassandra. We simplify achieving zero downtime for enterprise apps that are active everywhere–DataStax delivers the ultimate hybrid and multi-cloud database. For more information, visit [www.DataStax.com](http://www.datastax.com/) and follow us on [@DataStax](https://twitter.com/Datastax)
