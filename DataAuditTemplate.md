# Investigating Video Game Success — Stage 2 Data Audit
Eric Antwi Gyasi-Poku
2026-11-10

- [1: Project Overview](#1-project-overview)
- [2: Data Sources](#2-data-sources)
  - [2.1 Summary of sources](#21-summary-of-sources)
  - [2.2.1: Video Game Sales with
    Ratings](#221-video-game-sales-with-ratings)
  - [2.2.2 Steam Store Games](#222-steam-store-games)
  - [2.3: Investigated and rejected
    sources](#23-investigated-and-rejected-sources)
  - [2.4: What I could not find](#24-what-i-could-not-find)
- [3: Licensing and permissions](#3-licensing-and-permissions)
  - [3.1: Licence by source](#31-licence-by-source)
  - [3.2: Unresolved licensing](#32-unresolved-licensing)
  - [3.3: Downstream permissions](#33-downstream-permissions)
- [4: Consent and identifiability](#4-consent-and-identifiability)
- [5: Exclusions and harms](#5-exclusions-and-harms)
  - [5.1: Excluded data from the
    audit](#51-excluded-data-from-the-audit)
  - [5.2: Who could be harmed](#52-who-could-be-harmed)
  - [5.3: Unreleased working data](#53-unreleased-working-data)
- [6: Data Stewardship](#6-data-stewardship)
- [7: Use of AI](#7-use-of-ai)
- [8: Session information](#8-session-information)

# 1: Project Overview

The aim for my project is to investigate what factors contribute to the
success of video games, and i will be focusing on characteristics like
genre platform, release year,sales performance, etc.i want to look
through a lot of variables to which ones perform better and how it can
changed over time. My guess is that game success is influenced by genre,
platform and some combinations achieving higher sales than others.

------------------------------------------------------------------------

# 2: Data Sources

## 2.1 Summary of sources

| Source | Producer | Format | Coverage | Using |
|:---|:---|:---|:---|:---|
| Video Game Sales with Ratings | VGChartz / Metacritic; Kaggle | CSV | Multiple platforms, 1980–2016 | Yes |
| Steam Store Games | Steam Store / SteamSpy; Kaggle | CSV | PC games on Steam, collected in 2019 | yes |
| Essential Facts 2026 | Entertainment Software Association | Web report | United States, 2026 | No |

## 2.2.1: Video Game Sales with Ratings

**Producer and authority.** The dataset was compiled by Rush kirubi.
Using video game sales information from VGChartz and review scores from
Metacritic. it was published on kaggle for public use and analysis.I
could not find evidence that it was produced under a specific research
grant or government mandate.

**Original Dataset Purpose.** The dataset was created to add video game
sales with critic and user ratings and other information. The creator
suggested using the data for things like machine learning and data
visualization. this will be relevant to my project because I want to
find out which factors,like genre, platform, release year, and ratings,
are associated with video game success.

**Collection method.** The data was collected through web scraping. the
sale information was from VGChartz, and ratings and critic part was from
metacritic

**Coverage and resolution.** The dataset contains about 16,719 records
and contains video games released between 1980 and 2016 on multiple
gaming platforms. Each row represents a game on a particular platform.
Sales are in millions of units, with separate columns for North America,
Europe, Japan, other regions, and global sales.

**Licence.** it shows lincense as unknown on the kaggle website.I could
not confirm a specific licence granting permission to redistribute the
data.

**Access.** The dataset is available on Kaggle at
https://www.kaggle.com/datasets/rush4ratio/video-game-sales-with-ratings/data.
It can be downloaded as a CSV file, although a Kaggle account may be
required. Another researcher could retrieve it from the same page.

**Known problems.** One limitation i noticed is missing information,
mainly for critic scores, user scores, and ESRB ratings. According to
the dataset description, only approximately 6,900 records have complete
observations. Metacritic does not cover every gaming platform, which is
why there are missing values. The dataset also contains mostly older
games(ends in 2016) and may not accurately represent the current video
game industry. Finally, the sales figures are really close estimates and
not actual verified transactions.

    Rows: 16,719
    Columns: 16
    $ Name            <chr> "Wii Sports", "Super Mario Bros.", "Mario Kart Wii", "…
    $ Platform        <chr> "Wii", "NES", "Wii", "Wii", "GB", "GB", "DS", "Wii", "…
    $ Year_of_Release <chr> "2006", "1985", "2008", "2009", "1996", "1989", "2006"…
    $ Genre           <chr> "Sports", "Platform", "Racing", "Sports", "Role-Playin…
    $ Publisher       <chr> "Nintendo", "Nintendo", "Nintendo", "Nintendo", "Ninte…
    $ NA_Sales        <dbl> 41.36, 29.08, 15.68, 15.61, 11.27, 23.20, 11.28, 13.96…
    $ EU_Sales        <dbl> 28.96, 3.58, 12.76, 10.93, 8.89, 2.26, 9.14, 9.18, 6.9…
    $ JP_Sales        <dbl> 3.77, 6.81, 3.79, 3.28, 10.22, 4.22, 6.50, 2.93, 4.70,…
    $ Other_Sales     <dbl> 8.45, 0.77, 3.29, 2.95, 1.00, 0.58, 2.88, 2.84, 2.24, …
    $ Global_Sales    <dbl> 82.53, 40.24, 35.52, 32.77, 31.37, 30.26, 29.80, 28.92…
    $ Critic_Score    <dbl> 76, NA, 82, 80, NA, NA, 89, 58, 87, NA, NA, 91, NA, 80…
    $ Critic_Count    <dbl> 51, NA, 73, 73, NA, NA, 65, 41, 80, NA, NA, 64, NA, 63…
    $ User_Score      <chr> "8", NA, "8.3", "8", NA, NA, "8.5", "6.6", "8.4", NA, …
    $ User_Count      <dbl> 322, NA, 709, 192, NA, NA, 431, 129, 594, NA, NA, 464,…
    $ Developer       <chr> "Nintendo", NA, "Nintendo", "Nintendo", NA, NA, "Ninte…
    $ Rating          <chr> "E", NA, "E", "E", NA, NA, "E", "E", "E", NA, NA, "E",…

    # A tibble: 16,719 × 6
       Name                      Platform Year_of_Release Genre   Publisher NA_Sales
       <chr>                     <chr>    <chr>           <chr>   <chr>        <dbl>
     1 Wii Sports                Wii      2006            Sports  Nintendo      41.4
     2 Super Mario Bros.         NES      1985            Platfo… Nintendo      29.1
     3 Mario Kart Wii            Wii      2008            Racing  Nintendo      15.7
     4 Wii Sports Resort         Wii      2009            Sports  Nintendo      15.6
     5 Pokemon Red/Pokemon Blue  GB       1996            Role-P… Nintendo      11.3
     6 Tetris                    GB       1989            Puzzle  Nintendo      23.2
     7 New Super Mario Bros.     DS       2006            Platfo… Nintendo      11.3
     8 Wii Play                  Wii      2006            Misc    Nintendo      14.0
     9 New Super Mario Bros. Wii Wii      2009            Platfo… Nintendo      14.4
    10 Duck Hunt                 NES      1984            Shooter Nintendo      26.9
    # ℹ 16,709 more rows

The output showed info of dataset like number of rows and column. And
all column titles with with their data type(chr,dbl, etc) and a few
examples of them. And under that was first 6 columns of dataset and
first 10 rows of the dataset

## 2.2.2 Steam Store Games

**Producer and authority.** The dataset was put together by Nik Davis.
He used information from the Steam Store and also SteamSpy APIs. Steam
gave information about games available on its platform, while SteamSpy
gave estimated ownership and other game statistics. This dataset is
available for public and can be shared rather than an official
government or academic research dataset. I did not find anything about
specific research grant or government mandate for this one too

**Original Dataset Purpose.** The dataset was created to give info about
games that are on Steam for data analysis and research. It has
information such as game genres, prices, reviews, estimated ownership,
and average playtime. These variables are important to my project
because they can help me find factors that help in making video game
popular and successful.

**Collection method.** The data was collected automatically from Steam
and SteamSpy using computer programs. Information from these sources was
then added into CSV files. This is secondary data collected from online
gaming platforms.

**Coverage and resolution.** The dataset has about 27,000 games
available on Steam. The data was collected around May 2019. Each row in
the main steam.csv file is one game on steam. The dataset includes game
titles, release dates, genres, prices, categories, estimated owners,
ratings, and playtime. but it is only limited to PC games that are on
Steam and does not represent the entire video game industry.

**Licence.** The license for this dataset is the Creative Commons
Attribution 4.0 International (CC BY 4.0) licence. This allows reuse
with appropriate attribution, As long as the licence rules are followed.

**Access.** The dataset is publicly available on Kaggle at
https://www.kaggle.com/datasets/nikdavis/steam-store-games. It can be
downloaded as a ZIP file containing many CSV files, including steam.csv,
which I plan to use for my analysis. Other researchers can access the
dataset through the same page.

**Known problems.** One of the limitation is that the dataset was
collected in 2019, so it does not include very new games or reflect
current prices, reviews, and player activity. The ownership figures are
estimates rather than verified sales numbers. The dataset are only about
Steam games(pc), that mean it may not apply to console games or other
platform games. I will also check for missing values, duplicates, and
inconsistencies before beginning my analysis.

    Rows: 27,075
    Columns: 18
    $ appid            <dbl> 10, 20, 30, 40, 50, 60, 70, 80, 130, 220, 240, 280, 3…
    $ name             <chr> "Counter-Strike", "Team Fortress Classic", "Day of De…
    $ release_date     <date> 2000-11-01, 1999-04-01, 2003-05-01, 2001-06-01, 1999…
    $ english          <dbl> 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1,…
    $ developer        <chr> "Valve", "Valve", "Valve", "Valve", "Gearbox Software…
    $ publisher        <chr> "Valve", "Valve", "Valve", "Valve", "Valve", "Valve",…
    $ platforms        <chr> "windows;mac;linux", "windows;mac;linux", "windows;ma…
    $ required_age     <dbl> 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0,…
    $ categories       <chr> "Multi-player;Online Multi-Player;Local Multi-Player;…
    $ genres           <chr> "Action", "Action", "Action", "Action", "Action", "Ac…
    $ steamspy_tags    <chr> "Action;FPS;Multiplayer", "Action;FPS;Multiplayer", "…
    $ achievements     <dbl> 0, 0, 0, 0, 0, 0, 0, 0, 0, 33, 147, 0, 54, 0, 0, 0, 1…
    $ positive_ratings <dbl> 124534, 3318, 3416, 1273, 5250, 2758, 27755, 12120, 3…
    $ negative_ratings <dbl> 3339, 633, 398, 267, 288, 684, 1100, 1439, 420, 2419,…
    $ average_playtime <dbl> 17612, 277, 187, 258, 624, 175, 1300, 427, 361, 691, …
    $ median_playtime  <dbl> 317, 62, 34, 184, 415, 10, 83, 43, 205, 402, 400, 214…
    $ owners           <chr> "10000000-20000000", "5000000-10000000", "5000000-100…
    $ price            <dbl> 7.19, 3.99, 3.99, 3.99, 3.99, 3.99, 7.19, 7.19, 3.99,…

    # A tibble: 27,075 × 6
       appid name                           release_date english developer publisher
       <dbl> <chr>                          <date>         <dbl> <chr>     <chr>    
     1    10 Counter-Strike                 2000-11-01         1 Valve     Valve    
     2    20 Team Fortress Classic          1999-04-01         1 Valve     Valve    
     3    30 Day of Defeat                  2003-05-01         1 Valve     Valve    
     4    40 Deathmatch Classic             2001-06-01         1 Valve     Valve    
     5    50 Half-Life: Opposing Force      1999-11-01         1 Gearbox … Valve    
     6    60 Ricochet                       2000-11-01         1 Valve     Valve    
     7    70 Half-Life                      1998-11-08         1 Valve     Valve    
     8    80 Counter-Strike: Condition Zero 2004-03-01         1 Valve     Valve    
     9   130 Half-Life: Blue Shift          2001-06-01         1 Gearbox … Valve    
    10   220 Half-Life 2                    2004-11-16         1 Valve     Valve    
    # ℹ 27,065 more rows

## 2.3: Investigated and rejected sources

Essential Facts About the U.S. Video Game Industry (2026) —
Entertainment Software Association (ESA). I considered this report
because i wanted to also find correlation between age of gamers, what
they play and see if there is correlation between age and game sales.
However, it mainly provides combined or summarized statistics from many
individual observations rather than player-age information for
individual games, making it difficult to connect age demographics with
game sales and success.

## 2.4: What I could not find

As i mentioned above,I initially wanted to explore whether the average
age of video game players has a relationship with game success. But, I
could not find a freely accessible dataset that provides player-age
demographics for individual games with their sales or popularity. i
found some related information, but the available information I found
was either already analyzed into graph ,etc or did not include the
detailed data I needed. Because of this, I decided not to include player
age in my analysis and will instead focus on factors such as genre,
platform, release year, ratings, and sales.

------------------------------------------------------------------------

# 3: Licensing and permissions

## 3.1: Licence by source

| Source | Licence | Attribution_required | Attribution_given |
|:---|:---|:---|:---|
| Video Game Sales with Ratings | Unknown | Unknown | Yes - source credited |
| Steam Store Games | CC BY 4.0 | Yes | Yes |

**Attribution statements.** Steam Store Games: Dataset compiled by Nik
Davis, Steam Store Games (Clean dataset), available at
https://www.kaggle.com/datasets/nikdavis/steam-store-games. Licensed
under Creative Commons Attribution 4.0 International (CC BY 4.0):
https://creativecommons.org/licenses/by/4.0/. If i make any cleaning or
transformations during this project, it will be documented.

Video Game Sales with Ratings: Dataset compiled by Rush Kirubi using
information from VGChartz and Metacritic. Available at
https://www.kaggle.com/datasets/rush4ratio/video-game-sales-with-ratings/data.
The dataset’s licence is listed as unknown.

## 3.2: Unresolved licensing

For the Video Game Sales with Ratings dataset, it shows up on the
website with an unknown licence. I checked the dataset’s Kaggle page,
including its description and information about licensing, but could not
find a specific licence granting permission to redistribute the data.
The dataset adds information from VGChartz and Metacritic, so maybe the
original sources permissions may also apply.But until I can confirm the
relevant permissions, I will not publicly redistributing the raw dataset
but i will give or show a link to the original website page.

## 3.3: Downstream permissions

for steam store game data it is under license CC BY 4.0, which allows
others to adapt and use the material again as long as right attribution
is provided.but,the Video Game Sales with Ratings dataset has an unknown
licence, so I cannot just assume that other people have permission to
redistribute or modify its data. For this project, I plan to share my R
code, analysis, and visualizations with source acknowledgements, with
links to the original datasets rather than redistributing the files. I
will not also combine and republish the datasets as a new downloadable
dataset unless i find out that i have permission to do that.

------------------------------------------------------------------------

# 4: Consent and identifiability

My data is not describing people because it is about sales, game
ratings, genre, and other stuff do not describe people (eg name, date of
birth, etc).Since I am not collecting personal information or doing
surveys or interviews, individual participant consent is not needed for
my analysis.

**Consent.** I did not collect the data myself. Both datasets were
collected by other people from VGChartz, Metacritic, Steam, and
SteamSpy. The datasets contain information about video games rather than
individual players. I could not confirm what users were told when their
ratings or reviews were originally collected. However, I will only use
the available game level information for my analysis and will not try to
identify individual users.

**Identifiability.** None of the dataset contains individual player
names, usernames, addresses, or other direct personal information. Each
observation represents a video game or a game on a particular platform
rather than an individual player. Although the datasets include user
ratings and estimated player ownership, these are reported as combined
information from many players rather than identifiable player records.
Therefore, the risk of identifying individual players from the data is
low.

**How sensitive data will be used.** i dont think the project i am
trying to do is gonna have sensitive information because of how my
project is and the data i am gonna be using are not personal or
sensitive. I do not expect to need anonymization or suppression of
personal identifiers because none are included in the variables I plan
to analyze.

------------------------------------------------------------------------

# 5: Exclusions and harms

## 5.1: Excluded data from the audit

At this stage, I have not removed any columns or rows from the datasets
because I am still looking through the data. However, I may exclude
records with missing information, especially missing sales figures or
review scores, depending on the analysis. Removing these records could
affect my results because some games or platforms may be less
represented than others. I will document any changes I make during data
cleaning.

## 5.2: Who could be harmed

people that can be harmed are game developers, publishers, and smaller
gaming companies. They could be negatively affected if my findings are
misunderstood or misused. For example, maybe if my analysis suggests
that certain genres or types of games are less successful, people might
assume that games in those categories are not worth developing or
investing in. This could discourage some smaller developers who create
games for those audiences. Also, the datasets contain estimated sales
and ownership figures, so treating these estimates as exact numbers
could lead to unfair comparisons.s

## 5.3: Unreleased working data

I would not publicly share the original Video Game Sales with Ratings
dataset because its licence is unknown. However, I can provide a link to
the original Kaggle page so others can access it themselves. I plan to
share my analysis and R code while giving credit to the original data
sources.

------------------------------------------------------------------------

# 6: Data Stewardship

**Where it lives.** my project files will be in my github repository.

**Who maintains it.** i will maintain it. I do not currently have plans
to regularly update or maintain it after course ends but we will see if
i can

**Formats and dependencies.** i think people can still open the file
after a long time. because it will be in csv form which i dont think
will not be outdated. if there are changes to packages in future it
could cause problems. Also if the website i got the datasets from are
shut down or now running anymore, it would be difficult to reproduce

**Lifespan.** The project will be useful as a historical analysis of
video game success, but it may not accurately represent the current
gaming industry because the datasets contain older information. To keep
the analysis relevant to newer games and industry trends, the data would
need to be updated.

------------------------------------------------------------------------

# 7: Use of AI

**AI log:** [AI-log.md](log/AI-log.md) — maintained from November
10,2026 and committed alongside each stage of work.

I used chatgpt to help me find more dataset and dataset that also has
age in it since i was struggling to find a good one but i still didn’t
get a good one. i also use it to help me find where i can see the
licensing stuff.And i didn’t really get what the format and dependencies
part mean so i ask it to explain it to me and i did the rest myself

------------------------------------------------------------------------

# 8: Session information

    R version 4.6.1 (2026-06-24 ucrt)
    Platform: x86_64-w64-mingw32/x64
    Running under: Windows 11 x64 (build 26200)

    Matrix products: default
      LAPACK version 3.12.1

    locale:
    [1] LC_COLLATE=English_Canada.utf8  LC_CTYPE=English_Canada.utf8   
    [3] LC_MONETARY=English_Canada.utf8 LC_NUMERIC=C                   
    [5] LC_TIME=English_Canada.utf8    

    time zone: America/Halifax
    tzcode source: internal

    attached base packages:
    [1] stats     graphics  grDevices utils     datasets  methods   base     

    other attached packages:
     [1] knitr_1.52      lubridate_1.9.5 forcats_1.0.1   stringr_1.6.0  
     [5] dplyr_1.2.1     purrr_1.2.2     readr_2.2.0     tidyr_1.3.2    
     [9] tibble_3.3.1    ggplot2_4.0.3   tidyverse_2.0.0

    loaded via a namespace (and not attached):
     [1] bit_4.6.0          gtable_0.3.6       jsonlite_2.0.0     crayon_1.5.3      
     [5] compiler_4.6.1     tidyselect_1.2.1   parallel_4.6.1     scales_1.4.0      
     [9] yaml_2.3.12        fastmap_1.2.0      R6_2.6.1           generics_0.1.4    
    [13] pillar_1.11.1      RColorBrewer_1.1-3 tzdb_0.5.0         rlang_1.3.0       
    [17] utf8_1.2.6         stringi_1.8.9      xfun_0.61          S7_0.2.2          
    [21] bit64_4.8.6        otel_0.2.0         timechange_0.4.0   cli_3.6.6         
    [25] withr_3.0.3        magrittr_2.0.5     digest_0.6.39      grid_4.6.1        
    [29] vroom_1.7.1        rstudioapi_0.19.0  hms_1.1.4          lifecycle_1.0.5   
    [33] vctrs_0.7.3        evaluate_1.0.5     glue_1.8.1         farver_2.1.2      
    [37] rmarkdown_2.32     tools_4.6.1        pkgconfig_2.0.3    htmltools_0.5.9   
