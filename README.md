# Hey! you're using Shir's app

### to make it work you should change the external IP 

**Follow this steps:**

1. kubectl get service server-service -n <your-namespace> | tail -1 | awk '{print $4} <br />
   copy the ip address you got
2. Change the server/values.yaml file the value of: service.externalIP
3. run this command: helm upgrade server server/ --values server/values.yaml
4. Restart the client pod: kubectl delete pod -n <your-namespace> <pod-name> <br />
   you can get that: kubectl get pod -n <your-namespace>
