## Go implementation of Raft consensus algorithm

Raft description: https://raft.github.io/

Needs assert package, fetch using `go get github.com/stretchr/testify/assert`


## Test

simply run using `go test` in the parent directory, the console will print status messages detailing everything

For viewing, output log into file with `go test > log.log` then `cat log.log | less` this will allow you to render to output better than vim, and be able to view log messages

change # of testing services by assigning `n` a different value in `raft_test.go`

## Status
* [x] Leader election
* [x] Log replication
* [ ] Consistent state machines
    * [ ] If leader executed a command and crashed, then client retries the same
      command with a new leader. This way state will be changed two times.
      Will be nice to send a unique serial number with all the commands.
      (See section 8: "Client integration" for more)
* [ ] Live configuration changes (e.g. number of nodes)
* [ ] State restoration (transfer snapshots)
* [ ] Log compaction
