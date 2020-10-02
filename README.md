Built on the [lsFusion] platform (https://github.com/lsfusion/platform).

# Capabilities

* Keeping clients, organizations, as well as contact persons for them.
* Support for multiple proprietary companies.
* Work with contracts, agreements and acts.
* Ability to generate documents based on templates (Word) and templates.
* Input / import of customer payments and own payments from the accounting circuit.
* Control of working hours of employees. Support for vacations, sick days, time off. Import from Redmine.
* Support for different currencies.
* Support for employee expenses. Calculation of profit for clients.
* Registration of events by clients.

# Demo

A demo with a complete test database can be found at https://demo.lsfusion.org/crm.

The example introduces users with different roles and available forms.

Available logins:
* admin - Administrator (full access to all functions)
* owner - Founder
* manager - Manager
* accountant - Accountant
* employee - Employee

Passwords match logins.

You can change roles and their rights under the administrator on the Administration / Security policy form.

Data entered mainly for 2018. In all forms, it is best to choose the appropriate period.

# Installation

* Install lsFusion on the server as described in the following instructions: https://documentation.lsfusion.org/pages/viewpage.action?pageId=57738078.
* In the / var / lib / lsfusion folder, run git pull.
* In the file /etc/lsfusion2-server/lsfusion.conf add the following path to the value of the CLASSPATH parameter - / var / lib / lsfusion / crm / src / main / resources (preceded by a colon).
* Restart the lsFusion server (as in the first instruction).

# Short description

The main working forms are located on the Desktop tab. Each of them is designed to carry out a specific process (s).

## Working with clients

The form is designed for easy display and editing of all information for one client.

## Working with contracts

Shows a list of all active contracts with the ability to edit them and view all the detailed information associated with contracts.

## Dealing with debts

### Debt Control

Displays a list of liabilities for all customer agreements. There is an automatic calculation of the amount of payment for each debt, taking into account the binding to contracts / agreements / acts according to the FIFO principle. On the form, you can put an act on one or several debts within the framework of one contract.

### Payment plan

Shows monthly debts (future and current) in the context of contract types, as well as payments made.

## Results of work

### Profit by customer

Calculates income, expenses and profit in foreign currency for the selected interval. Income is calculated as all payments at the exchange rate on the date of payment. Expenses are calculated based on the marked time of employees by customers based on the amounts specified in the Expenses by employees form. Also, the marked time for projects without a client (internal projects) can be "signed" for all clients in proportion to income relative to groups of contracts.

### Profit by month

Consolidates income and expenses by month in currency in one form. Subtotal breakdown by types and groups of contracts.

### Manager report

Outputs to Excel file a list of all payments for customers tied to a specific employee with a specified role (for example, the Manager role).

## Work with documents

### Payment processing

It is used to import customer payments and outgoing payments from the accounting system with subsequent processing. As a rule, in the process of processing payments are linked to contracts, agreements and acts.

### Document processing

Shows a list of all working documents (contracts, agreements, acts) in the system in a single table. Designed to work with incoming and outgoing correspondence. In this form, you can mark the dates and methods of sending documents, close the processed ones.

### Results by acts

Displays the amount of issued acts by month in the context of organizations. Used by accountants to check the correctness of the issued acts.

## Work time

### Timesheet

Designed for employees to mark the time spent on specific clients, as well as to register vacations, sick leave and other reasons for being in the workplace. If you are automatically importing from an external timestamp system (eg Redmine), then the imported timestamps are also displayed on the form.

### Control of marked time

Shows in the form of a table the marked time and absence of each employee for a certain month. It is necessary for the manager to control the correctness of filling out the timesheet by employees.

### Billing

In this form, you can generate an Excel file for each client for a specified interval with a list of all labor costs. It is also possible to link tasks to specific contracts and agreements.

## Other

### Event handling

On this form, users can register events (calls, negotiations, presentations, etc.) related to certain clients. It also allows you to track the time of the need for the next contact with the client, if it was marked earlier, through the selection of the Last by client.

### My tasks

It is intended for creating tasks by other employees and changing the tasks assigned to the current user. Only tasks not imported from external systems are shown (for example, Redmine)

