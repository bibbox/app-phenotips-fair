# phenotips-fair BIBBOX application

A FAIR Data Point (FDP) helps the app PhenoTips to go FAIR (Findable, Accessible, Interoperable and Rusable).

This container can be installed as [BIBBOX APP](https://bibbox.readthedocs.io/en/latest/ "BIBBOX App Store") or standalone. 

After the docker installation follow these [instructions](INSTALL-APP.md).

## Standalone Installation 

Clone the github repository. If necessary change the ports in the environment file `.env` and the volume mounts in `docker-compose.yml`.
All data for the FDP are set in the docker-compose.yml as enviroment variables for the Jupyter container.
```
git clone https://github.com/bibbox/app-phenotips-fair
cd app-phenotips-fair
docker network create bibbox-default-network
docker-compose up -d
```

The main App can be opened and set up at:
```
http://localhost:8010
```

## Install within BIBBOX

Visit the BIBBOX page and find the App by its name in the store. Click on the symbol and select install. Then fill the parameters below and name your App, click install again.

## Docker Images used
  - [bibbox/phenotips](https://hub.docker.com/r/bibbox/phenotips) 
  - [mariadb](https://hub.docker.com/r/mariadb) 
  - [jupyter/datascience-notebook](https://hub.docker.com/r/jupyter/datascience-notebook) 
  - [fairdata/fairdatapoint](https://hub.docker.com/r/fairdata/fairdatapoint) 
  - [fairdata/fairdatapoint-client](https://hub.docker.com/r/fairdata/fairdatapoint-client) 
  - [mongo](https://hub.docker.com/r/mongo) 
  - [metaphacts/blazegraph-basic](https://hub.docker.com/r/metaphacts/blazegraph-basic) 


 
## Install Environment Variables
  - JUPYTER_TOKEN = 
  - FDP_TITLE = 
  - FDP_DESCRIPTION = 
  - CATALOG_TITLE = 
  - CATALOG_DESCRIPTION = 
  - VERSION = 
  - PUBLISHERNAME = 
  - PUBLISHEREMAIL = 
  - PUBLISHERUID = Unique id of Publisher e.g. ORCID
  - LANGUAGE = Please enter the language of Catalog and Dataset in IRI format. e.g. http://id.loc.gov/vocabulary/iso639-1/en
  - DATASET_TITLE = Please enter the title of the dataset
  - DATASET_DESCRIPTION = Please enter the description of the dataset.
  - THEMES = List of ';' separated IRI's. e.g http://theme.org/theme1;http://theme.org/theme2
  - KEYWORDS = List of ';' separated Keyword. e.g. phenotips;phenotypes;family
  - ISSUED = Please enter time and date of issuing in xsd format (e.g. "2017-11-16T00:00:00Z"^^xsd:dateTime) or Use the keyword 'now'
  - LICENSE = Please enter IRI for License
  - RIGHTS = Please enter IRI for Rights

  
The default values for the standalone installation are:
  - JUPYTER_TOKEN = token
  - FDP_TITLE = fdp title
  - FDP_DESCRIPTION = fdp description
  - CATALOG_TITLE = catalog title
  - CATALOG_DESCRIPTION = catalogue description
  - VERSION = enter version
  - PUBLISHERNAME = publisher name
  - PUBLISHEREMAIL = publisher@mail.com
  - PUBLISHERUID = uid
  - LANGUAGE = language
  - DATASET_TITLE = title of dataset
  - DATASET_DESCRIPTION = dataset description
  - THEMES = themes of dataset
  - KEYWORDS = keywords
  - ISSUED = now
  - LICENSE = enter your licence
  - RIGHTS = define the rights

  
## Mounted Volumes
### bibbox/phenotips Container
  - *./data/phenotips/extapi:/project/src*
### mariadb Container
  - *./data/var/lib/mysql:/var/lib/mysql*
### jupyter/datascience-notebook Container
  - *./data/jupyter/home/jovyan/work:/home/jovyan/work*
### fairdata/fairdatapoint Container
  - *./data/application.yml:/fdp/application.yml:ro*
### mongo Container
  - *./data/mongo/data:/data/db*
### metaphacts/blazegraph-basic Container
  - *./data/blazegraph:/blazegraph-data*

## Hints

•	approx. installation time with medium fast internet connection: 15 minutes
•	initial user/passwordd: Admin / admin
