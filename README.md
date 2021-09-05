# High-Potential-Regions-for-E-Commerce

## Description

### What
This Data Science project is an analyses of the sales & marketing potential of german regions for E-Commerce companies. It uses a combination of relative population density & relative retail density to combine those two KPIs for a final measure of potential. Regions with a high potential are then visualized in an interactive Folium plot.

### How
You can find the long version of "how" here: [**Project Report**]() <br />
The data was collected from 4 (2 Web Scrapings, 1 Geocoding, 1 Foursquare API) different sources, then cleaned & combined and finally the KPIs were computed and the geolocation data visualized.

**1. Data Collection:**
- **Web scraping Zipcode Information**:<br />The basis of the analysis are locations which are identified by zipcode, city, quarter, district and region. The data was collected from the website “https://home.meinestadt.de”.
- **Web scraping Wikipedia**:<br />Wikipedia was used to gain insights about the population and area of the location. In a first step a search string consisting of the zipcode and the quarter name was concatenated with the Wikipedia search URL having the settings on “Sort by most relevant”. In a second step the result page was crawled for the first entry’s URL and this URL was then requested to get to the Wikipedia page of the quarter, city or village (depending on the data).
- **Geocoding the locations**: <br />The distance to retail shops can only be computed (Step 4) when the location data is enriched with coordinates. The library “Geocoder” and an OpenStreetMap API were used to obtain the latitude, longitude and the bounding boxes.
- **Adding the Retail Information**: <br />As a last step for the data collection the Foursquare Developer API (“Personal” account) was used to map Fashion Retail Shops with their distance to the location data. The Foursquare API therefore uses the Latitudes and Longitudes from the previous step and returns all the stores’ names, categories, sub-categories, latitudes and longitudes and distance to the requested location in a user-defined circumference. The circumference (or radius = r) was computed for every location while looping through coordinates for API-requests, applying the formula “A = π r2” where A is known from the crawled Wikipedia pages and π (pi) is a constant: r = np.sqrt(A / π).
<br />

**2. KPI Computation:**
-	**population density**:<br /> A float computed from the Wikipedia info on population and area. Population divided by area is the population density.
-	**retail density**:<br /> A float computed from the Foursquare info on the shop count within the predefined radius divided by the Wikipedia info on the locations area. The complement of retail density (retail sparsity = 1 – retail density) is later used to compute the potential correctly.
- **potential**:<br /> The potential is a combination of the previous two variables and was computed as following: 1/2 * (normalized(population density) + (normalized(retail sparsity)).

**3. Visualization with Folium:**



### Why
With the lifting of the corona restrictions in Germany the e-commerce companies no longer have the “monopoly” on shopping and the competition gets more balanced again. The e-commerce industry needs to find strategies to keep up the momentum and not lose their newly gained customers.

A possible lever for customer retention and customer acquisition could be a geographical analysis of the retail landscape and population. Assuming that consumers with sparse shopping options in their area are more likely to order online, this project aims to find regions within Germany that have a high population density as well as a low retail density. If an e-commerce company is focusing their marketing strategies towards those regions it may uplift their ROI.

## Skills
Technical skills honed in this project are:
- Web Scraping (urllib, Requests, BeautifulSoup)
- Foursquare API (Developer Account)
- Geocoding (Geocoder)
- Data Cleaning & Preprocessing (Pandas, re, NumPy, Scikit-learn)
- Data Visualization (Matplotlib, Folium)

## Requirements
Installed modules:

| Library            | Version |
| :---               | --- |
| sys (Python)       | 3.9.1 | 
| pandas             | 1.2.5 | 
| numpy              | 1.21.0 | 
| re                 | 2.2.1 |
| sklearn            | 0.24.2 |
| json               | 2.0.9 | 
| requests           | 2.25.1 | 
| bs4                | 4.9.3 |
| folium             | 0.5.0 |
| matplotlib         | 3.4.1 |
| geocoder           | 1.38.1 |

## Personal Learnings
Some websites block python scripts that try to scrape them (read the /robots.txt from the scraped site first and always obey to the legal rules!) but you can bypass those errors when you don't exceed rate limits (time.sleep(np.random.uniform(0,2)) and when you tell the server that you are a browser (Request-headers: headers = {'User-Agent': 'Mozilla/5.0 (Windows NT 6.1)'}). In the end the scraped data is mostly really messy and it is a good practice to check some of the scraped sites by hand to determine if the correct data was picked by your algorithm. The most tricky thing is not that the scraping throws NULL values or error messages at you, it is that it gets you data but you don't know for sure if it is the correct one ("Is this region really that big or did the algo scrape the wrong information?").

I also learned that just because you standardize or normalize the data doesn't mean that the resulting variables are not skewed. Outliers can still influence a StandardScaler() or MinMaxScaler() so you have to find those outliers and inspect them for plausibility before even considering to delete them. Not all outliers are false data.

Most of the challenges that make up a good project appear when you are already deep in it and think you are nailing it. That makes it hard to estimate how much time you need for certain tasks; there is always the next error message waiting for you :-) And even if there are not Errors, there are still some things that seemed to be fine in ttheory but when you think about them from a programming point of view and disect the problem with code, you sometimes have to be quiet creative to find new solutions. In that case it is extremely important to document all your decisions - not only what you did, but also **WHY** you did it! Writing a project report besides the comments in your code definitely helps.

## Outlook
The biggest possibility for this project is the national census 2022 in Germany. This data will include area, population by age and gender and zipcode addresses that are the most accurate and up to date. Especially the demographic splits for the local population data are a huge opportunity for every retail company, that can then tailor their definition of potential to sex and age and get a more accurate picture of the high potential regions.

## more Infos
This is just a short README. I have written a full project report that entails all the details of the process + some discussion and outlook.

You can find it here: [**Project Report**]()

## 📫 Let's connect and learn from each other:

[<img src="https://github.com/kevin-goetz/kevin-goetz/blob/main/LinkedIn Logo.png" height="40em" align="center" alt="Connect with Me on LinkedIn" title="Connect with Me on LinkedIn"/>](https://linkedin.com/in/kgötz) [<img src="https://github.com/kevin-goetz/kevin-goetz/blob/main/Codewars Logo.svg" height="40em" align="center" alt="Connect with Me on Codewars" title="Connect with Me on Codewars"/>](https://www.codewars.com/users/kevin-goetz)


