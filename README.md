This is a small Kubernetes charm based on [From zero to hero: Write your first Kubernetes charm](https://canonical.com/juju/docs/ops/latest/tutorial/from-zero-to-hero-write-your-first-kubernetes-charm/). The charm requires a PostgreSQL database and supports observability apps from the COS Lite bundle.

The charm's integration tests are slightly different from the *zero to hero* charm:

- The tests that deploy the charm and integrate it with PostgreSQL are marked `smoke`.
- There's an extra test that exercises the workload over HTTP.
- There are extra tests that integrate the charm with Prometheus and Grafana (the *zero to hero* charm already tests the Loki integration).

The charm's CI workflows are based on [How to set up continuous integration for a charm](https://canonical.com/juju/docs/ops/latest/howto/set-up-continuous-integration-for-a-charm/). There's an extra workflow that uses [jjx](https://github.com/dwilding/jjx) to simulate the charm's integration tests (approx 70% faster than the integration test workflow).
