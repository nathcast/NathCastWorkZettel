202312131214
Status: #project 
Tags: 

# downloadRIS

## Issue - introduction

Users of the web site, when citing a datasets, sometime do not cite it properly: 
We need to provide a proper RIS file that people can import in their citation software and from there, the software will generate appropriate citations. 
The simple copy paste is not really a solution - although that would be a start. 

## Ideas: 
### pre-generated

we could have the specific formats of the RIS, and other references ready made by the db2json23 and saved in each dataset folders. 
When updating the json using db2json, the application could create for each dataset a few files with the relevant formats for the library. 
Then, all we need is a link on the page to the relevant download snippet. 
This is the easiest for me. 

### on the fly
A few buttons that would generate on the fly, the correct citation file and save as a temp file, to be downloaded. 

## todo: 
- [x] find reference formats
- [x] find out relevant fields and their translations in the citation format
- [x] program it in db2json23 
	- [x] class reference, format as each of them, export in individual files. 
- [x] make links in the website - filename for  the text is 01-shortname.ris in the relevant folder


## citation software formats

![[Pasted image 20231213151708.png]]

#### Bibtex - not doing that
https://en.wikipedia.org/wiki/BibTeX  .bib
```Bib
@article{ refId0,

    author = {{Frost, A. J.} and {Bodensteiner, J.} and {Rivinius, Th.} and {Baade, D.} and {Merand, A.} and {Selman, F.} and {Abdul-Masih, M.} and {Banyard, G.} and {Bordier, E.} and {Dsilva, K.} and {Hawcroft, C.} and {Mahy, L.} and {Reggiani, M.} and {Shenar, T.} and {Cabezas, M.} and {Hadrava, P.} and {Heida, M.} and {Klement, R.} and {Sana, H.}},

    title = {HR 6819 is a binary system with no black hole - Revisiting the source with infrared interferometry and optical integral field spectroscopy⋆

},

    DOI= "10.1051/0004-6361/202143004",

    url= "https://doi.org/10.1051/0004-6361/202143004",

    journal = {A&A},

    year = 2022,

    volume = 659,

    pages = "L3",

}
```

