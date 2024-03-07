# KQL Queries 💻

This repository contains a collection of KQL (Kusto Query Language) queries for data analysis and exploration.

## Table of Contents

- [Introduction](#introduction)
- [Getting Started](#getting-started)
- [Examples](#examples)

## Introduction 👋🏼

KQL is a powerful query language used in Azure Data Explorer (ADX), Azure Resource Graph Explorer, and Azure Monitor to analyze large volumes of data. It provides a rich set of operators and functions for querying and manipulating data.

## Getting Started 🚀

To get started with KQL queries, follow these steps:

1. Install Azure Data Explorer or Azure Monitor. (Optional)
    + You can use Azure Resource Graph Explorer to run KQL queries without installing any software.
2. Open the query editor or command line interface.
3. Write your KQL query using the appropriate syntax.
4. Execute the query and analyze the results.

## Examples 💡

Here are some examples of common KQL queries:

1. **List all resources in a subscription:**
    ```kql
    Resources
    | project name, type, location
    ```
2. **List all virtual machines in a subscription:**
    ```
    Resources
    | where type == "microsoft.compute/virtualmachines"
    | project name, location
    ```
3. **List all failed login attempts in the last 24 hours:**
    ```kql
    SecurityEvent
    | where TimeGenerated > ago(24h)
    | where EventID == 4625
    | project TimeGenerated, Computer, Account, IPAddress
    ```
