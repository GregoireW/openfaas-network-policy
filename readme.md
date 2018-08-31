***Some ingress policy for openfaas***

This is a small network policy example that we can use for `openfaas` namespace.

It is ingress based rule. There is 2 files : `generic.yml` and `specific.yml`. The specific file need to be updated as per your need  


- generic.yml
  - deny all ingress
  - gateway -> nats
  - queue-worker -> nats
  - prometheus -> alertmanager
  - prometheus -> gateway
  - alertmanager -> prometheus
  - alertmanager -> gateway
- specific.yml
  - grafana from an outside namespace -> prometheus
  - ingress controller from an outside namespace -> gateway (mandatory to connect to openfaas from the outside)

