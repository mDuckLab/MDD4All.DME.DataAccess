# MDD4All.DME.DataAccess

Reads and writes the object graph of MDD4All.DME, the object graph editor application.

A file is turned back into objects without the application knowing their types beforehand, which is what the load context and the type analyzer are for. Dictionaries with a complex key get their own treatment: JSON has no place for an object as a key, so they are either written in a form that survives the round trip or reported as what would be lost.
