This project was created to demonstrate a bug with AWS SAM local invocation and utilization of the Sentry lambda layer.


This was generated automatically with the `sam init` generator on version 1.53.0.


To reproduce, run:
`sam local invoke -e events/event.json`

Expected:
- Sample JSON output returned in about 20ms


Actual:
- The function times out after 60 seconds.


If you remove the lambda layer from `template.yaml` the function no longer times out. Note: No sentry code is called at all, just adding the lambda layer is enough to cause a timeout.