# WORK IN PROGRESS

This repo will remain private until the release of dsbench on the labs download site. At that time, it will be made public.

# DSBench

DSBench allows you to run realistic workloads against your CQL systems without having to build your own testing harness. It builds on a set of core testing concepts and machinery to give you a performance testing power suit. Specifically, it allows you to control and customize your client operations so that they are representative of a real workload that you would run with your application. If you don't want to control for this level of detail, you can use one of the built-in workloads with a single command.

This repository is where we manage issues, feature requests, and releases for DSBench, a testing tool that offers simple and powerful benchmarking for Databases. DSBench is a tailored version of some of the tools used by DataStax for internal testing as well as with customers for performance testing and verification.

## Supported Systems

In this initial release, DSBench supports CQL based systems and raw text.
In dsbench terms, this means:

- The CQL activity type
  - The initial release of the CQL activity type uses the DataStax driver version 1.9.0
- The stdout activity type.

Activity types are how DSBench gets its support for different protocols or client drivers. The initial release of DSBench includes only two, but additional types will be supported in future releases.

## Getting Started

DSBench comes with its own internal documentation, some of which is also
included on this site. The intent is to make documentation and UI features live together in an interactive way in a future release.

- [Basic Examples](getting_started/basic_examples.md)
- [Next Steps](getting_started/next_steps.md)
- [Accessing the Guidebook](getting_started/accessing_guidebook.md)

## Releases

Releases of DSBench will be linked from [DataStax Labs Downloads](https://downloads.datastax.com/#labs) to releases in this repository.

Each release will be themed around a major improvement for user experience. When needed, a release will also include an internal improvement for technical debt. Bug-fixes or small enhancements will also be included, based on user feedback and bug reports.

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

DSBench development is sponsored by DataStax.

DataStax helps companies compete in a rapidly changing world where expectations are high and new innovations happen daily. DataStax is an experienced partner in on-premises, hybrid, and multi-cloud deployments and offers a suite of distributed data management products and cloud services. We make it easy for enterprises to deliver killer apps that crush the competition.

More than 400 of the world’s leading enterprises including Capital One, Cisco, Comcast, Delta Airlines, eBay, Macy’s, McDonald’s, Safeway, Sony, and Walmart use DataStax to build modern applications that can be deployed across any cloud. For more information, visit [www.DataStax.com](http://www.datastax.com/) and follow us on [@DataStax](https://twitter.com/Datastax)