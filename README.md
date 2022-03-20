# AttackCruncher

The Attach Cruncher tool crunches the raw attacker source details into a more understandable rolled-up summary.

## Input 

For input, this tool assumes the source data is in the format written to Azure Table Storage by Azure Diagnostic for Azure Windows Server VMs failed RDP login attemps similar to those written directly into the Windows Event Log. The extracted data includes IP addresses associated with failed RDP login attempts.   

## Output 

The output of this tool is a CSV file. You aim this tool at an Azure Storage account containing Azure Diagnostics logs in the expected format (see Input description above) and it will parse out key fields (e.g., source IP data) and organize and enrich it by providing for each IP address the ISO country codes for its country of registration/origin.   The output is a two-column CSV with the IP address followed by the ISO country code.  

## Side Effects 

As an optional final step, this tool can be configured to upload the generated CSV to a blob container in Azure Storage. This can be handy if you want to make it easy to refer to this CSV file, such as from a Kusto query.
