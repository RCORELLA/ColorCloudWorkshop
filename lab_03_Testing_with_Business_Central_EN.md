# Lab03 - Testing AI in Business Central

## Objective
In this lab you will learn how to integrate and test AI capabilities in Business Central using Azure OpenAI. You will configure a custom extension and verify its functionality with real customer data.

## Prerequisites

Before starting this lab, it is **essential** to have completed Lab02 and have:

- ✅ [Lab02](https://github.com/RCORELLA/AprendeBusinessCentralWorkshopsPublic/blob/main/lab_02_deploy_openAI.md) fully functional
- ✅ Azure OpenAI deployed with the necessary connection details
- ✅ Access to a Business Central environment where you can install extensions

## Step 1: Download the Extension

Download the extension file from the repository:

📦 [Roberto Corella - Aprende Business Central_LAB00 - Testing AI Foundry_1.0.0.0.app](https://github.com/RCORELLA/AprendeBusinessCentralWorkshopsPublic/blob/main/Roberto%20Corella%20-%20Aprende%20Business%20Central_LAB00%20-%20Testing%20AI%20Foundry_1.0.0.0.app)

> **Note:** Make sure to save the .app file in an accessible location on your machine.

## Step 2: Install the Extension in Business Central

1. Access your **Business Central** environment
2. Search for the **Extension Management** page
3. Click **Upload Extension**
4. Select the `.app` file downloaded in the previous step
5. Wait for the installation process to finish
6. Verify that the extension appears as **Installed** in the list

## Step 3: Configure ABC AI Setup

Once the extension is installed, you need to configure the connection parameters for Azure OpenAI:

1. Search for and open the **ABC AI Setup** page
2. Fill in the following fields with the information from Lab02:
   - **Endpoint**: URL of your Azure OpenAI service
   - **API Key**: Service access key
   - **Deployment Name**: Name of the deployed model (e.g., gpt-4, gpt-35-turbo)
   - Any other specific configuration parameters

<img width="1870" height="495" alt="image" src="https://github.com/user-attachments/assets/31b28915-75f1-45c3-a9a2-dc51dc947ba9" />

> ⚠️ **Important:** Make sure all data matches exactly with your Azure OpenAI deployment from Lab02.

## Step 4: Test the Functionality

Now it's time to verify that everything works correctly:

1. Go to the **Customers** list
2. Open the **Customer Card** for any customer
3. Locate the **Copilot** button called **ABC Ask me Anything**
   <img width="782" height="403" alt="image" src="https://github.com/user-attachments/assets/50b0e0a5-e860-4ca2-b9ab-7ae02c4ee2fb" />

5. Click the button
6. Run a test query, for example:
   - "How do I create an invoice in Business Central?"
   - "Can you explain dimensions in Business Central?"

## Success Verification

✅ If everything is configured correctly, you should:
- See the Copilot panel open when clicking the button
- Receive coherent responses based on Business Central
- See no connection error messages

## Troubleshooting

If you encounter issues:

| Problem | Solution |
|---------|----------|
| Connection error | Verify that the Endpoint and API Key in ABC AI Setup are correct |
| Button doesn't appear | Confirm that the extension is installed and activated |
| Incoherent responses | Verify the model's Deployment Name in the configuration |
| Permission error | Make sure you have permissions to use the extension |

## Additional Resources

- [Complete workshop repository](https://github.com/RCORELLA/AprendeBusinessCentralWorkshopsPublic)
- [Lab02 - Deploy OpenAI](https://github.com/RCORELLA/AprendeBusinessCentralWorkshopsPublic/blob/main/lab_02_deploy_openAI.md)

## Conclusion

Congratulations! You have successfully integrated AI capabilities into Business Central. This setup allows you to explore how artificial intelligence can enhance the user experience and provide insights based on business data.

---

**Next step:** Experiment with different types of queries and explore the possibilities of AI in other Business Central modules.

---

*Instructor: Roberto Corella*  
*LinkedIn: https://www.linkedin.com/in/robertocorella/*  
*Date: April 2026*
