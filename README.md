# How-I-Onboarded-85-Cybersecurity-Interns-in-Azure-Using-a-One-Click-Workflow

This is how I achieved it.

Below you will find a GIF that walks through the full process. If it has not loaded yet, give it a few seconds and it will appear.

This project is based on a simulated **JIRA Ticket** designed to reflect a real world scenario.

The task required me to onboard **85 cybersecurity interns** and structure them across three operational teams

✅ Cloud Operations

✅ Security Operations

✅ Governance, Risk and Compliance

My responsibility was to ensure each user was properly provisioned in Microsoft Entra ID with the correct group assignments, access controls, and licensing so that every intern could securely access the systems they need from day one.

<p align="center">
  <img src="/images/demo4.gif" width="700"/>
</p>

## Breaking Down My Thinking

First, let me take you through my approach

<br>

Creating 85 user accounts manually would not make sense in a real business environment

It is time consuming
and increases the risk of errors

<br>

So I focused on a more structured and practical approach
one that aligns with how this is handled in production

<br>

Before implementing anything
I mapped out the full process in my mind

to ensure the solution is

✅efficient
✅consistent
✅secure
<br>

The diagram below shows how I structured this solution for the business

<p align="center">
  <img src="/images/internmind.png" width="550"/>
</p>

## **Step 1**: Navigating to Microsoft Entra ID
<p align="center">
  <img src="/images/01entra-home.gif" width="550"/>
</p>

I started by accessing Microsoft Entra ID, which is where I would manage identity, user provisioning, group membership, and password reset settings for the new interns.

## Step 2: Preparing the CSV template
<p align="center">
  <img src="/images/02-csv-template.gif" width="550"/>
</p>

In the GIF above, I navigate through Microsoft Entra ID to locate one of the most efficient features Azure provides — the Bulk Operations option.

Instead of creating users one by one, I click on Bulk operations → Create, which allows me to streamline the entire onboarding process.

From there, I download the CSV template that Azure provides. This template becomes the foundation for defining all 85 users in a structured and scalable way before uploading them into the environment.

## Screenshots Of CSV Templates

With the two screenshots below, I’m showing a clear before-and-after of how I prepared the bulk user file.

In the first screenshot, this is the original CSV template exactly as I downloaded it from Azure untouched and ready to be populated.

<p align="center">
  <img src="/images/csvtemp1.jpg" width="550"/>
</p>

In the second screenshot, this is after I injected the data provided by HR. I populated the file with each candidate’s name, user principal name, and an initial password for first-time access.

It’s **important** to note that these **passwords** are only **temporary**. Each user is required to change their password as soon as they sign in for the first time, ensuring the environment remains **secure** from the start.

<p align="center">
  <img src="/images/csvtemp2.jpg" width="550"/>
</p>

Now that I’ve injected all the appropriate candidate details into the CSV file, I’m ready to move into the next phase — uploading.

At this point, I make sure to save the file properly so that it’s ready to be uploaded in the next step using the Bulk Operations feature in Azure.

## Step 3: Uploading the CSV file
