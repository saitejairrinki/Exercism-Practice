To install an SSL certificate for Apache using Certbot on Ubuntu, follow these steps:

1. **Update Ubuntu Apt Repository List:**

    Update the package repository list to ensure you're getting the latest packages:

    ```bash
    sudo apt update
    ```

2. **Install Snapd:**

    Install snapd package and set it up:

    ```bash
    sudo apt install snapd -y
    sudo snap install core;
    sudo snap refresh core
    ```

3. **Install Certbot:**

    Install Certbot using snap:

    ```bash
    sudo snap install --classic certbot
    ```

4. **Prepare the Certbot Command:**

    Create a symbolic link for Certbot:

    ```bash
    sudo ln -s /snap/bin/certbot /usr/bin/certbot
    ```

5. **Install SSL Certificate for Apache:**

    Use Certbot to install an SSL certificate for Apache:

    ```bash
    sudo certbot --apache --non-interactive --keep-until-expiring --renew-with-new-domains --agree-tos --email <email_id> --no-eff-email --domains "<domain_name>"
    ```

    Replace `<email_id>` with your email associated with the SSL certificate and `<domain_name>` with your domain name.

    The `--apache` flag tells Certbot to use the Apache plugin for installation.

Please note that these steps are based on the information you provided in your original question. Make sure to replace `<email_id>` and `<domain_name>` with your actual email and domain. Additionally, ensure that your Apache server is correctly configured to serve the domain you're installing the SSL certificate for.

After running the Certbot command, it will guide you through the process of obtaining and installing the SSL certificate, updating your Apache configuration, and reloading the Apache service. Once the process is complete, your website should be accessible over HTTPS with the newly installed SSL certificate.
