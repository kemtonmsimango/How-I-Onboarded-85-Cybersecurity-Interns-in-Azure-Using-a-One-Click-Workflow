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
