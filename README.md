# csv-to-e-invoice
Simple bashskript to create an e-invoice with one item from two csv-files

The bashskript bin/crt-serial-letter-from-csv creates an e-invoice
in two steps:
- Create an invoice-pattern for the company
  bin/crt-serial-letter-from-csv example/ data/e-invoice-pattern.xml data/company.csv 
  example creates the invoice-pattern H12345 for this company in example/files
- Create an invoice from data invoice.csv for the company H12345
  bin/crt-serial-letter-from-csv example/ data/H12345 data/invoice.csv
  example creates the invoice R2025001 in example/files 

The e-invoice-pattern is created with the help of chatgpt.
I used to check my created invoices with chatgpt.

Note: The skript creates a copy of the used csv-files in the *outputfolder* with praefix *new* using the process-id.
If an old subfolder *files* exists in *outputfolder* it will be moved to the subfolder with name *process-id*. 
