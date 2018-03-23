# Bento Compose

Docker compose project uses a docker-compose.yml for local development of jhu_bento. 
The following services are created
- solr:  Search indexs for catalog, and libguides
- lara:  Ruby on Rails API 
- mysql: Used by Lara RoR app

Assumes a  prepopulated data directory used by solr, and mysql

Assumes a populated .env file, used by docker compose 
- see the dotenv-example file

The lara, and jh_bento git projects are sub_modules of this project
