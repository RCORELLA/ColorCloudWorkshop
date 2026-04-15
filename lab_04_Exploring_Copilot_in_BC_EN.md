# Lab 04 - Copilot Use Cases in Business Central

## Objective
In this lab you will explore the different Copilot functionalities natively integrated into Business Central. You will learn how to use data analysis, conversational chat, configuration generation, and task automation through natural language prompts.

## Prerequisites

- ✅ Access to Business Central with Copilot enabled
- ✅ Demo data or real data in the system
- ✅ Basic familiarity with Business Central navigation

## Use Case 1: View Analysis with Copilot

Copilot can help you create custom data analyses directly from Business Central lists.

### Exercise 1.1: Product Output Analysis

**Objective:** Visualize product outputs grouped by month and product.

**Steps:**
1. Go to the **Item Ledger Entries** page
2. Click the **Analyze** button in the ribbon
3. Enable **Copilot** in the analysis panel
4. Enter the following prompt:
```
Show product outputs by month grouped by product
```

**Expected result:**
- A table showing products in rows
- Months in columns
- Output quantities as values

### Exercise 1.2: Customer Analysis by Country

**Objective:** Get a grouped view of customers by geographic location.

**Steps:**
1. Go to the **Customers** page
2. Click **Analyze**
3. Enable **Copilot**
4. Enter the following prompt:
```
Show customers grouped by country, using the customer master data
```

**Expected result:**
- Customers grouped by country
- Customer count per region
- Option to view additional information such as total balance per country

## Use Case 2: Conversational Chat with Copilot

The Copilot chat allows you to run natural language queries against your company's data.

### Exercise 2.1: Query Invoices for a Specific Customer

**Steps:**
1. Open the **Copilot Chat** from any page (Copilot icon in the top corner)
2. Enter the following prompt:
```
Could you give me last 3 invoices from Adatum Corporation?
```

**Expected result:**
- List of the last 3 invoices for Adatum Corporation
- Relevant information: invoice number, date, amount
- Direct links to invoices for quick access

### Exercise 2.2: Filter Customers by Balance

**Steps:**
1. In the **Copilot Chat**, enter the following prompt:
```
Can you show me customers with a balance greater than 500?
```

**Expected result:**
- Filtered list of customers with balance > 500
- Current balance information for each customer
- Option to open the customer card directly

> 💡 **Tip:** Copilot understands both English and Spanish. You can switch between languages based on your preference.

## Use Case 3: Configuration Generation

Copilot can help you create complex configurations through simple instructions.

### Exercise 3.1: Create Number Series for Sales Orders

**Objective:** Automatically generate a numbering configuration for sales documents.

**Steps:**
1. Go to the **No. Series** page
2. Enable **Copilot** (if available on the page) or use the chat
3. Enter the following prompt:
```
Create number series for sales orders
```

**Expected result:**
- Copilot suggests a new number series
- Proposes a code (e.g., SO-ORD)
- Defines logical numbering ranges
- Configures automatic increments

**Actions:**
- Review Copilot's proposal
- Adjust if necessary
- Accept and save the configuration

## Use Case 4: Document Automation

One of the most powerful features: automatically replicating previous documents.

### Exercise 4.1: Repeat a Previous Order

**Objective:** Create a new sales order based on one from last month.

**Steps:**
1. Open a new **Sales Order**
2. In the customer field, select the desired customer
3. Enable **Copilot** on the document (button in the ribbon)
4. Enter the following prompt:
```
Repeat the same order as last month
```

**Expected result:**
- Copilot searches for previous orders from the customer
- Identifies last month's order
- Copies the order lines automatically
- Adjusts dates to the current context

**Next actions:**
- Review the copied lines
- Modify quantities or products if necessary
- Confirm and process the order

> ⚠️ **Important:** Always verify that copied data is correct before processing documents.

## Best Practices

### For Data Analysis
- ✅ Be specific about the groupings you want
- ✅ Mention the time period if relevant

### For Conversational Chat
- ✅ Use complete and clear sentences
- ✅ Specify exact customer or product names
- ✅ Include concrete numeric criteria (e.g., "greater than 500")

### For Automation
- ✅ Always verify automatically generated data
- ✅ Adjust configurations to your specific needs

## Additional Use Cases to Explore

Once you master the previous exercises, try these prompts:

**Analysis:**
- "Show sales by salesperson for the last quarter"
- "Group products by category and show current stock"

**Chat:**
- "What are the 5 best-selling products this month?"
- "Show me pending orders to be fulfilled"

**Automation:**
- "Create a quote based on this customer's last quote"
- "Generate number series for purchase delivery notes"

## Troubleshooting

| Problem | Solution |
|---------|----------|
| Copilot doesn't appear | Verify that your license includes Copilot and it is enabled in the settings |
| Inaccurate responses | Rephrase the prompt to be more specific |
| Can't find historical data | Make sure data exists for the mentioned period |
| Error creating configurations | Verify that you have administrator permissions |

## Additional Resources

- [Official Copilot in Business Central documentation](https://learn.microsoft.com/dynamics365/business-central/copilot-overview)
- [Workshop repository](https://github.com/RCORELLA/AprendeBusinessCentralWorkshopsPublic)

## Conclusion

Congratulations! You have explored the main Copilot functionalities in Business Central. This tool can significantly boost your productivity by:
- Simplifying complex data analyses
- Answering questions in natural language
- Automating repetitive tasks
- Accelerating system configurations

---

**Next step:** Experiment with your own prompts and discover new ways to leverage Copilot in your daily work with Business Central.

---

*Instructor: Roberto Corella*  
*LinkedIn: https://www.linkedin.com/in/robertocorella/*  
*Date: October 2025*
