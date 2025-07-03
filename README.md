# csv-to-e-invoice
Simple bashskript to create an e-invoice with one item from two csv-files

The bashskript bin/crt-serial-letter-from-csv creates an e-invoice
in two steps:
- Create an invoice-pattern for the company<br>
  bin/crt-serial-letter-from-csv example/ data/e-invoice-pattern.xml data/company.csv <br>
  example creates the invoice-pattern H12345 for this company in example/files
- Create an invoice from data invoice.csv for the company H12345 <br>
  bin/crt-serial-letter-from-csv example/ data/H12345 data/invoice.csv <br>
  example creates the invoice R2025001 in example/files 

The e-invoice-pattern is created with the help of chatgpt.
I used to check my created invoices with:
https://erechnungsvalidator.service-bw.de/

Note: The skript creates a copy of the used csv-files in the *outputfolder* with praefix *new* using the process-id.
If an old subfolder *files* exists in *outputfolder* it will be moved to the subfolder with name *process-id*. 

How to use:
 1. Fill data/company.csv with your company data
 2. Fill data/invoice.csv with one or more invoice data 
 3. bin/crt-serial-letter-from-csv myinvoices/ data/e-invoice-pattern.xml data/company.csv  <br>
    asuming your company ID is MyCompanyID
 4. cp myinvoices/files/MyCompanyID myinvoices/files
 5. bin/crt-serial-letter-from-csv myinvoices/ myinvoices/MyCompanyID data/invoice.csv
 6. find your invoices in myinvoices/files
 7. check whether your invoices are correct. I do it with the link above.

Note: If you want to change the column headers in data/invoice.csv or data/company.csv
you have to change the pattern in data/e-invoice-pattern.xml too.
