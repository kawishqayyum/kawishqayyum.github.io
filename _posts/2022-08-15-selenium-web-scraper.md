Extract tabular data behind authentication using `selenium`, process it, and push it to `snowflake`.

### Libraries:
1. `selenium`
2. `pandas`
3. `snowflake`
4. `sqlalchemy`

## Workflow

This is the basic workflow. All of the following steps are automated using a selenium webdriver.

> Disclaimer The sensitive information is redacted for privacy reasons. 

1. Enter login credentials to the website:
![login](/assets/img/selenium-web-scraper/images/login.png)

2. Once logged in, the website displays a list of stores. For every store click the second button (refer to the image below)
![stores](/assets/img/selenium-web-scraper/images/listing.png)

3. Clicking the button in 2, leads you to this page (image below). On this page, expand all the listings:
![past-sales](/assets/img/selenium-web-scraper/images/past-sales.png)

4. Once expanded, there are a total of 5 tables (Table #1, Table #2, etc.). Extract all these tables. 
![past-sales-expanded](/assets/img/selenium-web-scraper/images/past-sales-expanded.png)

5. Then click on the the three red buttons (labeled 1, 2, 3) and you will a bunch of other tables. Extract all these tables as well.
![three-buttons](/assets/img/selenium-web-scraper/images/three-buttons.png)

6. The above data is extracted in a `pandas` `DataFrame` for further processing and finally pushed to `snowflake`.
