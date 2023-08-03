# Indian Companies-NSE BSE

NSE BSE companies is a part of Indian companies which is one of the domains, which is a part of the IndicWiki Project.

## Description

The aim of this domain is to create a large number of articles (about 4060) about BSE NSE companies. Hence, we are generating these data-rich articles in telugu for about 4060 companies, and uploading them to wikipedia, so that people who can read only in their native language (here, telugu) can benefit from this information.

## Installation and setup

Create virtual environment in the project folder using the following commands.

```bash
pip install virtualenv
pip install python3.9 
virtualenv -p python3.9 env
```

After the successful creation of virtual environment (venv), clone the repository or download the zip folder of the project and extract it. 

requirements.txt comes along with the Project Directory.

## Guide to generate XML dump, articles for different Companies

- Clone the repository into the local system.
- Open the notebook file XMLgen.ipynb, Configure `From_n` and `To_n` variables then Execute the notebook by clicking on "Run all", where `From_n` and `To_n` correspond to the row numbers of the first and last desired articles (only serial order is possible). For example `From_n = 30` and `To_n = 50` would generate xml dump for companies in rows 30-50 (inclusive). By default, dump is generated for all companies (case where no mdifications are done).
- On executing the above Notebook xml dump is obtained in `xml files`. If `From_n` and `To_n` were modified then the file name would be birds_{From_n}-{To_n}.xml, names of these files would have the range passed in their filenames (such as `top5_company.xml` etc).

## Github Structure

- The indian-companies-bse-nse (root) folder contains files as
  - requirements.txt  → python requirements file
  - data   → nse bse companies data
  - xml files   → the xml dump for all birds
  - templates   → the jinja template for article generation
  - python files   → python files for gathering,cleaning ect.
  - render.ipynb   → to render the article
  - XMLgen.ipynb   → to render the article

### data

> Github folder Link: <https://github.com/LavanyaGajulapalli/indian-companies-bse-nse/tree/master/data>

- This folder contains various datasets (final and intermediate), and the implementations as to how they were obtained. 
  - _final_wiki_71.xlsx_  → This is a csv file containing all the data related to nse bse companies present in wikipedia.
  - _nonwiki_8.xlsx_  → This is a csv file containing all the data related to remaining nse bse companies.
 
### scrape_new_data

> Github folder Link: <https://github.com/LavanyaGajulapalli/indian-companies-bse-nse/tree/master/python%20files>

- This folder also contains the code used to scrape the data from different websites.
  - infoboxscrapper.ipynb   → This is a python file used to scrape infobox of companies present in wikipedia, Tools used is Selenium. [wikipedia.org](https://www.wikidata.org/)
  - wikipedia url scrapper.ipynb  → This is a python file used to scrape the wikipedia url of the companies. [wikipedia.org](https://www.wikidata.org/)
  - wiki_qidscrapper.ipynb   → This is a python file used to scrape qid of companies present in wikipedia, Tool used is selenium [wikipedia.org](https://www.wikidata.org/)
  - incorpdatescrapping.ipynb   → This is a python file used to scrape the incorporation date of companies,Tool used is Selenium. [zaubacorp.com](https://www.zaubacorp.com/)  

### Translation

> Github folder Link: <https://github.com/LavanyaGajulapalli/indian-companies-bse-nse/blob/master/python%20files/translation.ipynb>
- this file is used to translate the data for all the data

### Template

> Github folder Link: <https://github.com/LavanyaGajulapalli/indian-companies-bse-nse/tree/master/templates>

- This folder .
  - _company.j2_  → This file consists of the improved template to generate wikitext provided a companies's data, corresponding to latest dataset
