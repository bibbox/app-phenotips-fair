# phenotips-fair BIBBOX application

This container can be installed as [BIBBOX APP](https://bibbox.readthedocs.io/en/latest/ "BIBBOX App Store") or standalone. 

- after the docker installation follow these [instructions](INSTALL-APP.md)

## Standalone Installation 

Clone the github repository. If necessary change the ports in the environment file `.env` and the volume mounts in `docker-compose.yml`.

```
git clone https://github.com/bibbox/app-phenotips-fair
cd app-phenotips-fair
docker-compose up -d
```

The main app can be opened and set up at
```
http://localhost:8010
```

## Install within BIBBOX

Visit the BIBBOX page and find the App by its name in the Store. Click on the symbol and select Install. Then fill the parameters below and name your app click install again.

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
### bibbox/phenotips Conatiner
  - *./data/phenotips/extapi:/project/src*
### mariadb Conatiner
  - *./data/var/lib/mysql:/var/lib/mysql*
### jupyter/datascience-notebook Conatiner
  - *./data/jupyter/home/jovyan/work:/home/jovyan/work*
### fairdata/fairdatapoint Conatiner
  - *./data/application.yml:/fdp/application.yml:ro*
### mongo Conatiner
  - *./data/mongo/data:/data/db*
### metaphacts/blazegraph-basic Conatiner
  - *./data/blazegraph:/blazegraph-data*
