---
title: Learn to Run - Connection Credentials
parent: Course Admin
nav_order: 1
---

Welcome to "Learn to Run". Here are some of the artifacts you will need for the practical elements of the course

### Logging into your instance

- You will need to connect to your instance using SSH. In order to authenticate you will need a private key:

    ```bash
    -----BEGIN OPENSSH PRIVATE KEY-----
    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
    -----END OPENSSH PRIVATE KEY-----
    ```

- This key should be treated as a secret. It will be rotated at the end of the course
- Paste it into a text file called my-key.pem, accessible from your terminal
- Connect using the connection string on the students page
