# Lab: Initial Azure OpenAI Setup

## Objective
Access the Azure OpenAI portal and familiarize yourself with the available resources.

---

## Step 1: Access the Portal

1. Open your web browser
2. Go to the URL: **https://ai.azure.com/**
3. Sign in with your Azure credentials

---

## Step 2: Explore the Azure AI Foundry Portal

Once inside the portal, you'll see the main interface with the following sections:

### Left Side Menu

#### **Home**
- Portal main page

#### **Get started**
- Resources and tutorials to get started

#### **Model catalog**
- Catalog of available AI models

#### **Playgrounds**
- **Chat**: Interface for testing conversational models
- **Assistants** (PREVIEW): Create custom assistants
- **Video** (PREVIEW): Video processing tools
- **Audio** (PREVIEW): Audio processing tools
- **Images**: Image generation and processing

#### **Tools**
- **Fine-tuning**: Model fine-tuning
- **Azure OpenAI**: OpenAI resource management

---

## Step 3: Review Recent Resources

In the central panel you'll see the **"Recent resources"** section showing:

### Available Resources

1. **customer360** (Azure OpenAI - eastus) — Main OpenAI resource
2. **usOpenAiwithDalle** (Azure OpenAI - eastus) — Resource with DALL-E capabilities
3. **customer360** (Project Default - eastus) — Default project with AI Foundry resource

---

## Step 4: Create a New Project

### 4.1. Start Creation

1. In the main panel, click the **"+ Create new"** button
2. Select **"Project"**

### 4.2. Basic Project Configuration

On the "Create a project" screen, fill in the following fields:

<img width="739" height="759" alt="image" src="https://github.com/user-attachments/assets/28425ec1-bcce-4c7d-a353-9b99f2fecfd7" />

#### **Project Name** *
- Enter a descriptive name for your project
- Example: `Demo-Companial`

### 4.3. Advanced Options

Expand the **"Advanced options"** section to configure:

#### **Azure AI Foundry resource** *
- Name of the Azure AI Foundry resource
- Example: `demo-companial-resource`

#### **Subscription** *
- Select your Azure subscription
- Example: `rcorella`
- If you need to create a new one: click **"Create a new subscription"** 🔗

#### **Resource group** *
- Select an existing resource group or create a new one
- Example: `(new) rg-rcorella-3874`
- To create a new group:
  1. Type the name of the new group
  2. Click **"Create new resource group"**
  3. Enter the name (e.g., `Demo-Companial`)
  4. Click **"OK"**

#### **Public network access**
- Status: **Enabled** (enabled by default)
- Allows access from the public internet

#### **Region** *
- Select the region where the project will be hosted
- Example: `Sweden Central`
- Other common options: East US, West Europe, etc.

### 4.4. Policies and Security

At the bottom you'll see:
- Link to data, privacy and security policies
- **"Configure in Azure Portal"** 🔗 — For advanced configuration

### 4.5. Create the Project

1. Verify that all required fields (*) are complete
2. Click the blue **"Create"** button
3. Alternatively, click **"Cancel"** to cancel

### 4.6. Setup Process

Once creation has started, you'll see a screen with:

- **"Welcome to Azure AI Foundry"**
- **"Jumpstart your AI journey"** — Description of capabilities
  - Search for ideal models from OpenAI, Mistral, Meta, and other providers
  - Link, test, and customize within a project
  - **"Explore models"** button to get started

---

## Step 5: Confirm the Endpoints

<img width="991" height="886" alt="image" src="https://github.com/user-attachments/assets/1799a091-2ea3-47e9-b7cf-d7c87d4b0f3c" />

## Step 6: Choose the Model

<img width="1591" height="753" alt="image" src="https://github.com/user-attachments/assets/34aa5e94-d0d9-4ab2-8c91-ac75addd3415" />

## Step 7: Deploy to a Web App

<img width="1154" height="917" alt="image" src="https://github.com/user-attachments/assets/63300be2-abe7-442b-ab14-9da94675749b" />

Once deployed, you'll be able to access the web app.

<img width="670" height="909" alt="image" src="https://github.com/user-attachments/assets/6ae73a2d-5e78-498a-85ad-a9ad98f34319" />

<img width="1182" height="711" alt="image" src="https://github.com/user-attachments/assets/d5efc74d-87df-4f25-99ec-1be2fd1e5ebd" />

---

## Important Notes

- The default region for these resources is **East US**
- Some services are in **PREVIEW**
- You can search for specific resources using the search bar at the top

---

## Next Steps

Once familiar with the portal:
1. Explore the **Model catalog** to see available models
2. Try the **Chat Playground** to interact with the models
3. Review the documentation under **Get started**

---

## Additional Resources

- Portal: https://ai.azure.com/
- Official Azure OpenAI documentation
- Examples and tutorials in the portal

---

*Instructor: Roberto Corella*  
*LinkedIn: https://www.linkedin.com/in/robertocorella/*  
*Date: October 2025*
