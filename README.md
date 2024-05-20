# ermine
SQL Server Backed Event Store

First off, don't get too excited because it's going to be a little while before there's too much happening here.

## Goals and Approach

* Robust Event Store functionality using SQL Server as the storage mechanism
* Closely based on Marten's event sourcing functionality, i.e., basically Marten's `IEventStore` service
* Possibly avoid having to use Marten's unit of work mechanics, but think about that
* Opt into the bigger Critter Stack "stateful resource" model with Weasel to build out schema objects
* Support both conjoined and separate database multi-tenancy
* **No code generation this time**, so maybe wait until Marten gets the 100% explicit alternative for projections
* Research the idea of sharing code with Marten, but not at the expense of making this harder
* Support projections, but the default will project to simple JSON stored tables
* STJ only for the serialization
* Only really support load by key for the projected documents. No LINQ support
* Probably going to have to play nicely with EF Core for projections
* Take the dependency right off the bat on Wolverine and recreate the "aggregate handler workflow" from Wolverine.Marten ???
* Support projections through Wolverine right off the bat

