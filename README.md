# go-promexporter

Query used:
sum(rate(http_requests_total{path="/", container_name="httpmetrics"}[2m]))

Commands to run:

Sanity: k port-forward services/httpmetrics-service 8080:8080

Watch Deployment: k get deploy httpmetrics-deployment --watch

Check HPA: k get hpa

Put load: hey -n 2000 http://localhost:8080