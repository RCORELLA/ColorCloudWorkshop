# Lab 2: Deploying an OpenAI Model

## Objective
Deploy an Azure OpenAI Service model for use with Business Central and the Copilot Toolkit.

---

## Introduction: Why an OpenAI Model for Business Central?

### Integration with the Copilot Toolkit

The official Copilot Toolkit codeunits are specifically designed to connect with Azure OpenAI Service endpoints. These include:

- **"AOAI Chat Messages"**
- **"AOAI Operation Response"**
- **"AOAI Chat Completion Params"**
- And other related codeunits

### Connection Requirements

These codeunits expect the following elements:

1. ✅ **An Azure OpenAI Service endpoint**
   - Azure OpenAI service URL

2. ✅ **An Azure OpenAI API Key**
   - Authentication key to access the service

3. ✅ **A model-specific deployment name**
   - Examples: `gpt-4`, `gpt-35-turbo`
   - Name of the model deployment in your Azure resource

---

## Step 1: Create the Azure OpenAI Resource

### 1.1. Access the Azure Portal

1. Open your browser
2. Go to: **https://portal.azure.com**
3. Sign in with your Azure credentials

### 1.2. Create a New Resource

1. In the Azure portal, click **"+ Create a resource"**
2. In the search bar, type: `Azure OpenAI`
3. Select **"Azure OpenAI"** from the results
4. Click **"Create"**

   <img width="1252" height="753" alt="image" src="https://github.com/user-attachments/assets/6c559643-698a-4d6e-9f75-d2371d7a0f82" />

### 1.3. Configure the Resource

Fill in the following fields:

#### **Basics**

- **Subscription**: Select your Azure subscription
- **Resource group**: Select or create a resource group
- **Region**: Choose a region (e.g., East US, Sweden Central)
- **Name**: Enter a unique name for your resource
- **Pricing tier**: Select the appropriate pricing tier

  <img width="708" height="751" alt="image" src="https://github.com/user-attachments/assets/51f40625-9391-4823-ac16-d78fe268c5d3" />

#### **Network**

- Configure network options according to your security needs

#### **Tags**

- (Optional) Add tags to organize your resources

### 1.4. Review and Create

1. Click **"Review + create"**
2. Review the configuration
3. Click **"Create"**
4. Wait for the deployment to complete (may take a few minutes)

<img width="1017" height="666" alt="image" src="https://github.com/user-attachments/assets/eaf8e145-fdf8-4888-a86e-291ca78290ed" />

---

## Step 2: Go to Azure AI Foundry

### 2.1. From the Azure Portal

Once the resource is created:

1. Go to your newly created Azure OpenAI resource
2. In the top menu or in the **Overview** section, look for the button:
   - **"Go to Azure AI Foundry Studio"** or
   - **"Explore Azure AI Foundry"**
3. Click that button

<img width="2028" height="852" alt="image" src="https://github.com/user-attachments/assets/1cebac8b-738b-495a-a94e-efbf508d8f44" />

### 2.2. Direct Access

Alternatively, you can go directly to:
- **https://ai.azure.com/**
- Select your Azure OpenAI resource from the resource list

---

## Step 3: Deploy a Model

### 3.1. Navigate to Deployments

1. In Azure AI Foundry, go to the left side menu
2. Click **"Deployments"** or **"Model deployments"**

### 3.2. Create a New Deployment

1. Click **"+ Create new deployment"**
2. Select the model you want to deploy:
   - **gpt-4** - Most advanced model
   - **gpt-4-turbo** - Optimized version of GPT-4
   - **gpt-35-turbo** - Faster and more cost-effective version
   - **gpt-4o** - Latest optimized model

<img width="1255" height="663" alt="image" src="https://github.com/user-attachments/assets/ba1750e8-026b-4073-a270-1096258184a5" />

### 3.3. Configure the Deployment

- **Deployment name**: Enter a descriptive name
  - Example: `gpt-4-deployment` or `gpt-35-turbo-prod`
  - ⚠️ **Important**: This name will be required in Business Central
- **Model version**: Select the model version
- **Deployment type**: Select the type (Standard or Provisioned)
- **Tokens per minute rate limit**: Configure the token limit

### 3.4. Confirm Deployment

1. Review the configuration
2. Click **"Create"**
3. Wait for the deployment to complete

<img width="697" height="713" alt="image" src="https://github.com/user-attachments/assets/10f6ff48-51cb-4619-aeb2-6981e1c1b5df" />

---

## Step 4: Retrieve Credentials for Business Central

### 4.1. Endpoint URL

1. Go to your resource in Azure AI Foundry
2. In the menu, select **"Keys and Endpoint"** or equivalent
3. Copy the **Endpoint URL**
   - Format: `https://YOUR-RESOURCE.openai.azure.com/`

### 4.2. API Key

1. In the same **"Keys and Endpoint"** section
2. Copy **Key 1** or **Key 2**
3. ⚠️ **Important**: Store this key securely

### 4.3. Deployment Name

- This is the name you gave the deployment in Step 3.3
- Example: `gpt-4-deployment` or `gpt-35-turbo-prod`

---

## Step 5: Test the Model (Optional)

### 5.1. Use the Chat Playground

1. In Azure AI Foundry, go to **"Playgrounds" → "Chat"**
2. Select your deployment
3. Type a test message
4. Verify that the model responds correctly

---

## Summary: Information for Business Central

At the end of this lab, you should have:

| Element | Description | Example |
|---------|-------------|---------|
| **Endpoint** | Service URL | `https://my-resource.openai.azure.com/` |
| **API Key** | Authentication key | `abc123...xyz789` |
| **Deployment Name** | Name of the deployed model | `gpt-4-deployment` |

This information will be needed to configure the Copilot Toolkit codeunits in Business Central.

---

## Important Notes

- 🔒 **Security**: Never share your API Key publicly
- 💰 **Costs**: OpenAI models have associated usage costs
- 📊 **Limits**: Respect the configured rate limits
- 🔄 **Versions**: Keep model versions up to date

---

## Next Steps

In the next lab, you will learn to:
- Configure Business Central with these credentials
- Use the Copilot Toolkit codeunits
- Create your first integration with OpenAI

---

## Troubleshooting

### Error: "Deployment failed"
- Verify that you have available quota in your subscription
- Check that the selected region supports the model

### I don't see the "Go to Azure AI Foundry" button
- Make sure the resource has been fully deployed
- Refresh the Azure portal page

### The model doesn't respond in the Playground
- Verify that the deployment status is "Succeeded"
- Check that you have selected the correct deployment

---

*Instructor: Roberto Corella*  
*LinkedIn: https://www.linkedin.com/in/robertocorella/*  
*Date: October 2025*
