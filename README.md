![MIKES DATA WORK GIT REPO](https://raw.githubusercontent.com/mikesdatawork/images/master/git_mikes_data_work_banner_01.png "Mikes Data Work")        

# Find SQL Compatibility Levels And SQL Version Support
**Post Date: June 23, 2017**        



## Contents    
- [About Process](##About-Process)  
- [SQL Logic](#SQL-Logic)  
- [Build Info](#Build-Info)  
- [Author](#Author)  
- [License](#License)       

## About-Process


![Compatibility Levels And SQL Support]( https://mikesdatawork.files.wordpress.com/2017/06/image001.png "Get SQL Compatibility Levels And Support")
 
<p>Here's some quick SQL logic that shows the Compatibility_Level with the type of support from the different SQL Versions out there.</p>      


## SQL-Logic
```SQL
--find all compatibility levels per database and see what other SQL versions support it.
 
use master;
set nocount on
 
select
    'server_name'         = @@servername
,   'database_name'       = upper(sd.name)
,   'compatability_level' =
                case cast(sd.compatibility_level as varchar(255))
                    when 60     then '60 (SQL 6.0)      Works only on SQL 6'
                    when 65     then '65 (SQL 6.5)      Works only on SQL 6.5'
                    when 70     then '70 (SQL 7.0)      Works only on SQL 7'
                    when 80     then '80 (SQL 2000)     Works only on SQL 2000'
                    when 90     then '90 (SQL 2005)     Works on SQL 2005, 2000'
                    when 100    then '100 (SQL 2008)    Works on SQL 2008R2, 2005'
                    when 110    then '110 (SQL 2012)    Works on SQL 2012, 2008R2, 2005'
                    when 120    then '120 (SQL 2014)    Works on SQL 2014, 2012, 2008R2'
                    when 130    then '130 (SQL 2016)    Works on SQL 2016, 2014, 2012, 2008R2'
                    when 140    then '140 (SQL 2017)    Works on SQL 2017, 2016, 2014, 2012, 2008R2'
                end
from
    sys.databases sd
where
    database_id <> 2
order by
    sd.name
,   sd.compatibility_level desc
```
Feel free to check Microsoft Documentation to verify found here:
https://docs.microsoft.com/en-us/sql/t-sql/statements/alter-database-transact-sql-compatibility-level



[![WorksEveryTime](https://forthebadge.com/images/badges/60-percent-of-the-time-works-every-time.svg)](https://shitday.de/)

## Build-Info

| Build Quality | Build History |
|--|--|
|<table><tr><td>[![Build-Status](https://ci.appveyor.com/api/projects/status/pjxh5g91jpbh7t84?svg?style=flat-square)](#)</td></tr><tr><td>[![Coverage](https://coveralls.io/repos/github/tygerbytes/ResourceFitness/badge.svg?style=flat-square)](#)</td></tr><tr><td>[![Nuget](https://img.shields.io/nuget/v/TW.Resfit.Core.svg?style=flat-square)](#)</td></tr></table>|<table><tr><td>[![Build history](https://buildstats.info/appveyor/chart/tygerbytes/resourcefitness)](#)</td></tr></table>|

## Author

[![Gist](https://img.shields.io/badge/Gist-MikesDataWork-<COLOR>.svg)](https://gist.github.com/mikesdatawork)
[![Twitter](https://img.shields.io/badge/Twitter-MikesDataWork-<COLOR>.svg)](https://twitter.com/mikesdatawork)
[![Wordpress](https://img.shields.io/badge/Wordpress-MikesDataWork-<COLOR>.svg)](https://mikesdatawork.wordpress.com/)

     
## License
[![LicenseCCSA](https://img.shields.io/badge/License-CreativeCommonsSA-<COLOR>.svg)](https://creativecommons.org/share-your-work/licensing-types-examples/)

![Mikes Data Work](https://raw.githubusercontent.com/mikesdatawork/images/master/git_mikes_data_work_banner_02.png "Mikes Data Work")

