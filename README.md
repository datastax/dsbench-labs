# DSBench

DSBench allows you to run realistic workloads against your CQL systems without having to build your own testing harness. It builds on a set of core testing concepts and machinery to give you a performance testing power suit. Specifically, it allows you to control and customize your client operations so that they are representative of a real workload that you would run with your application. If you don't want to control for this level of detail, you can use one of the built-in workloads with a single command.

This repository is where we manage issues, feature requests, and releases for DSBench, a testing tool that offers simple and powerful benchmarking for Databases. DSBench is a tailored version of some of the tools used by DataStax for internal testing as well as with customers for performance testing and verification.

## Supported Systems

In this initial release, DSBench supports CQL based systems and raw text. In dsbench terms, this means:

- The CQL activity type
  - The initial release of the CQL activity type uses the DataStax driver version 1.9.0
- The stdout activity type.

Activity types are how DSBench gets its support for different protocols or client drivers. The initial release of DSBench includes only two, but additional types will be supported in future releases.

## Getting Started

1. Download dsbench from [DataStax Labs Downloads](https://downloads.datastax.com/#labs)
2. Start dsbench in docserver mode: `dsbench docserver https://0.0.0.0:12345/`
3. Browse to the system you are running it on and you will be presented with the user guide.

As a short preview of what you can do with DSBench, some
[Basic Examples](getting_started/basic_examples.md) are shared here. [The Guidebook](getting_started/the_guidebook.md) provides the most essential place to get access to the docs.

[Next Steps](getting_started/what_next.md)

## Releases

Releases of DSBench will be linked from [DataStax Labs Downloads](https://downloads.datastax.com/#labs) to releases in this repository.

This is a description of our strategy for balancing the scope of each release: Each one will be themed around a major improvement for user experience. When needed, a release will also include an internal improvement for technical debt. Bug-fixes or small enhancements will also be included, based on user feedback and bug reports, as well as improvements in the user guide for casual and advanced users.

These are indicated by labels in the issue tracker:
- `UX` for use experience - up to 1 per milestone - basis for the milestone theme
- `TECH` for tech debt - up to 1 per milestone
- `documentation` for docs focus - part of the theme
- `bug` tickets - as needed

The theme of each release will be described clearly in the milestone. If there is a ramp in bugs that need fixed, we may opt to do a quality-only release to fix things on a case-by-case basis befor returning to themed releases.

More details on the plans for each release can be seen on the [DSBench Milestones](https://github.com/datastax/dsbench-labs/milestones) plan. These milestones are subject to change, but we will do our best to stick to the ones which have been decided.

## Support

### Community Support

It is supported by a community of active users at [DataStax DSBench Community](https://community.datastax.com/dsbench/index.html).

### Bug Fixes

If you think you have found a bug, you may [file a bug report](https://github.com/datastax/dsbench-labs/issues/new?labels=bug). DSBench is actively used within DataStax, and verified bugs will get attention as resources permit. For the best results, please follow [DSBench Bug Report Guidelines](filing_a_bug_report.md)

### Feature Requests

If you would like to see something in DSBench that is not there yet,
please [submit a feature request](https://github.com/datastax/dsbench-labs/issues/new?labels=feature).

## Sponsors

[![DataStax Logo](https://www.datastax.com/sites/default/files/content/graphics/logo/DS-logo-2019_1-25percent.png)](http://datastax.com/)

DSBench development is sponsored by DataStax.

DataStax offers a suite of distributed data management products and cloud services powered by Apache Cassandra. We simplify achieving zero downtime for enterprise apps that are active everywhere–DataStax delivers the ultimate hybrid and multi-cloud database. For more information, visit [www.DataStax.com](http://www.datastax.com/) and follow us on [@DataStax](https://twitter.com/Datastax)
