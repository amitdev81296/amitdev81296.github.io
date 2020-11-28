# Airport Information Scraper

Here we present a dataset that stores information about airports such as airport name, location coordinates (latitude and longitude), IATA code and IACO code.

### General Information
    Dataset Name                Airports
    Institution Name            Drexel University, Philadelphia, PA
    Data Investigators          Alex Van Kooy
                                Amit Nijsure
                                Fernando Ramirez
                                Abdulaziz Alquzi
    Contact Person              Prof. Christopher MacLellan
    Date of Data Collection     28 November, 2020
    Data Collected From         Wikipedia (Tampa Data Center)
    Language                    English
    Collector Script            airport_data_collection.ipynb (Jupyter Notebook)
    Purpose of Data Collection  Educational

### Data and File Overview
    File Name              airports.csv
    File Description       Link | Name | IATA | ICAO | Location | Latitude | Longitude
    File Format            Comma Separated Values (CSV)
    File Created On        28 November, 2020
    File Updated On        28 November, 2020
    
### Methodological Information
1. Wikipedia stores airport information alphabetically using the International Air Transport Association (IATA) codes.
2. We collect the data for alphabetically (A through Z) and periodically store it in the CSV file to avoid memory overload.
3. The **_collect_data_** method in our code is built to accept an alphabet, go to the Wikipedia page containing tablularized information about the airports with IATA codes starting with that alphabet, scrape the available information - Link, Name and Location - and then visit each airport's individual Wikipedia page to fetch the location coordinates (latitude and logitude) information.
4. The **_collect_data_** method internally checks for deadlinks and incorrect airport links and segregates these unreachable airports into another data structure
5. The **_get_lat_long_** method uses a Beautiful Soup (BS4) Object to parse the latitude and longitude information from a particular airport's Wikipedia page.
6. After the information for airports has been stored in the dictionary we try to fill as many missing values as we can from another [publicly available dataset](https://raw.githubusercontent.com/jpatokal/openflights/master/data/airports.dat).
7. After all possible data is collected for an alphabet, we print out the time taken for scraping, number of pages scraped (successfully and unsuccessfully) and the size of the data collected, we use the **_csv.DictWriter_** module in Python to store the collected data to our main dataset file.

### Data-specific Information
    Number of Data Attributes       7
    Number of Rows (Records)        9,047
    Attribute List                  Link | Name | IATA | ICAO | Location | Latitude | Longitude

### Prerequisites For Running The Script
Please make sure you have the latest version of Python installed on your system before proceeding with running the script. We have also used some Python libraries such as _lat-lon-parser_ (for easier parsing of coordinates), _pandas_ (for easier dataframe processing), _BeautifulSoup_ (web scraping utility) and _robotexclusionrulesparser_ (parsing robots.txt files).
```
pip install -q robotexclusionrulesparser lat_lon_parser bs4 pandas
```

### Running the Script
The script is an IPython Notebook which can either be run locally on Jupyter Notebook or using Google Collaboratory.

### Sharing and Access Information
    
    
