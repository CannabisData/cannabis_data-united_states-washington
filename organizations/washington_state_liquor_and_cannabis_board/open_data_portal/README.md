## The Washington State Liquor and Cannabis Board Open Data Portal

The [Washington State Liquor and Cannabis Board (WSLCB)](https://lcb.wa.gov/) is tasked with regulating the adult-use cannabis industry in the state of Washington.  In the course of its operations, the WSLCB collects a large amount of public information.  Demonstrating a commitment to transparency and accountability, the WSLCB operates a Socrata-based data portal:
https://data.lcb.wa.gov/

Socrata is a Seattle-based software vendor that services local, county, state, and federal governments.  They offer a turnkey open data portal service called [Publica Open Data](https://socrata.com/publica-open-data/).

### Datasets

The WSLCB Data Portal prominently features a Marijuana Dashboard, a Socrata "Story" composed of several chart-based representations of historical and contemporary data:
https://data.lcb.wa.gov/stories/s/WSLCB-Marijuana-Dashboard/hbnp-ia6v/

All of the view types in the WSLCB Data Portal can be browsed from the web.  The Portal currently features [Datasets](https://data.lcb.wa.gov/browse?limitTo=datasets), [Charts](https://data.lcb.wa.gov/browse?limitTo=charts), [Data Lens pages](https://data.lcb.wa.gov/browse?limitTo=new_view), [Filtered Views](https://data.lcb.wa.gov/browse?limitTo=filters), and [Stories](https://data.lcb.wa.gov/browse?limitTo=story):
https://data.lcb.wa.gov/browse

The WSLCB Data Portal also includes one [external dataset](https://data.lcb.wa.gov/dataset/MJRETAIL/qv2r-d9rj), a geographic information dataset interfaced through an ArcGIS connector which shows the locations of all licensed retail businesses, visually distinguishing licensees which also have a medical marijuana endorsement:
https://www.arcgis.com/home/webmap/viewer.html?url=https://services.arcgis.com/7eDYNwg9LqtJxNLP/arcgis/rest/services/MedicallyEndorsed/FeatureServer/0

*(It's worth noting the currency of this geographic information is uncertain as [the map description](https://services.arcgis.com/7eDYNwg9LqtJxNLP/arcgis/rest/services/MedicallyEndorsed/FeatureServer/0) indicates it was last updated in July 2017.)*

### Exports

You can export data directly from the WSLCB Data Portal in a number of formats: JSON, XML, CSV, CSV for Excel, CSV for Excel in Europe, TSV for Excel, RDF, RSS.  Look for `Export` buttons on the detail screens of individual Charts, Datasets, Data Lenses, and Filtered Views.

### API

Developers can access the WSLCB Data Portal programmatically.  On the browse screen, every Dataset includes a link to `API Docs` which takes one to documentation for that specific API endpoint.  If you're on the Dataset's detail screen, select `API` to access the API endpoint information or link to documentation for that specific endpoint.  From a Chart or Filtered View, select `Export` then `SODA API` to access the API details.

Let's look at an example.  The ["Licensed Businesses" Dataset](https://data.lcb.wa.gov/Licensing/Licensed-Businesses/u3zh-ri66) includes 13 columns of information about every licensed adult-use business in the state of Washington (1,896 rows as of a November 13, 2017 update).  Navigating to [the documentation for the Licensed Businesses endpoint](https://dev.socrata.com/foundry/data.lcb.wa.gov/bhbp-x4eb) we can find the API endpoint itself (https://data.lcb.wa.gov/resource/bhbp-x4eb.json), metadata about the Dataset including its last update timestamp, column metadata, and useful code snippets in several programming languages.

Socrata recommends registering for and sending an [Application Token](https://dev.socrata.com/docs/app-tokens.html) along with all API requests.  If you send a valid App Token as a request header or query parameter, your requests won't be rate limited.  This requires [creating a portable OpenData Socrata profile](https://data.lcb.wa.gov/login) and [registering a new Application](https://data.lcb.wa.gov/profile/app_tokens).  You can then [send the identifier](https://dev.socrata.com/docs/app-tokens.html#using-your-application-token) as an `X-App-Token` request header or `$$app_token` query parameter.

Socrata supports several [official client libraries and endorsed community libraries](https://dev.socrata.com/libraries/).  I'm most interested in Python these days, and Socrata recommends using [xmunoz](https://github.com/xmunoz)'s [`sodapy` client](https://github.com/xmunoz/sodapy) that's built on top of [Kenneth Reitz](https://www.kennethreitz.org/)'s [Requests package](https://github.com/requests/requests/).

### Code

We'll take a look at what you can do with the WSLCB Data Portal API endpoints using Jupyter Notebooks:

* Dataset: [Licensed Businesses](./wslcb-portal-licensed_businesses.ipynb)
