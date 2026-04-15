# Lab-05: Business Central Extension with AI - OpenAI Integration

## Objective

Create an extension for Microsoft Dynamics 365 Business Central that integrates OpenAI from the customer card, using a Prompt Dialog Page with question guides (Prompt Guides).

Fill in the TODOs so we can display the page.

## Prerequisites

- Visual Studio Code installed
- AL Language extension for VS Code
- Business Central Development Environment (Sandbox)
- Basic knowledge of AL Language
- Lab 5 completed

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

## Step 1: Fill in OpenAIIntegration.Codeunit.al

```al
codeunit 81101 "ABC AI Module"
{

    procedure Generate(UserPrompt: Text): Text
    var
        AzureOpenAI: Codeunit "Azure OpenAI";
        AOAIOperationResponse: Codeunit "AOAI Operation Response";
        AOAIChatCompletionParams: Codeunit "AOAI Chat Completion Params";
        AOAIChatMessages: Codeunit "AOAI Chat Messages";

        Result: Text;
    begin
        // Initialize the Azure OpenAI service
        // endpoint: https://your-openai-endpoint
        // apiKey: your-api-key
        // Deployment: gpt-4.1
        SetAuthorization(AzureOpenAI);

        // Set up the chat completion parameters
        // temperature 
        // maxTokens

        SetParameters(AOAIChatCompletionParams);

        // Set the Copilot capability for the Azure OpenAI service
        AzureOpenAI.SetCopilotCapability(Enum::"Copilot Capability"::"ABC Ask Me AnyThing");

        // Set the system meta prompt        
        AOAIChatMessages.SetPrimarySystemMessage(GetSystemMetaPrompt());

        // Add the user message to the chat messages
        AOAIChatMessages.AddUserMessage(GetUserPrompt(UserPrompt));

        // Add the tone option if it is set

        AzureOpenAI.GenerateChatCompletion(AOAIChatMessages, AOAIChatCompletionParams, AOAIOperationResponse);
        if AOAIOperationResponse.IsSuccess() then
            Result := AOAIChatMessages.GetLastMessage()
        else
            Result := AOAIOperationResponse.GetError() + ' - ' +
                 AOAIOperationResponse.GetStatusCode().ToText();
        exit(Result);
    end;



    // Add the parameters for the chat completion request

    local procedure SetParameters(var AOAIChatCompletionParams: Codeunit "AOAI Chat Completion Params")
    begin
        AOAIChatCompletionParams.SetMaxTokens(3500);
        AOAIChatCompletionParams.SetTemperature(0);
    end;


    local procedure GetSystemMetaPrompt(): Text
    var
        MetaPrompt: Text;
    begin
        Metaprompt := 'You are a helpful Business Central Support agent. Please provide only information related to Business Central. ' +
                      'If you do not know the answer, say "I do not know" and do not provide any other information. ' +
                      'Do not include any disclaimers or additional information. ' +
                      'Your responses should be concise and to the point.';
        exit(Metaprompt);
    end;


    local procedure GetUserPrompt(Prompt: Text): Text
    var
        DataTextBuilder: TextBuilder;

    begin
        // generating the prompt for the AI
        DataTextBuilder.AppendLine('You are an expert Business Central Support agent.');
        DataTextBuilder.AppendLine('You can review the information from the website https://learn.microsoft.com/es-es/dynamics365/business-central/');

        DataTextBuilder.AppendLine('This is the user question:');
        DataTextBuilder.AppendLine(Prompt);
        DataTextBuilder.AppendLine('You need to generate a step to step guide to help the user with their question.');

        exit(DataTextBuilder.ToText());
    end;

    local procedure SetAuthorization(var AzureOpenAI: Codeunit "Azure OpenAI")
    var
        Endpoint: Text;
        Deployment: Text;
        Apikey: Text;
    begin
        if not recAISetup.get() then
            Error('You have not configured access');

        Endpoint := recAISetup.EndPoint;
        Deployment := recAISetup.Deployment;
        Apikey := recAISetup."API Key";

        AzureOpenAI.SetAuthorization(Enum::"AOAI Model Type"::"Chat Completions", Endpoint, Deployment, Apikey);
    end;



    var
        recAISetup: Record "ABC AI Setup";
        EndPoint: Text;
        Deployment: Text;
        ApiKey: Text;

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

## Step 3: Update the Prompt Dialog Page

## Step 4: Compile and Deploy

1. Press `F5` in Visual Studio Code
2. The extension will be compiled and published to your development environment
3. Access Business Central and navigate to a customer card
4. You will see the new "AI Assistant" button

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
