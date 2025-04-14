# Scraping CRISPR crops patents, analyzing in Python and visualizing with Illustrator and Scrollama: [Story](https://annikamcginnis.github.io/crispr-crops/)

## Goal
- To understand trends in application and acquisition of CRISPR crops patents
- To create a scrollytelling experience explaining a chart, inspired by [this Reuters piece](https://www.reuters.com/graphics/TEST-TEST/010070HX15H/) 

## Main Findings
- Since CRISPR's invention, public institutions and agribusiness companies in China and the U.S. have led the race to create new types of crops deemed “safer” than traditional genetically modified organisms (GMOs) by many regulatory bodies. Top crops include rice, corn/maize and tomatoes, but applications have been filed for almost 100 different crops.
- From 2013 to April of this year, inventors filed about 1,500 patent applications for CRISPR crops in WIPO. Almost 500 of those applications have been granted by major world patent offices in China, the U.S., South Korea, Russia, Canada and others.
- The U.S.-based Dow Agrosciences, now under Corteva Agriscience, applied for the first crops patent through WIPO in September 2012. But China beat the U.S. to grant the first crop patents, on methods to improve rice yields, in June 2016.
- Since then, Chinese scientists have churned out new inventions at an accelerating pace. By 2016, China overtook the U.S. in annual CRISPR crop patent applications.
- By 2019, Chinese institutions were putting out about 100 or more applications a year- over 40% that were later granted - while the U.S. produced just 20-30 applications per year, less than 30% granted.
- Other countries have also produced CRISPR crops patents, including Germany, South Korea and Russia. In 2023, eight countries including Australia, Canada, Israel and the Netherlands developed gene editing methods for crops.
- While Chinese scientists have filed hundreds more patents related to specific crops like rice and tobacco, U.S. institutions own more general inventions that can be applied to edit the genes of many different crops.
- The U.S. has attempted to globalize its patent ownership, submitting four out of five applications to multiple patent offices. Most Chinese patents, however, are law only in China: The country submits just one out of every 10 applications abroad, although it has ten times more institutions submitting applications than the U.S.
- Chinese patents are granted 2.5 times faster than U.S. patents, at an average of less than two years. Its fastest patent - to develop a drought resistant variety of rice - was granted in just 59 days.
- Major American agribusiness companies are among the top owners for CRISPR crop inventions, including Monsanto Technology (now owned by Bayer) and Corteva Agriscience.


## Data Collection
I scraped the front page of all CRISPR crops patent applications from the [World Intellectual Property Organization PATENTSCOPE Database](https://patentscope.wipo.int/search/en/search.jsf). First, I queried for all patent applications with the following terms on the front page: “CRISPR” AND (“crops” OR “crop” OR “plants” OR “plant” OR “agriculture”). Using the downloaded dataset, I extracted the links from the patent ID column using Google Sheets formulas. Then, I built a scraper that looped through these links to extract all the data from the front page of the patent application in PATENTSCOPE. (https://patentscope.wipo.int/search/en/search.jsf)

Because there were no unique class or ID elements for each field, and each patent contained slightly different fields, the scraped data was not organized in uniform columns. I had to manually rearrange each of the around 1,500 patents' columns in Google Sheets by filtering sub-datasets and comparing the scraped data with the patent pages on PATENTSCOPE, which was a time-consuming process. I merged and conducted further cleaning of the data in Python.


## Data Analysis
I used the following languages, libraries, APIs and models in my data cleaning and analysis: 
- Python
- Playwright
- BeautifulSoup
- Pandas
- OpenAI
- Gemini
- Google Places API
- matplotlib
- ai2html
- Adobe Illustrator
- html, css & d3

I used the Google Places API to search for each patent applicant's location (country, city, and latitude and longitude).
I used the Gemini LLM through the OpenAI library to categorize all crop patents by their type of crop and purpose of editing the crop, using the patents' titles and abstracts. 

I conducted my data analysis in Python using the Pandas library, creating new columns and pivot tables to investigate the applicants, crops, purpose of application, length of time between applications and grants, percentage granted, and other indicators.

I produced a waffle chart using matplotlib showing the applications and grants divided by year and country. In Illustrator, I then produced 9 different versions of this graphic to visualize various components of the data, including the first applied and granted patents, comparison between U.S., China and other countries' patent applications, the number of patents filed in foreign offices, and the type of crops. I produced desktop and mobile versions for each graphic, swiching the horizontal desktop view to vertical for mobile. I used ai2html to make them responsive. 

I used the Scrollama story template and modified the code so that a new graphic would be shown at each step. I also modified the header styling and general styling of the page using HTML and CSS.


## Reflection

This project was challenging on many levels: 1, scraping the data from a non-organized site, which required a lot of manual cleaning that took about a week to complete; and 2) building a waffle chart that would change display as I scrolled. I learned more on how to use Illustrator to develop more creative graphics. However, I know I can still improve my workflows in Illustrator - especially improving how to create multiple charts that require identical placement and sizing. 

I was also able to use the Google Places API for the first time, which pretty accurately detected lat/longs based on place names, compared to the Geocode API. This project also enabled me to bring together a lot of skills from past projects, like categorizing using the Gemini LLM and conducting in-depth analysis using Pandas.

I was able to make my scrolly graphic work by producing 9 different versions of my chart, but I'd like to learn how to do this using d3 or other coding languages.
 
