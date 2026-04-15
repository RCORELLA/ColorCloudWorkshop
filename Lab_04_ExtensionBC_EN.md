# Lab-04: Business Central Extension with AI - OpenAI Integration

## Objective

Create an extension for Microsoft Dynamics 365 Business Central that integrates OpenAI from the customer card, using a Prompt Dialog Page with question guides (Prompt Guides).

Fill in the TODOs so we can display the page.

## Prerequisites

- Visual Studio Code installed
- AL Language extension for VS Code
- Business Central Development Environment (Sandbox)
- Basic knowledge of AL Language

## Project Structure

```
Lab-05-BC-OpenAI/
├── .vscode/
│   └── launch.json
├── src/
│   ├── page/
│   │   ├── CustomerCardExt.PageExt.al
│   │   └── OpenAIPromptDialog.Page.al
│   ├── codeunit/
│   │   └── OpenAIIntegration.Codeunit.al
│   └── enum/
│       └── CopilotCapability.Enum.al
├── app.json
└── README.md
```

## Step 1: Initial Setup

### 1.1 Create the `app.json` file

```json
{
  "id": "12345678-1234-1234-1234-123456789012",
  "name": "OpenAI Customer Assistant",
  "publisher": "Your Name",
  "version": "1.0.0.0",
  "brief": "OpenAI integration in the customer card",
  "description": "Extension that allows querying OpenAI from the customer card",
  "privacyStatement": "",
  "EULA": "",
  "help": "",
  "url": "",
  "logo": "",
  "dependencies": [],
  "screenshots": [],
  "platform": "1.0.0.0",
  "application": "26.0.0.0",
  "idRanges": [
    {
      "from": 50100,
      "to": 50149
    }
  ],
  "features": [
    "TranslationFile"
  ],
  "runtime": "15.0"
}
```

## Step 2: Create the Enum to Register the App

### 2.1 File `CopilotCapability.Enum.al`

```al
enumextension 50100 "Copilot Capability extensions" extends "Copilot Capability"
{
    value(50100; "ABC Ask Me AnyThing")
    {
        Caption = 'ABC Ask Me AnyThing';
    }
}
```

## Step 3: Create the Prompt Dialog Page

### 3.1 File `OpenAIPromptDialog.Page.al`

```al
page 50100 "OpenAI Prompt Dialog"
{
    PageType = PromptDialog;
    Caption = 'AI Assistant for Customers';
    Extensible = false;
    IsPreview = true;

    PromptMode = Prompt;

    layout
    {
        area(Prompt)
        {
        //TODO
        }

        area(Content)
        {
           //TODO
        }
    }

    actions
    {
        //TODO
    }

    var
        
        //TODO

   
}
```

## Step 4: Extend the Customer Card

### 4.1 File `CustomerCardExt.PageExt.al`

```al
pageextension 50100 "Customer Card AI Ext" extends "Customer Card"
{
    actions
    {
    //TODO
    }
}
```

## Step 5: Compile and Deploy

1. Press `F5` in Visual Studio Code
2. The extension will be compiled and published to your development environment
3. Access Business Central and navigate to a customer card
4. You will see the new "AI Assistant" button

**Use of Azure Key Vault** (recommended for production)

## Applied Best Practices

✅ **Naming Conventions:** Objects with descriptive names and consistent prefixes  
✅ **Object IDs:** Use of the assigned range (50100-50149)  
✅ **Caption and ToolTip:** All fields have descriptions  
✅ **Data Classification:** Fields correctly classified  
✅ **Extensibility:** Use of extensible Enums

## Testing

### Test Cases

1. **Customer Analysis:** Select a customer with complete data and use the "Customer Analysis" guide
2. **Custom Question:** Write a specific question about sales or history
3. **Error Validation:** Test without a configured API Key
4. **Credit Limits:** Use the credit risk guide

## Troubleshooting

| Error | Solution |
|-------|----------|
| "API Key not configured" | Configure the API Key in the `GetOpenAIApiKey()` method |
| "Error parsing response" | Verify the JSON format from OpenAI |
| "Customer not found" | Make sure you open from a valid customer card |

## Additional Resources

- [AL Language Documentation](https://docs.microsoft.com/dynamics365/business-central/dev-itpro/developer/)
- [OpenAI API Documentation](https://platform.openai.com/docs/)
- [BC PromptDialog Pages](https://docs.microsoft.com/dynamics365/business-central/dev-itpro/developer/devenv-page-type-promptdialog)

## License

This project is an educational lab for learning AI integration in Business Central.

---

**Author:** Roberto Corella  
**Date:** April 2026  
**Version:** 1.0.0
