# Laravel SSH Continuous Deployment

This is an example of a Laravel project for continuous deployment over SSH, allowing automatic deployment to your VPS or web hosting that supports SSH.

## How to use it?

### Step 1

Make sure you already made and fill your `.env` file with correct configuration

### Step 2

Copy folder `.github` to your project, especially the files inside `.github/workflows` folder

### Step 3

Create private and public key using command below

``` bash
ssh-keygen -m PEM -t rsa -b 4096
```

Please Note: You should not set a Passphrase (keep it empty) for the private key you generated.

Add public key to `authorized_keys` file on your server

We can use private key later on github action secrets configuration next step.

### Step 4

Open your github repository then open `Settings > Secrets and variables > Actions`

#### Create new repository secret on tab Secrets

| Name                 | Secrets                                                                                     |
|----------------------|---------------------------------------------------------------------------------------------|
| SSH_DEV_PRIVATE_KEY  | your development private key                                                                |
| SSH_DEV_HOST         | your development ssh ip or domain                                                           |
| SSH_DEV_USER         | your development ssh username                                                               |
| SSH_DEV_PORT         | your development ssh port                                                                   |
| SSH_DEV_TARGET_DIR   | project directory on your development server (/var/html/www or /home/username/your-project) |
| SSH_PROD_PRIVATE_KEY | your production  private key                                                                |
| SSH_PROD_HOST        | your production  ssh ip or domain                                                           |
| SSH_PROD_USER        | your production  ssh username                                                               |
| SSH_PROD_PORT        | your production  ssh port                                                                   |
| SSH_PROD_TARGET_DIR  | project directory on your production server (/var/html/www or /home/username/your-project)  |
