# Lab-06: Generating Customers

## Modify the Prompts


Modify the system prompt

```al
Metaprompt := 'You are a helpful Asistant to help to create records in Business Central.' +
                      'If the question is not related to create records, say "I can not do this task.  Only can create records" and do not provide any other information. ' +
                      'Do not include any disclaimers or additional information. ' +
                      'Your responses should be concise and to the point.';

```

Modify the user prompt

```al
local procedure GetUserPrompt(Prompt: Text): Text
    var
        DataTextBuilder: TextBuilder;

    begin
        // generating the prompt for the AI
        DataTextBuilder.AppendLine('You are an expert Business Central Support agent.');
        DataTextBuilder.AppendLine('You are going to help the user to create demo customers in Business Central.');

        DataTextBuilder.AppendLine('According with the user help:');
        DataTextBuilder.AppendLine(Prompt);
        DataTextBuilder.AppendLine('You will generate a number demo customers for Business Central.');
        DataTextBuilder.AppendLine('You will generate the customers with the following characteristics:');
        DataTextBuilder.AppendLine('1. We will have a Customer Name');
        DataTextBuilder.AppendLine('2. We will have an invented Address, with Address, number, city, post code and country');
        DataTextBuilder.AppendLine('3. We will have a Phone number');
        DataTextBuilder.AppendLine('The maximum number of customers to create is 10.');
        DataTextBuilder.AppendLine('You will generate the customers with the following characteristics:');
        DataTextBuilder.AppendLine('Name (in bold format): Customer Name');
        DataTextBuilder.AppendLine('Address: Address, number, city, post code and country');
        DataTextBuilder.AppendLine('Phone: Phone number');
        DataTextBuilder.AppendLine('Example: Customer Name: John Doe' +
                                  'Address: 123 Main St, Springfield, 12345, USA' +
                                  'Phone: +1 (555) 123-4567');
        DataTextBuilder.AppendLine('You will generate the customers based on the user request, such as "Create 10 Customers from Spain"');
        exit(DataTextBuilder.ToText());
    end;
```
