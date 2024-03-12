202401171036
Status: #idea
Tags: 

see also [[usefulSQL for erapaper]] 
# ENDNOTE compare Tables

in erapapers-today is the endnote from PC9074 
in erapapers is the biblio from teh usual one. 

```SQL 

SELECT ept.PaperID, ept.title, ept.Year
FROM `eraPapers-today` ept
WHERE PaperID NOT IN
(
SELECT PaperID
FROM eraPapers ep
);
```


results: 
- 2975	Soil aggregate stablility and macrofauna as indicators of soil health and sustainable agricultural systems. Proceedings 810	2017
- 2974	Agricultural fertilisers contribute substantially to microplastic concentrations in UK soils	2024
- 2970	Herbicide resistance in Alopecurus myosuroides: The value of routine testing of seed samples submitted by farmers since 1985	2023
- 2969	The blackgrass genome reveals patterns of non?parallel evolution of polygenic herbicide resistance	2023
- 2971	The implications of spatially variable pre-emergence herbicide efficacy for weed management	2018
- 95	Biological weed control via nutrient competition: Potassium limitation of dandelions	1999
- 2826	Broadbalk Wheat Experiment cropping 1843-2021	2021
- 260	Using the long-term experiments at Rothamsted to address current agricultural and environmental issues.	1998
- 42	The Relationship between Crop Yields from an Experiment in Southern England and Long-Term Climate Variations	1995


and the other way round
```SQL 
SELECT ep.PaperID, ep.title, ep.Year
FROM `eraPapers` ep
WHERE PaperID NOT IN
(
SELECT PaperID
FROM `eraPapers-today` ept2
);
```
- 2990	Agricultural fertilisers contribute substantially to microplastic concentrations in UK soils	2024
- 2992	The blackgrass genome reveals patterns of non-parallel evolution of polygenic herbicide resistance	2023
- 2991	Herbicide resistance in Alopecurus myosuroides: The value of routine testing of seed samples submitted by farmers since 1985	2023
- 2868	The implications of spatially variable pre-emergence herbicide efficacy for weed management	2018
- 2989	Soil aggregate stablility and macrofauna as indicators of soil health and sustainable agricultural systems. Proceedings 810	2017
- 2984	Using the long?term experiments at Rothamsted to address current agricultural and environmental issues	1998
- 2985	Biological Weed Control via Nutrient Competition: Potassium Limitation of Dandelions	1999
- 2983	The relationship between crop yields from an experiment in southern England and long-term climate variations	1995


comparing the titles: 

SELECT ept.PaperID, ept.title, ept.Year

FROM `eraPapers-today` ept

WHERE title NOT IN

(

SELECT title

FROM eraPapers ep

);

- 2969	The blackgrass genome reveals patterns of non?parallel evolution of polygenic herbicide resistance	2023
- 260	Using the long-term experiments at Rothamsted to address current agricultural and environmental issues.	1998

```
select title, year, Journal, volume, Pages, count(*) from `eraPapers` ep group by title, year , Journal, volume, Pages having count(*)>1
```


---
## References
