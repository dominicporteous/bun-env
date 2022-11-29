# bun-env

Reproducing inconcistencies with interacting with process.env between Node and Bun.

You must use a build of Bun at least version `0.3.0` (using `bun upgrade --canary`)

## Expected behaviour 

Tests should all pass. 

Run tests on Node via `node options.test.node.js`
Run tests on Bun via `bun wiptest options.test.js`

## Actual behaviour 

Tests which are manipluating process.env (simulating that env variables are being set and unset for different tests) behave correctly in Node, however in Bun it seems that the unset operations are not being applied and therefore the env variables set are being persisted across test cases.

## Notes

Tests are an excerpt from bun-commander, which is amining to port commanderjs functionality into Bun.

