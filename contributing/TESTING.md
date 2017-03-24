Testing
==

All development should be accompanied with a corresponding unit and (if
applicable) end-to-end test. Feature work will not be approved for merge without
coverage. Similarly, bug fixes will not be approved for merge without a
corresponding regression test.

We use the following suite of tools for tests:

* **Mocha** for unit testing server-side code
* **Chai** for route testing server-side
* **Pretender JS** for creating a mock server routes with Ember/
* **QUnit** default Ember testing framework

[Ember Testing](https://guides.emberjs.com/v2.12.0/testing/) is included with
any Ember application generated using Ember CLI.

[TravisCI](https://travis-ci.com) is used for Continuous Integration and will
run the entire test suite. End-to-end browser tests are executed using the
Firefox browser. All tests must be passing in TravisCI before the feature is
approved for merge.
