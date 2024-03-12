202311291617
Status: #dev

Tags: 

# db2json23

I have made exe files for Margaret and Sarah - but most don't work. Only CData works/ 
Today I made some changes
I am using py2exe to build the exe files. 

```python
from py2exe import freeze

  

freeze(

    console=['BExpts.py', 'CData.py', 'DKeywords.py', 'FFiles.py', 'Gimages.py','settings.py'],

    windows=[],

    data_files=[],

    zipfile='library.zip',

    options={},

    version_info={}

)




```
- [x] Consider using https://pyinstaller.org/en/stable/usage.html to rebuild the apps for db2json > to https://github.com/Rothamsted-Ecoinformatics/db2json23/issues/1


---
## References
https://pyinstaller.org/en/stable/usage.html