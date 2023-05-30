Install kubeseal - kubectl apply -f https://github.com/bitnami-labs/sealed-secrets/releases/download/v0.15.0/controller.yaml  
Download key from logs once kubeseal controller is up and running or via kubectl command - kubectl get secret sealed-secrets-key<ID> -o yaml -n kube-system  

Sealing sensitive info - echo -n something-secret | kubeseal --raw --namespace argocd --name mysecret --scope namespace-wide --cert ~/.ssh/kubeseal.pem  
