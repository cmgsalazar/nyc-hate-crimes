# Jews, Asians, gays most targeted for hate crimes: NYPD data

For my first final project for the Lede Program, I wrote about hate crimes in New York City. I initially found and downloaded datasets from the [Federal Bureau of Investigation (FBI)](https://cde.ucr.cjis.gov/LATEST/webapp/#/pages/explorer/crime/hate-crime), but the data cover only up to 2022. 

When I found more updated crime reports from the [New York Police Department](https://www.nyc.gov/site/nypd/stats/reports-analysis/hate-crimes.page), I decided to use those instead. 

## Process

`scraper.ipynb` — I began by scraping the webpage through `BeautifulSoup` and download only `.xlsx` files. The source code did not use `class` and `id` attributes, so I ran conditionals and loops.

The datasets are under the folder `downloaded-datasets`.

`wrangler.ipynb` — I did cursory previews of each file before deciding on a final topic for this project: **hate crimes according to bias motivation**. I had the option to work with the data either by quarter or by year, and preferred the former for a more nuanced analysis (e.g., anti-Asian incidents during Covid-19, anti-Jewish incidents at the onset of the Israel-Hamas war).

Observed issues during this part of the process: 
* unnecessary rows that contain text as title and description of the dataset
* blank bottom rows that were not part of the actual dataset; and
* inconsistent order, capitalization, and naming conventions of columns.

Using `pandas`, I ran each dataframe (quarterly data) to take only the row showing total reported incidents and merge that to another dataframe. Throughout the process, I had to `drop` unnecessary rows and columns, change strings to lowercase and `strip` leading and trailing spaces for consistency, `rename` columns, and `concat` to combine dataframes.

`viz.ipynb` — Using `matplotlib`, I visualized trends based on the data, then saved charts to `.svg` for polishing in Adobe Illustrator. 

For a last-minute decision to add a pie chart showing total hate crimes per category, I used Datawrapper. 

Read the story here: [Jews, Asians, gays most targeted for hate crimes: NYPD data](https://cmgsalazar.github.io/lede/nyc-hate-crimes/)

## Why this matters to me

During my first (and so far, only) visit to New York in 2022, a friend warned me against discrimination and physical attacks because I looked undoubtedly Asian. I was told to be on my toes at all times and to stand away from the edge of railway platforms to avoid being pushed. 

While the Philippine consulate in New York [reported](https://www.pna.gov.ph/articles/1223583) that pandemic-fueled hate crimes against have now dwindled, Filipinos still ranked third among Asians who experienced hate incidents and crimes, according to a 2021 study.

Just a few days ago, a 74-year-old Filipina died in California after a homeless man shoved her onto a moving train. _Was it considered a hate crime?_ No one can say for sure. But the thought made me look into crime statistics and led me to this project. 

Similarly, my mother is based in Israel and I have several LGBTQ+ friends. I was curious to see whether in a city known to be multicultural and diverse, hate crimes due to religious affiliations, gender identities, and race and ethnicity still persist.

Apparently so.