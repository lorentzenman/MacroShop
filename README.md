# MacroShop
Collection of scripts to aid in delivering payloads via Office Macros.  Most are python. See http://khr0x40sh.wordpress.com for details.

1. macro_safe.py

   Generates safe for VB inclusion into an excel spreadsheet.  Requires a batch file generated by Veil-Evasion powershell payloads. To include, enable the developer menu in Office, head to Visual Basic tab, double click on This_Workbook and paste the contents of the output file. Syntax is:
python macro_safe.py test.bat test.txt

2. exeinvba.py

   Generates VB code for including and unpacking a portable executable onto a file system for delivery via Office Macro.  To include, enable the developer menu in Office, head to Visual Basic tab, double click on This_Workbook and paste the contents of the output file.  Requires a PE. Syntax is:
python exeinvba.py --exe test.exe --out test.vb [--dest "C:\\Users\\Public\\Documents\\test.exe"]
Ensure any backslashes are escaped in the dest variable

3. macro_safe_old.py

   Same as macro_safe.py, just uses powershell vice VB for architecture detection to call the correct version of powershell.

4. b64_enc.py

   Watered down version of exeinvba.py that will output both the raw base64 string of the executable and the variable specific section of the VB.  May be useful for use with different VB templates or other methods that may require an executable passed as a base64 string somewhere.  Automatically stores output into base64_output.txt (raw) and base64_output.vb. Syntax is:
python b64_enc.py test.exe
