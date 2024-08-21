# Power BI Desktop: Summer Olympics Report 

![](https://w7.pngwing.com/pngs/55/943/png-transparent-2012-summer-olympics-2020-summer-olympics-2016-summer-olympics-2018-winter-olympics-olympic-games-olympic-rings-miscellaneous-flag-sport.png)

*Note: This project is presented in a dashboard-like style, but as Power BI has another separate feature officially known as Dashboards on Power BI Service, the Power BI term Report shall be used to avoid confusion.*

This project is aimed at creating a Power BI report to present key facts and trends on the 1896 - 2016 Summer Olympic Games in a visual dashboard-like format. This interactive and dynamic multiple-page report comes well-supported with:

- **Slicers** to enable full-fledged self-service analytics functionalities
- **Bookmarks, page navigation and buttons** for enhanced user experience and friendliness
- **Dynamic image** for greater report dynamism
- **Cross-filtering and highlighting** for more interactivity between visuals
- A spectrum of **visuals** including (but not limited to) radar charts, funnel charts, R script visuals and maps, each one specially curated to convey a specific data point
- **Tooltips** to finish each visual with even more informative content
- **DAX functions** for data manipulation with calculated measures, columns and tables
- … and many more!

## Data Source

The raw data used in this project can be found [here](https://mavenanalytics.io/data-playground?page=8&pageSize=5) (click on 120 Years of Olympic History). It contains the following files: 

- `athlete_events.csv` where each row records an athlete’s participation in an event in an Olympic Games from 1896 to 2016, with information on the athlete’s age, representing nation, medal won for that event etc. 

- `country_definitions.csv` is a data table unpacking the names of the NOC abbreviations used in `athlete_events.csv`. 

- Data dictionaries `athlete_events_data_dictionary.csv` and `country_definitions_data_dictionary.csv` to explain each variable in `athlete_events.csv` and `country_definitions.csv`.

In addition, the attached Excel file `Summer_Olympics_Logo.xlsx` was manually compiled and used to generate the dynamic image in the report. It contains URLs to each Summer Olympics logo in history.

## Caveats

- The original dataset `athlete_events.csv` contains data on both the Summer and Winter Olympic Games. For a more focused analysis, this report will narrow down to Summer Olympic Games only. 

- The original dataset `athlete_events.csv` contains duplicate rows. As repeated participation in the same event in the same Games makes no sense, these duplicated rows were dropped. 

- The original dataset `country_definitions.csv` records Singapore’s NOC abbreviation as SIN but `athlete_events.csv` refers to it as SGP. For standardization and table joining, SIN in `country_definitions.csv` was replaced with SGP.

- Host cities listed in the City column of `athlete_events.csv` were manually mapped to the countries they were in via a calculated column to produce the Host NOCs rank chart. The mapping is as follows:

  | **City** | **Host NOC** |
  | -------- | -------- |
  | Athina | GRE |
  | Paris | FRA |
  | St. Louis | USA |
  | London | GBR |
  | Stockholm | SWE |
  | Antwerpen | BEL |
  | Amsterdam | NED |
  | Los Angeles | USA |
  | Berlin | GER |
  | Helsinki | FIN |
  | Melbourne | AUS |
  | Roma | ITA |
  | Tokyo | JPN |
  | Mexico City | MEX |
  | Munich | FRG |
  | Montreal | CAN |
  | Moskva | URS |
  | Seoul | KOR |
  | Barcelona | ESP |
  | Atlanta | USA |
  | Sydney | AUS |
  | Beijing | CHN |
  | Rio de Janeiro | BRA |

- The 1906 Intercalated Summer Olympics Games is not considered an official season of the Games, but since it is included in the original dataset `athlete_events.csv`, it will be kept for analysis<sup>1</sup>.

- If both `region` and `notes` column values are present for a particular NOC abbreviation, the `notes` column value will be used as the NOC name in this report, else `region`. This is because the `notes` value tends to be more specific and accurate that the `region` value. 

- NOC names in this report are structured as the name followed by the NOC’s abbreviation. The abbreviation is included as an identifier since some NOCs have the same name but different NOCs *eg* Russia - URS and Russia - RUS.

## Post-Project Insights

- There were 29 Summer Olympic Games from 1896 to 2016<sup>1</sup>. In total, 116,776 athletes from 230 NOCs participated in these Games. 

- In the past, most participating athletes in the Summer Olympics were male. However, in recent years, the number of female athletes has increased tremendously and is now close to the number of male athletes. It seems that gender parity at the Games is no longer a dream. 

- Only 5 NOCs participated in all 29 seasons of the Games: France (FRA), Greece (GRE), Italy (ITA), Switzerland (SUI) and UK (GBR). 

- 23 different cities hosted the Games. Both London and Athina (Athens) hosted the Games thrice — the most number of times among all 23 cities. 

- A total of 52 sports were played in the history of the Summer Olympic Games. Athletics, Cycling, Fencing, Gymnastics and Swimming are the only sports to be played at all 29 Games. Rugby sevens is the latest addition, and Golf has made a comeback to the Games after 112 years. Sports like Basque Pelota, Cricket, Croquet, Jeu De Paume and Roque were only played in 1 season and have been discontinued ever since. 

- It appears that the country with the most participating athletes and the host country tend to get a good rank at the Games in that particular year. However, countries that send the most athletes seem to have more ‘stable’ performance — all but 1 made it to the top 5 in medal tally rank in their respective years. On the other hand, several host countries dropped out of the top 10 in the year they hosted, with 1 host country ranking 27th overall. That being said, it has to be noted that on many occasions, the country that sends the most athletes is the host country itself. 

- USA (USA), Russia (URS), France (FRA), Germany (GER), Russia (EUN), China (CHN) and UK (GBR) are the only NOCs to top the medal tally at the Games. USA (USA) significantly surpasses the rest of these NOCs in the number of times it reached first place. USA (USA) came in first on 17 Games — more than half the number of Games in history.

- Most gold medallists get their gold medals at the age of 21 to 24. Perhaps this is the peak performance age for athletes.