#### Reference Manager: ris
**RIS** is a standardized tag format developed by Research Information Systems, Incorporated (the format name refers to the company) to enable citation programs to exchange data.[[1]](https://en.wikipedia.org/wiki/RIS_(file_format)#cite_note-1) It is supported by a number of [reference managers](https://en.wikipedia.org/wiki/Reference_management_software "Reference management software"). Many [digital libraries](https://en.wikipedia.org/wiki/Digital_libraries "Digital libraries"), like [IEEE Xplore](https://en.wikipedia.org/wiki/IEEE_Xplore "IEEE Xplore"), [Scopus](https://en.wikipedia.org/wiki/Scopus "Scopus"), the [ACM Portal](https://en.wikipedia.org/wiki/ACM_Portal "ACM Portal"), [Scopemed](https://en.wikipedia.org/w/index.php?title=Scopemed&action=edit&redlink=1 "Scopemed (page does not exist)"), [ScienceDirect](https://en.wikipedia.org/wiki/ScienceDirect "ScienceDirect"), [SpringerLink](https://en.wikipedia.org/wiki/Springer_Science%2BBusiness_Media "Springer Science+Business Media"), [Rayyan](https://en.wikipedia.org/wiki/Rayyan "Rayyan"), [Accordance](https://en.wikipedia.org/wiki/Accordance "Accordance") Bible Software,[[2]](https://en.wikipedia.org/wiki/RIS_(file_format)#cite_note-2) and online library catalogs can export citations in this format. Citation management applications can export and import citations in this format.


RIS: https://en.wikipedia.org/wiki/RIS_(file_format)  .ris
```RIS

TY  - DATA
AU  - Kimori, June
AU  - Philcox, Daniel
AU  - Glendining, M.J.
PY  - 2022
TI  - Exhaustion Land Experiment annual crop yields 1940-1975
CL  - specific resource type
PP  - Electronic Rothamsted Archive, Rothamsted Research, Harpenden, UK
ID  - 10.23637/REX4-YLD4075-01
DOI  - 10.23637/REX4-YLD4075-01
DI  - 10.23637/REX4-YLD4075-01 
DO  - 10.23637/REX4-YLD4075-01
M3  - 10.23637/REX4-YLD4075-01
UR  - https://doi.org/10.23637/REX4-YLD4075-01
KW  - Exhaustion land
KW  - KeyRefEX
AB  - This dataset contains annual spring barley yield data for all plots of the Exhaustion Land Experiment, 1949-1975, and agronomic details including sowing dates and varieties. No yields were recorded 1940-1948. Basal nitrogen fertilizer was applied to all plots 1940-1974; no other fertilizer or manure was applied. This phase of the experiment tests the residual effects of different fertilizers and manures applied 1856-1901.
ER  - 
```

This is the proposed correspondence 
```RIS

TY  - DATA
PP  - publisher_id > organisation.name
T1  - publisher_id > organisation.name
PY  - publication_year
CL  - specific_resource_type_id
M3  - document_format_id
C5  - document_format_id
VL  - version
LA  - lang
UR  - https://doi.org/+ identifier
DOI  - identifier
DO  - identifier
DI  - identifier
ID  - identifier
TI  - title
AU  - author, first
AU  - author, first
AU  - author, first
KW  - Keyword
KW  - Keyword - remove KeyRef
AB  - description_abstract
ER  - 
```

This is the correspondence RIS - Endnote (import filter for endnote) for a Dataset
```RIS
TY  -	`DATA`
A2  -	Producer
A4  - 	Funding Agency
AB  - 	Abstract
AD  -	Author Address
AN  -	Accession Number
AU  -	Investigators
C1  - 	Time Period
C2  - 	Unit of Observation
C3  - 	Data Type
C4  - 	Dataset(s)
CA  -	Caption
CN  - 	Call Number
CY  -	Place Published
DA  - 	Date of Collection
DB  - 	Name of Database
DO  -	DOI
DP  - 	Database Provider
ET  - 	Version
JF  - 	Notes
J2  -	Abbreviation
KW  -	Keywords
L1  -	File Attachments
L4  -	Figure
LA  - 	Language
LB  - 	Label
N1  -	Notes
NV  - 	Study Number
OP  - 	Version History
PB  -	Distributor
PY  -	Year
RI  - 	Geographic Coverage
RN  - 	Research Notes
SE  - 	Original Release Date
SN  -	ISSN
ST  - 	Short Title
T3  -	Series Title
TA  - 	Translated Author
TI  -	Title
TT  - 	Translated Title
UR  -	URL
Y1  - 	Year/Date of Collection
Y2  -	Access Date
ER  -	{IGNORE}
-----	Special EBSCO Tag
L3  -	DOI
-----	Special CABDirect2 tags
OI	DOI
```

#### endnote 
https://www1.citavi.com/sub/manual3/en/index.html?importing_enw.htm 

```ENW 
--- exported from EN ---
%0 Dataset
%A Kimori, June
%A Philcox, Daniel
%A Glendining, M.J.
%D 2022
%T Exhaustion Land Experiment annual crop yields 1940-1975
%C Electronic Rothamsted Archive, Rothamsted Research, Harpenden, UK
%! Exhaustion Land Experiment annual crop yields 1940-1975
%R 10.23637/REX4-YLD4075-01
%K Exhaustion land; KeyRefEX
%X This dataset contains annual spring barley yield data for all plots of the Exhaustion Land Experiment, 1949-1975, and agronomic details including sowing dates and varieties. No yields were recorded 1940-1948. Basal nitrogen fertilizer was applied to all plots 1940-1974; no other fertilizer or manure was applied. This phase of the experiment tests the residual effects of different fertilizers and manures applied 1856-1901.

```

| Field Code | EndNote Field Name |
| ---- | ---- |
| %A | Author |
| %B | Secondary Title (of a Book or Conference Name) |
| %C | Place Published |
| %D | Year |
| %E | Editor /Secondary Author |
| %F | Label |
| %G | Language |
| %H | Translated Author |
| %I | Publisher |
| %J | Secondary Title (Journal Name) |
| %K | Keywords |
| %L | Call Number |
| %M | Accession Number |
| %N | Number (Issue) |
| %P | Pages |
| %Q | Translated Title |
| %R | Electronic Resource Number |
| %S | Tertiary Title |
| %T | Title |
| %U | URL |
| %V | Volume |
| %W | Database Provider |
| %X | Abstract |
| %Y | Tertiary Author |
| %Z | Notes |
| %0 | Reference Type |
| %1 | Custom 1 |
| %2 | Custom 2 |
| %3 | Custom 3 |
| %4 | Custom 4 |
| %6 | Number of Volumes |
| %7 | Edition |
| %8 | Date |
| %9 | Type of Work |
| %? | Subsidiary Author |
| %@ | ISBN/ISSN |
| %! | Short Title |
| %# | Custom 5 |
| %$ | Custom 6 |
| %] | Custom 7 |
| %& | Section |
| %( | Original Publication |
| %) | Reprint Edition |
| %* | Reviewed Item |
| %+ | Author Address |
| %^ | Caption |
| %> | Link to PDF |
| %< | Research Notes |
| %[ | Access Date |
| %= | Last Modified Date |
| %~ | Name of Database |

```ENW

--- imported by my code ---
%0 Dataset
%T Broadbalk Wheat Chalk Applications 
%I Electronic Rothamsted Archive, Rothamsted Research 
%W e-RA - the electronic Rothamsted Archive 
%D 2022 
%C Rothamsted Research, Harpenden, Herts, AL5 2JQ, UK. 
%9 xlsx 
%7 1.0 
%G en 
%U https://doi.org/10.23637/rbk1-chalk-01 
%R 10.23637/rbk1-chalk-01 
%A Glendining, Margaret 
%A Poulton, Paul 
%A Gregory, Andy 
%K wheat; Rothamsted Research; Broadbalk long-term experiment; arable soils; liming; 
%X Details of the routine chalk (lime) applications to the Broadbalk Wheat Experiment, first applied in 1955. A regular scheme was introduced in 1956 and revised in 1976. The aim was to maintain soil pH above 7.5 and minimize the range of pH values within each Section. No chalk was required 1993-2007. As in earlier years, differential chalk applications were made to selected plots in 2008, 2014 and 2019, the amount applied depending on the soil pH. 

```



#### text file  - we are not doing that - or we put that in a copy - paste 
```txt

HR 6819 is a binary system with no black hole - Revisiting the source with infrared interferometry and optical integral field spectroscopy
A. J.  Frost, J.  Bodensteiner, Th.  Rivinius, D.  Baade, A.  Merand, F.  Selman, M.  Abdul-Masih, G.  Banyard, E.  Bordier, K.  Dsilva, C.  Hawcroft, L.  Mahy, M.  Reggiani, T.  Shenar, M.  Cabezas, P.  Hadrava, M.  Heida, R.  Klement, H.  Sana
A&A 659 L3 (2022)
DOI: 10.1051/0004-6361/202143004

```

I will take the reference out of fields in the metadata document - not eraPapers! 

### coding

in db2json23:  metadata 
this will show the codes used and the fields corresponding. 

```python

def prepRIS(documentInfo):

    data = documentInfo.data

    # horizontal line is ---

    newline = '\n'

    readme = f''

    readme += f"TY  - DATA  "

    readme += newline

    readme += f"TI  - {data['name']} "

    readme += newline

    readme += f"CY  - {data['publisher']['name']} "

    readme += newline

    readme += f"DB  - e-RA - the electronic Rothamsted Archive "

    readme += newline

    readme += f"PY  - {data['publication_year']} "

    readme += newline

    readme += f"DP  - Rothamsted Research, Harpenden, Herts, AL5 2JQ, UK. "    

    readme += newline

    readme += f"M3  - {data['encodingFormat']} "

    readme += newline

    readme += f"ET  - {data['version']} "

    readme += newline

    readme += f"LA  - {data['inLanguage']} "

    readme += newline

    readme += f"UR  - https://doi.org/{data['identifier']} "

    readme += newline

    readme += f"DO  - {data['identifier']} "

    authorPerson = ''

    authorOrg = ''  

    for item in data['creator']:

        if item['type'].lower() == 'person':

            authorPerson += newline

            authorPerson += f"AU  - {item['familyName']}, {item['givenName']} "        

        if item['type'].lower() == 'organization':

            authorOrg += newline

            authorOrg += f"AU  - {item['name']}, "      

    if  authorPerson == '':

        readme += authorOrg

    else:

        readme += authorPerson  

    readme += newline

    readme += f"KW  - "

    for item in data['keywords'] :

        if 'KeyRef' not in item:

            readme += f"{item}, "

    for item in data['description'] :

        if item['descriptionType'] == 'Abstract':

            readme += newline

            readme += f"AB  - {item['description']} "

    readme += newline        

    readme += f"ER  -  "

    return readme

  
  

def prepENW(documentInfo):

    data = documentInfo.data

    # horizontal line is ---

    newline = '\n'

    readme = f''

    readme += f"%0 Dataset"

    readme += newline

    readme += f"%T {data['name']} "

    readme += newline

    readme += f"%I {data['publisher']['name']} "

    readme += newline

    readme += f"%W e-RA - the electronic Rothamsted Archive "

    readme += newline

    readme += f"%D {data['publication_year']} "

    readme += newline

    readme += f"%C Rothamsted Research, Harpenden, Herts, AL5 2JQ, UK. "    

    readme += newline

    readme += f"%9 {data['encodingFormat']} "

    readme += newline

    readme += f"%7 {data['version']} "

    readme += newline

    readme += f"%G {data['inLanguage']} "

    readme += newline

    readme += f"%U https://doi.org/{data['identifier']} "

    readme += newline

    readme += f"%R {data['identifier']} "

    authorPerson = ''

    authorOrg = ''  

    for item in data['creator']:

        if item['type'].lower() == 'person':

            authorPerson += newline

            authorPerson += f"%A {item['familyName']}, {item['givenName']} "        

        if item['type'].lower() == 'organization':

            authorOrg += newline

            authorOrg += f"%A {item['name']}, "      

    if  authorPerson == '':

        readme += authorOrg

    else:

        readme += authorPerson  

    readme += newline

    readme += f"%K "

    for item in data['keywords'] :

        if 'KeyRef' not in item:

            readme += f"{item}; "

    for item in data['description'] :

        if item['descriptionType'] == 'Abstract':

            readme += newline

            readme += f"%X {item['description']} "

    readme += newline        

    return readme
   
```
I am doing it in RIS. Then will ask others if it is worth also doing the other formats. 

Bib text is a json sort of format 
ENW is a one line per info preceded by a code and a space 

![[Pasted image 20240104154844.png]]

![[Pasted image 20240111114213.png]]

---
## References

Lab Notebook
https://uk-mynotebook.labarchives.com/share/Nathalie%2520Castells%2520Notebook1%2520-%25201%2520for%2520all/NTMuMzAwMDAwMDAwMDAwMDA0fDIwNjY2LzQxL1RyZWVOb2RlLzE1NDE1MzE5Mzl8MTM1LjI5OTk5OTk5OTk5OTk4 

