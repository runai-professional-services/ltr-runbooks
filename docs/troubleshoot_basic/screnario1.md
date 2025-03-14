---
title: Stuck at Login
nav_order: 1
parent: Troubleshooting Basics
---

# Troubleshooting Basics - Scenario 1

## UI Stuck at Login Screen

*Note: Your instructor will apply a failure to your running cluster to replicate a common failure*

### Scenario

A user has just reported an issue logging into the platform. They claim that they are using the correct credentials, however, once logged in, they are re-directed back to the login page.

### Troubleshooting

#### Attempt to replicate

- Log out of the platform and attempt to replicate the issue. You will notice that the report was correct and you are unable to log into the UI.

### Potential Issue 1 - Time Skew in Kubernetes Nodes

#### Check clocks on nodes

- Connect to the cluster using K9S; (This is already installed in your environment)

    ```bash
    k9s
    ```

- Obtain a shell on each of the nodes and run the `date` command

    ```bash
    date
    ```

- Note the time on each of the nodes and apply NTP / correct as necessary

### Potential Issue 2 - Expired Certificates

#### Recover the certificate for inspection

- Using kubectl, recover and decode the `runai-backend-tls` secret in the `runai-backend` namespace

    ```bash
    kubectl get secret runai-backend-tls -n runai-backend \
        -o jsonpath='{.data.tls\.crt}' | base64 --decode
    ```

#### Decode the certificate

- Go to [this link](www.sslshopper.com/certificate-decoder.html) and paste the top certificate from the bundle into the dialogue box.
- Check the expiry date of the certificate

#### Update to a valid certificate

- The certificate expired and is no longer valid. Replace the certificates with the valid ones found in ~/Artifacts/certificates
  
#### Create a new secret with kubectl

- Use the provided certificates to create a new secret. First though, you'll need to delete the old ones:

    ```bash
    kubectl delete secret runai-backend-tls -n runai-backend
    kubectl delete secret runai-cluster-domain-tls-secret -n runai
    ```

- Now create the new ones

    ```bash
    kubectl create secret tls runai-backend-tls -n runai-backend \
        --cert ./certificates/fullchain.pem --key ./certificates/private.pem

    kubectl create secret tls runai-cluster-domain-tls-secret -n runai \
        --cert ./certificates/fullchain.pem --key ./certificates/private.pem
    ```

#### Attempt to log into the cluster

- You should now have restored access to the cluster
