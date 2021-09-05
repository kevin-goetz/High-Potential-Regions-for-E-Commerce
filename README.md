# High-Potential-Regions-for-E-Commerce

## Description

### What

### How

### Why


## Skills
Technical skills learned in this course are:
- Web Scraping (urllib, Requests, BeautifulSoup)
- Foursquare API (Developer Account)
- Geocoding (Geocoder)
- Data Cleaning & Preprocessing (Pandas, re, NumPy, Scikit-learn)
- Data Visualization (Matplotlib, Folium)

## Requirements
The values you are prompted for are:

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
The biggest possibility for this project is the national census 2022 in Germany. This data will include area, population by age and gender and zipcode addresses that are the most accurate and up to date. Especially the demographic splits for the local population data are a huge opportunity for every retail companies, that can then tailor their definition of potential so sex and age and get a more accurate picture of the high potential regions.

## more Infos
This is just a short README. I have written a full project report that entails all the details of what, why and how + some discussion and outlook.

You can find it here: [Project Report]()

## 📫 Let's connect and learn from each other:

[<img src="https://github.com/kevin-goetz/kevin-goetz/blob/main/LinkedIn Logo.png" height="40em" align="center" alt="Connect with Me on LinkedIn" title="Connect with Me on LinkedIn"/>](https://linkedin.com/in/kgötz) [<img src="https://github.com/kevin-goetz/kevin-goetz/blob/main/Codewars Logo.svg" height="40em" align="center" alt="Connect with Me on Codewars" title="Connect with Me on Codewars"/>](https://www.codewars.com/users/kevin-goetz)


