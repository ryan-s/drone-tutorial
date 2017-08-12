# ci-integ-test-example

Drone IO integration test project

This will be a mini application with 2 parts:
1. frontend (react/redux micro-app)
2. micro-app backend (Golang or Python...)

This would all be wrapped in docker containers and have tests:
1. Unit tests (mocha and ginkgo)
2. Integration tests  (mocha and ginkgo) running in seperate proces
3. e2e test - selenium headless or something
4. Perf tests using protractor

All wrapped in docker containers and sent to the drone io army for build, test, publish...

Lets see how far I make it.
