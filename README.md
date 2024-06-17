# Deploud.com

<img src='./logo-deploud.svg' alt='Deploud Logo' width="250px" />

[Site here](https://deploud.com)

Deploud helps you deploy your app to AWS, GCP, and Azure with a [b]single command[/b]. 

Deploud is supporting the deployment of a Docker Image to Google Cloud Run Instantaneously.

## Why I Built Deploud

Deploud is designed for people who:

- **Want to save scarce engineering time**: Handling infrastructure is not your core business. You want to focus on delivering value to your customers, not on setting up services and permissions.
- **Don't want to struggle with piecing together documentation**: Are tired of inconsistent APIs, naming conventions, and data models across cloud services, and the nuanced limitations that hinder expected functionality.
- **Hate dealing with obtuse errors because of security limitations**: Have you had cryptic error messages like "exec format error" or "Cloud Run Admin API has not been used in project..."? We've been there. We've done that. That's why Deploud produces verified scripts.
- **Save costs**: Don't pay for wrapper services like Vercel, Fly, Netlify when you can go directly to the provider.
- **Want to create a custom solution**: We simplify the hard stuff: Making sure the services we select, connect to each other properly. As we don't abstract the cloud provider, you can pair and customize your services however you want. There's no Deploud lock-in. You can take the code and run it.

## How It Works

### Quickly deploy your project with a single command

Deploud will generate a .zip that contains all the files you need to get your application deployed. It contains the following files:

- **cli**: Command Line Interface tools
- **pulumi**: Pulumi scripts
- **scripts**: Deployment scripts
- **gen.bash**: Generation script
- **del.bash**: Deletion script
- **config.json**: Configuration file

You should unzip them somewhere in your project (e.g., `<root>/deploy`). You will be able to customize the paths to the Docker file within Deploud (recommended) or the included config.json.

The scripts will:
1. Install the required CLI tools (gcloud, expect, docker, jq, pulumi, golang).
2. Configure the required permissions in GCloud.
3. Scaffold the right Pulumi scripts for you.

You will be able to inspect what each of the scripts do. These have a single point of entry, the gen.bash script (and del.bash to remove the instances).

These scripts are **idempotent**. This means you can run them as many times as you want and they will not create duplicate resources.

### Run the Code

Navigate to the folder where you unzipped the files and run the following command:
```bash
bash gen.bash
```

### Delete the cloud resources:
This will not delete your files. 
```bash
bash del.bash
```


## Key Features

![Deploud](./logo-deploud.svg)

**Deploy Your Docker Image to Google Cloud Run Instantly**: Automate Your Cloud Deployments with a Single Command – Scaffold, Customize, and Own Your Deployment Scripts.

### The Problem

I spent 21.4 hours not delivering value to my customers because I...

- Had to spend **7+ hours navigating and piecing together documentation** to upload to Google Cloud Run.
- Deal with **obscure and obtuse errors** like "exec format error" or "Cloud Run Admin API has not been used in project...".
- **Failed to get the right answer** with Gemini and ChatGPT.
- **Got lost setting up service accounts, roles, and permissions**—it was a nightmare.
- Had to **orchestrate services with Pulumi** to ensure each one was enabled correctly.

I wished for a solution that could handle the upload for me **without the extra costs of wrapper services like Vercel, Netlify, and Fly**.

**I just want to deploy!**

## System Requirements

A bash-supported environment:
- **Windows Subsystem for Linux (WSL)**
- **macOS**
- **Linux**

![System Requirements](./images/system-requirements.png)

## Issues

Please use this GitHub repository to submit any issues you encounter. Your feedback is invaluable to us.

---

Thank you for choosing Deploud!
