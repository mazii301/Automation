# Employee Onboarding Feedback Automation
This project is an automated workflow built in Microsoft Power Automate. 
Its purpose is to collect employee onboarding feedback, notify user on Microsoft Teams, and store responses in a structured SharePoint Excel file.

The survey itself is in Polish:
“Twoja opinia o miejscu pracy”
///
Project Overview
The automation triggers whenever a new employee submits the onboarding survey “Twoja opinia o miejscu pracy”.

**The workflow performs two core actions:**

1️. Send a Teams notification to the employee / HR bot

A Microsoft Teams bot sends a message containing:

- information that a new survey was submitted

- full survey results (all answers)

This ensures instant visibility for the user.

2️. Append a new row to the SharePoint Excel file

The Excel file “Feedback pracowniczy.xlsx”, stored on SharePoint, is automatically updated.
A new row is added with:

submission timestamp

employee email (if provided)

all answers from the questionnaire

This allows the team to continuously build a database of onboarding feedback.

**Survey Details (Polish)**

Survey name: Twoja opinia o miejscu pracy
Purpose: Poznanie pierwszych wrażeń pracownika oraz jego oceny procesu onboardingu.

Questions included:

Jak oceniasz swoje pierwsze wrażenia z pracy w naszej firmie?

Czy czujesz się dobrze poinformowany o swoich obowiązkach?

Nie

Raczej nie

Raczej tak

Tak

Na ile jesteś zadowolony z atmosfery w zespole?

Czy uważasz, że Twoja praca jest zgodna z Twoimi oczekiwaniami?

Nie

Raczej nie

Raczej tak

Tak

Co najbardziej podoba Ci się w pracy tutaj, a co chciałbyś zmienić?


**Workflow Architecture**

Trigger

“When a new response is submitted” (Forms)

“Get response details”

Parallel Branches
Execution Branch

Add a new row to Excel (SharePoint)

File: Feedback pracowniczy.xlsx

Table: Table1

Columns filled with dynamic response values

Operational Branch

Get user profile (V2) – optional, used to identify sender

Post a message in a chat or channel (Teams)
Includes:

survey title

submission information

each answer formatted in a readable layout

**Technologies Used**

Microsoft Power Automate

Microsoft Forms

Microsoft Teams

SharePoint (Excel Online)
