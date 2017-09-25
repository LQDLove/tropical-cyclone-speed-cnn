# tropical-cyclone-speed-cnn
CNN based wind speed estimation of tropical cyclones based on IR/WV satellite imagery


**CURRENT STATUS: DATA STILL CRAWLING**

Data Source: https://www.nrlmry.navy.mil/TC.html

## Sample Data 


<img src="https://www.nrlmry.navy.mil/tcdat/tc17/ATL/15L.MARIA/ir/geo/1km/20170924.1815.goes13.x.ir1km.15LMARIA.90kts-943mb-291N-730W.100pc.jpg" width="250" />
<img src="https://www.nrlmry.navy.mil/tcdat/tc17/ATL/15L.MARIA/vapor/geo/1km/20170924.1815.goes13.x.wv1km.15LMARIA.90kts-943mb-291N-730W.100pc.jpg" width="250" />

Hurricane Maria, 90kts, 2017-09-24 18:15 UTC

## Example of Observational Information:

year|basin|storm|time|wind|pressure|n_images
---|---|---|---|---|---|---
2006|ATL|01L.ALBERTO|2006-06-11 13:00:45|40|1002.0|1
2006|ATL|01L.ALBERTO|2006-06-11 13:00:45|40|1002.0|1
2006|ATL|01L.ALBERTO|2006-06-11 14:00:15|40|1002.0|1
2006|ATL|01L.ALBERTO|2006-06-11 14:00:15|40|1002.0|1
2006|ATL|01L.ALBERTO|2006-06-11 14:00:45|40|1002.0|1
2006|ATL|01L.ALBERTO|2006-06-11 14:00:45|40|1002.0|1
2006|ATL|01L.ALBERTO|2006-06-11 15:00:00|40|1002.0|1
2006|ATL|01L.ALBERTO|2006-06-11 15:00:00|40|1002.0|1
2006|ATL|01L.ALBERTO|2006-06-11 15:00:15|40|1002.0|1
2006|ATL|01L.ALBERTO|2006-06-11 15:00:15|40|1002.0|1

## Aggregated storm information

year|storm|basin|max_speed|min_pressure|start_time|end_time|n_images|ace|category
---|---|---|---|---|---|---|---|---|---
2006|01L.ALBERTO|ATL|60|996.0|2006-06-11 13:00:45|2006-06-15 15:00:45|440|3.0|TS
2006|02L.BERYL|ATL|50|1002.0|2006-07-18 20:00:45|2006-07-21 20:00:15|272|2.2|TS
2006|03L.CHRIS|ATL|55|1001.0|2006-08-01 08:00:45|2006-08-06 22:00:15|525|2.7|TS
2006|04L.DEBBY|ATL|45|1000.0|2006-08-23 06:00:00|2006-08-28 02:00:30|877|2.5|TS
2006|05L.ERNESTO|ATL|65|987.0|2006-08-25 18:00:45|2006-09-01 19:00:45|596|5.5|1
2006|06L.FLORENCE|ATL|80|963.0|2006-09-05 14:00:30|2006-09-18 04:00:00|1308|16.9|1
2006|07L.GORDON|ATL|105|955.0|2006-09-11 17:00:45|2006-09-21 02:00:00|937|20.9|3
2006|08L.HELENE|ATL|110|954.0|2006-09-14 06:00:30|2006-09-26 23:00:30|1505|26.6|3
2006|09L.ISAAC|ATL|75|985.0|2006-09-28 13:00:15|2006-10-03 01:00:45|355|6.1|1
2006|01C.IOKE|CPAC|140|900.0|2006-08-20 07:00:30|2006-09-06 17:00:30|2190|86.5|5

## Aggregated seasonal statistics
year|basin|max_speed|min_pressure|start_time|end_time|max ace|sum ace|n_storms|n_images|n_maj|n_hur
---|---|---|---|---|---|---|---|---|---|---|---
2006|ATL|110|954.0|2006-06-11 13:00:45|2006-10-03 01:00:45|26.6|86.4|9|6815|2|5
2006|CPAC|140|900.0|2006-08-20 07:00:30|2006-09-06 17:00:30|86.5|86.5|1|2190|1|1
2006|EPAC|130|933.0|2006-05-27 18:00:00|2006-11-22 17:00:45|30.3|135.8|18|14605|5|10
2006|IO|125|916.0|2006-04-26 07:00:30|2006-09-28 06:00:30|10.1|13.4|2|1113|1|1
2006|SHEM|155|879.0|2005-11-19 18:00:30|2006-04-27 14:00:30|32.0|164.2|19|8261|7|11
2006|WPAC|140|898.0|2006-05-09 13:00:56|2006-12-19 21:00:56|31.2|258.8|21|16374|10|14
2007|ATL|145|909.0|2007-05-09 13:00:45|2007-12-16 23:00:45|34.0|79.4|14|6818|2|4
2007|EPAC|120|946.0|2007-05-29 01:00:30|2007-10-25 04:00:30|22.6|59.0|11|5310|1|4
2007|WPAC|95|956.0|2007-10-12 02:00:30|2007-11-24 06:00:30|3.1|9.8|7|502|0|4
2008|ATL|90|979.0|2008-11-06 00:00:45|2008-11-12 14:00:15|4.5|4.5|1|432|0|1