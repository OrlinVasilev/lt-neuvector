### Demo for Lightening talk for Cyber Security Talks Bulgaria January 14th  #32
https://www.eventbrite.dk/e/32-cyber-security-talks-bulgaria-tickets-1141259189959
https://www.meetup.com/cyber-security-talks-bulgaria-meetup-group/events/305481883/?eventOrigin=group_upcoming_events

# NeuVector

## Install NV

We are going to install with helm from the official Open Source Channels
https://github.com/neuvector/neuvector-helm

```bash
helm repo add neuvector https://neuvector.github.io/neuvector-helm/
helm install neuvector --namespace neuvector --create-namespace neuvector/core
```

## Access the Console
```bash
NODE_PORT=$(kubectl get --namespace neuvector -o jsonpath="{.spec.ports[0].nodePort}" services neuvector-service-webui)
NODE_IP=$(kubectl get nodes --namespace neuvector -o jsonpath="{.items[0].status.addresses[0].address}")
echo https://$NODE_IP:$NODE_PORT
```
user: admin/admin