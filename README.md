This is a work in progress experiment PoC of rewriting OctoSQL in Rust, as I've been seeing 10-100x performance improvements using a more optimized design.

# Roadmap
The current roadmap is to achieve feature parity with the Go version of OctoSQL. When this is done, we'll decide which one gets to stay.

- [x] Projection
- [x] Filter
- [x] GroupBy
  - [ ] Support all types
  - [ ] More aggregates
  - [ ] StarExpression
- [x] Triggers
  - [x] Counting
  - [ ] Delay
- [x] Retractions
  - [x] Add retractions to Projection (don't allow the user to remove the retraction column)
- [x] Stream join
  - [ ] Float support (currently not tested and possibly wacky)
- [ ] Expressions
  - [x] Evaluation in record context.
  - [x] Evaluation in execution context of variables (if we're in a subquery, we need to understand both the current record, and variables stemming from record flows above us)
  - [ ] Common functions / operators. (Currently only Equals)
- [x] Map (evaluate expressions, this is the only place where expressions are evaluated in OctoSQL, everything else gets evaluated expressions passed from here by name)
  - [ ] StarExpression
- [ ] Watermarks
  - [ ] Metadata Message and Handling
  - [ ] Watermark trigger
  - [ ] Watermark generators
	- [ ] Start with Max difference
- [ ] Shuffle
- [x] Subqueries
  - [ ] Handle all primitive types
  - [ ] Handle multiple columns/rows (Tuple values)
- [ ] Lookup join
- [x] Physical Plan (fit for pattern matching)
  - [ ] Basic optimiser
  - [ ] Pushing down projections
  - [ ] Pushing down filters
- [x] Logical Plan
- [x] SQL
  - [ ] Temporal Extensions
- [ ] Nice output printing
- [ ] Datasources
  - [x] CSV
  - [ ] MySQL
  - [ ] PostgreSQL
  - [ ] JSON
  - [ ] Parquet
  - [ ] Excel
  - [ ] Kafka
- [ ] Durations and Dates support

# Contributing
Contributions are welcome!

Please open an issue or contact me personally when you want to try to contribute, so that no work gets duplicated or thrown away.
