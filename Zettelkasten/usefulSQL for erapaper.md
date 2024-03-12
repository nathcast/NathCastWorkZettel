202401171126
Status: #idea
Tags: 

# usefulSQL for erapaper

``` sql

-- eradoc.`eraPapers-today` definition

  

CREATE TABLE `eraPapers-today` (

`PaperID` int(11) NOT NULL AUTO_INCREMENT,

`RefType` tinytext,

`Authors` text,

`Year` int(11) DEFAULT '0',

`Title` text,

`Journal` text,

`Volume` text,

`Issue` text,

`Pages` text,

`Date` text,

`Keywords` text,

`Comment` text,

`DOI` tinytext,

`GRID` tinytext,

`URL` mediumtext,

PRIMARY KEY (`PaperID`),

FULLTEXT KEY `Authors` (`Authors`,`Title`,`Journal`),

FULLTEXT KEY `Keywords` (`Keywords`),

FULLTEXT KEY `DOI` (`DOI`),

FULLTEXT KEY `URL` (`URL`)

) ENGINE=MyISAM AUTO_INCREMENT=2737 DEFAULT CHARSET=latin1 COMMENT='List papers imported from Endnote';

  

-- find and remove GRID

select * from eraPapers-today ep where GRID like '%GRID%'

  

UPDATE eradoc.eraPapers-today SET GRID='' WHERE GRID like 'GRID';

  

-- up the previous one : remember to adjust name

RENAME TABLE eradoc.eraPapers TO eradoc.`z-2024-01-16-eraPapers`;

  

-- rename the new one

RENAME TABLE eradoc.`eraPapers-today` TO eradoc.eraPapers;

  

-- these papers have NO link to the actual article

select * from eraPapers ep where DOI like '' and URL like '' and GRID like '' and RefType like 'Journal Article' order by year DESC

  

select DISTINCT RefType from eraPapers ep order by RefType ASC

-- find duplicate

select title, year, Journal, volume, Pages, count(*) from `eraPapers` ep group by title, year , Journal, volume, Pages having count(*)>1

  

-- compare 2 table IDs

SELECT ept.PaperID, ept.title, ept.Year

FROM `eraPapers-today` ept

WHERE title NOT IN

(

SELECT title

FROM eraPapers ep

);

SELECT ep.PaperID, ep.title, ep.Year

FROM `eraPapers` ep

WHERE title NOT IN

(

SELECT title

FROM `eraPapers-today` ept2

);

-- find duplicate

select title, year, Journal, volume, Pages, count(*) from `eraPapers` ep group by title, year , Journal, volume, Pages having count(*)>1

  

  

select * from Rs left join RaDOIs rd on rd.RUID = Rs.RUID where Rs.GRID like "%ResReport1964-226-230%";

  

SELECT Rs.`GRID`, Rs.RTitle, Books.`Year` FROM `Rs`left join RaDOIs on RaDOIs.GRID = Rs.GRID join Books on Books.BookID = Rs.BID WHERE `needsDOI`= 1 and RaDOIs.GRID is Null and isLatest = 1 and Books.isLive = 1 order by Rs.`GRID` ASC
```

---
## References
