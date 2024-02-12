# HelloID-Task-SA-Source-ExchangeOnPremises-MailboxSearch

## Prerequisites
- [ ] Execute the cmdlet **Enable-PsRemoting** on the **Exchange server** to which you want to connect.
- [ ] Within **IIS**, under the **Exchange Back End site** for the **Powershell sub-site**, check that the authentication method **Windows Authentication** is **enabled**.
- [ ] Permissions to manage the Exchange objects, the default AD group **Organization Management** should suffice, but please change this accordingly.

## Description

This code snippet executes the following tasks:

1. Define a wildcard search query `$searchValue` based on the search parameter `$datasource.searchValue`
2. Creates a session to Exchange using Remote PowerShell.
3. List all mailboxes in Exchange On-Premises that match the wildcard search query `$searchValue` in their name or email addresses using the cmdlet: [Get-Mailbox](https://learn.microsoft.com/en-us/powershell/module/exchange/get-mailbox?view=exchange-ps)
   > The filter property **-filter** accepts different values [See the Microsoft Docs page](https://learn.microsoft.com/en-us/powershell/module/exchange/get-mailbox?view=exchange-ps#-filter)
4. Return a hash table for each user account using the `Write-Output` cmdlet.

> To view an example of the data source output, please refer to the JSON code pasted below.

```json
{
    "searchValue": "Consultancy"
}
```
