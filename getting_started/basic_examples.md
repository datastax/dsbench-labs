# Basic Examples

The command-line examples below are meant to give you an idea of what you can do with DSBench. It is not meant to suffice as documentation. DSBench comes with its own documentation service. To see the official docs, [Run the Guidebook](the_guidebook.md).

## Check the DSBench version

    dsbench --version

## List the available activity types

    dsbench --list-activity-types

Initially, only two activity types are included in dsbench: `cql` and `stdout`. More will be included in subsequent releases.

Example output:
```
user@system:~$ dsbench --list-activity-types
cql
stdout
```

## Get help on an activity type

Every activity type has its own built-in documentation. You can access it with `help <activity type>`

    dsbench help stdout

## Write data to stdout

This example will use the stdout activity type to print 10
cycles worth of data.

    dsbench run type=stdout yaml=baselines/cql-keyvalue.yaml tags=phase:rampup cycles=10

In this example `run` is a command to dsbench. It instructs dsbench to
configure and run an activity. All of the options that follow in `name=value` form are used to parameterize that command. Specfically:

- `type=stdout` tells dsbench which activity type to run. This is essentially a lower-level driver which adapts the concepts of dsbench to a specific target interface. The stdout entry is simply a way to write data to the console for experimentation and testing.
- `yaml=baselines/cql-keyvalue.yaml` tells dsbench which workload definition file to use. This file determines the data bindings, statements, and other things like ratios which ultimately determine the access patterns used in a workload.
- `tags=phase:rampup` is a tag filter which selects only the statements from the workload with the matching tag name and value. By convention statements which are tagged for phase _rampup_ are used to load in data with contiguous identifiers. This allows you to incrementally layer in more data as needed with no holes or overlaps, depending on your key structure.
- `cycles=10` is shorthand for `cycles=0..10`, which means use the sequence of `[0,10)` to control the number of statements, but also the seed value for each of those statements. With dsbench, the cycles become seeds for data, and each command line represents a deterministic workload.

## ... in readout format

Sometimes it is more useful to just see the data associated with each logical statement in an easier to read form. With `type=stdout` you can also specify a format, like `format=readout`.

    dsbench run type=stdout yaml=baselines/cql-keyvalue.yaml tags=phase:rampup cycles=10 format=readout

## Initialize CQL schema

These examples below use one of the built-in workloads, `cql-keyvalue` as a reference point.

This will create a keyspace named testks using SimpleStrategy and replication factor 1:

    dsbench run type=cql yaml=baselines/cql-keyvalue.yaml tags=phase:schema host=dsehost rf=1

The host is simply a node in your cluster. It is used as a contact point
in the driver. If you like, you can pass more than one separated by commas, like `host=node1,node2`.

If this command is succesful, you will see little to no output besides the
logging message telling you where the scenario log was written. In general, dsbench will not bother you with all the details unless you ask for them with the `-v` option, as in

    dsbench -v run type=cql yaml=baselines/cql-keyvalue.yaml tags=phase:schema host=dsehost rf=1

## Write 100000 rows of data

    dsbench run type=cql yaml=baselines/cql-keyvalue.yaml tags=phase:rampup host=dsehost

## Overwrite randomly within 100000 cycles of data

This command specifies that writes should occur on rows
within the first 100000 identifiers. This works because the main phase is configured to do pseudo-random selection of the key values. However, the maximum identifier value is controlled by another parameter named `keycount`.

    dsbench run type=cql yaml=baselines/cql-keyvalue.yaml tags=phase:main,type:write host=dsehost keycount=100000

## Do random reads within 100000 cycles of data

    dsbench run type=cql yaml=baselines/cql-keyvalue.yaml tags=phase:main,type:read host=dsehost keycount=100000

## Do random reads and writes within 100000 cycles of data

    dsbench run type=cql yaml=baselines/cql-keyvalue.yaml tags=phase:main host=dsehost keycount=100000

# Summary

This is not meant to be a substitute for good documentation. It is just to show what you can do at a really basic level if you need to. If you are interested in running test with dsbench, it is highly recommended you download and run it in docserver mode to see the full set of docs.