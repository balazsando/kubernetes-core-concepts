# Create a secret and store securely in kubernetes
kubectl create secret generic my-secret --from-literal=pwd=my-password

# Create a secret from a file
kubectl create secret generic my-secret
    --from-file=ssh-privatekey=~/.ssh/id_rsa
    --from-file=ssh-pulickey=~/.ssh/id_rsa.pub

# Create a secret from a key pair
kubectl create secret tls tls-secret --cert=path/to/tls.cert
    --key=path/to/tls.key

# yaml is only base64 encoded... not a strong encryption

# Get secrets
kubectl get secrets

# Get YAML for specific secret -- base64 encoded
kubectl get secrets db-passwords -o yaml