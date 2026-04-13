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

## Step 2: Preparing the CSV Template
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

<p align="center">
  <img src="/images/demo5.gif" width="550"/>
</p>

Now I’ve moved into the next phase — uploading the CSV template.

In the GIF above, I’m uploading the CSV file that I’ve already injected with the correct candidate details, including their names, user principal names, and initial passwords.

Right below this paragraph, I’ve included supporting visuals to show the outcome of this process.

The first screenshot captures the successful upload, confirming that the file was processed without errors and that everything in the template was formatted correctly.

<p align="center">
  <img src="/images/userprocess.jpg" width="550"/>
</p>


In the GIF that follows, I refresh the environment after the upload to validate the changes, showing that all users have been successfully created.

<p align="center">
  <img src="/images/demo6.gif" width="550"/>
</p>

## Step 4: Creating and Reviewing Groups

<p align="center">
  <img src="/images/demo7.gif" width="550"/>
</p>

Now I’m moving into the next phase — creating and reviewing groups.

At this stage, I create dynamic groups to align with the three departments defined in the ticket: **Cloud Operations**, **Security Operations Center (SOC)**, and **Governance, Risk, and Compliance (GRC)**. Each department is separated into its own group to ensure proper organization and access control.

I specifically chose **dynamic groups** because they significantly reduce administrative effort. Instead of manually assigning each user, Azure automatically places users into the correct group based on their attributes — in this case, the department field defined in the CSV.

This means as long as the user’s department is correctly set, they are automatically assigned to the appropriate group without any **manual intervention**.

Below this section, I’ve included the dynamic membership rules used for each group, showing exactly how users are automatically assigned based on their department attributes.

You’ll also notice that I created a total of four dynamic groups. I’ll explain later why I included an additional group for **SSPR and an “All Departments”** grouping as part of the overall design.


**SOC Dynamic Rule Screenshot**

<p align="left">
  <img src="/images/grcscreen.jpg" width="450"/>
</p>

**GRC Dynamic Rule Screenshot**

<p align="left">
  <img src="/images/socscreen.jpg" width="450"/>
</p>

**CloudOps Dynamic Rule Screenshot**

<p align="left">
  <img src="/images/cloudscreen.jpg" width="450"/>
</p>

## Step 5: Assigning Licenses

<p align="center">
  <img src="/images/demo8.gif" width="550"/>
</p>

Now I’m moving into **Step 5 — Assigning Licenses**, which is one of the most important parts of this entire process.

In the **GIF above**, I demonstrate how I navigated into the groups I previously created. For this walkthrough, I show one example, but the same process applies across all groups.

Instead of assigning licenses to each user individually, I used **group-based licensing**. This means I assign the license directly to the group, and all users within that group automatically inherit the license.

This approach makes the process significantly more **efficient**, especially when working with a large number of users. It eliminates the need for repetitive manual work and ensures consistency across the organization.

As a result, every user within the group receives the appropriate license based on their assigned department.

In the **screenshot below**, I show a validation step where a user within the group has **successfully inherited** the license — confirming that the group-based licensing was applied correctly according to the defined scope.

<p align="center">
  <img src="/images/licensepic.jpg" width="650"/>
</p>

## Step 6: Enabling Self-Service Password Reset (SSPR) to Reduce Helpdesk Dependency

<p align="center">
  <img src="/images/demo9.gif" width="550"/>
</p>

Now I’m moving into Step 6 — **Enabling Self-Service Password Reset (SSPR)** to reduce help desk dependency.

This is a critical part of creating a secure Azure environment. Users will inevitably forget their passwords, and without SSPR, this would require constant intervention from an administrator to reset accounts.

To avoid that, I enabled **Self-Service Password Reset (SSPR)** — a powerful feature in Azure that allows users to securely reset their own passwords without relying on the help desk.

Instead of enabling this feature user by user, I applied it at the group level. I scoped SSPR to a group that contains all relevant users, which ensures that everyone within that group is automatically covered without any manual selection.

In the GIF above, I demonstrate how I configured and enabled SSPR for the group and saved the configuration.

In the screenshot below, I show the **authentication methods** configured for SSPR — including the security questions that users must set up as part of the verification process.

**Authentication Methods**
<p align="left">
  <img src="/images/authpic.jpg" width="550"/>
</p>

**Security Questions**
<p align="left">
  <img src="/images/authpic2.jpg" width="550"/>
</p>



With this in place, users are able to securely manage their own password resets, reducing administrative overhead while maintaining strong security practices.

At this point, the onboarding and configuration process is **complete**.

# Thank you for the Read 
<p align="center">
  <img src="/images/defendk.jpg" width="550"/>
</p>

My name is Kemton, and I’m an Azure Administrator focused on cloud administration with a strong interest in security.

I currently hold **CompTIA Security+** and **AZ-900** (Azure Fundamentals), and I’m actively working towards earning my AZ-104 (Azure Administrator) certification.

If you’d like to connect or follow my journey, feel free to check out my LinkedIn — it’s included in the image above.

I appreciate you taking the time to go through this project. I hope it was helpful, practical, and gave you real insight into how these processes are handled in a real-world environment.

