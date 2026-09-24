Turns a file back into an object graph, and writes one back out.

The types are not known beforehand. They are read from the file or resolved through the
type analyzer, which is what lets an editor open a data model it has never seen.

A load that fails says why - not readable, not valid JSON, wrong root type - instead of
throwing something for the caller to interpret. And before writing, a dictionary with an
object as its key is examined: those entries have no plain form in JSON, so what would
be lost is named rather than dropped in silence.

Targets net9.0, because loading an assembly into a context of its own needs it.
