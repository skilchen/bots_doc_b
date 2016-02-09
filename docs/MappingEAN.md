## EAN/UCC checkdigits

Synonyms: GTIN, ILN, GLN, UPC, EAN, UAC, JAN

Can be used for UPC-A, UPC-E, EAN8, EAN13, ITF-14, SSCC/EAN-128 etc.  
These numbers end with a check-digit.


### transform.checkean(EAN\_number)

Returns True is if check-digit is OK, False if not.  
When not a string with digits, raises botslib.EanError

     transform.checkean('8712345678906') 
     #returns 'True' for this EAN number.


### transform.addeancheckdigit(EAN\_number)

Returns EAN number including check digit (adds checkdigit).

      transform.addeancheckdigit('871234567890') 
      #returns '8712345678906' for EAN number '871234567890'.


### transform.calceancheckdigit(EAN\_number)

Returns the checkdigit-string for a number without check-digit.\

     transform.calceancheckdigit('871234567890') 
     #returns '6' for EAN number '871234567890'.
