# Worldwide Economic Impact of Russia's Invasion of Ukraine

## Data Sources

### The FAO Food Price Index
The Food and Agriculture Organization of the United Nations publishes the FAO Food Price Index (FFPI), which is a monthly measure of international prices of selected food commodities. This includes an overall index, as well as an index for each of the categories 'Meat', 'Dairy', 'Cereals', 'Oils', and 'Sugar'. For more information, see [here](https://www.fao.org/worldfoodsituation/foodpricesindex/en).

### Commodities-API
Theis analysis uses data from the [Commodities-API](https://www.commodities-api.com/). Specifically, it uses the [Commodities-API time-series endpoint](https://www.commodities-api.com/documentation#timeseries). The request for this endpoint requires five parameters: an access key, the start date of the timeframe, the end date of the time frame, 'base' (a three-letter currency code of the preferred base currency), and 'symbols' (the currency or commodity code). The maximum timeframe in a request is 365 days.

### UN comtrade database API
Data is extracted from the UN comtrade database API via an API, documentation for which can be found [here](https://comtrade.un.org/data/doc/api/). Details of all the possible options in the API call can be found in the documentation but the specific parameters used in this analysis are as follows:
* 'max' is the maximum number of records returned, set to 100,000 below.
* 'type' allows you tp specify whether you want commodities ('C') or services ('S') data.
* 'freq' is the dataset frequency, which can be set to annual ('A') or monthly ('M').
* 'px' is the trade specification scheme (set to 'HS' below which stands for "Harmonized System, as reported").
* 'ps' is the time period data is requested for.
* 'r' stands for 'reporting area', set to 'all'.
* 'p' stands for partner area. We set this to '0' (World), '643' (Russian Federation) and '804' (Ukraine).
* 'rg' denotes the type of trade flow (imports=1).
* 'cc' denotes the commodity type. Below, we use 1001 for 'Wheat and meslin' and 270900 for 'Oils; petroleum oils and oils obtained from bituminous minerals, crude'.
