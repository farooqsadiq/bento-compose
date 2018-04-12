# Bento Compose

Docker-compose project uses a docker-compose.yml for local development of the jhu_bento project, and its dependencies.

The following services are created
- solr:  Search indexs for catalog, and libguides
- lara:  Ruby on Rails API
- mysql: Used by Lara RoR app

## Additiional manual configuration
Prepopulated *data* directory used by solr, and mysql

Populated .env file, used by docker compose
- see the dotenv-example file

The lara, and jh_bento git projects are sub_modules of this project hence you have to use the --recursive flag when you clong the bento-compose project.

## Using this project in development

In a terminal
```
\# Clone the repository and sub modules lara, jhu_bento
git clone --recursive https://github.com/farooqsadiq/bento-compose.git

\# Go into the directory
cd ~/Documents/Projects/bento-compose

\# Make sure you have an .env file (see LAG team)

\# Start the docker containers (starts solr, mysql, and lara)
\# This will also build the containers.
docker-compose up -d
```

- The containers are running in Docker - Kitematic
  solr: http://localhost:8983/solr
  mysql: localhost:33306 (use mysqlworkbench)
  lara: http://localhost:3000
- Change directory into the jh_bento directory
  cd  ~/Documents/Projects/bento-compose/jhu_bento
- Add a .env file in the jh_bento directory
  You will need to get this from LAG
- Install node and yarn
  brew upgrade; brew install node yarn
- Build and Start the jh_bento, which is a node application
  yarn start

Note in Atom you can install the gitplus package which enables you to run git commands from within the editor. See https://www.youtube.com/watch?v=7Id1_VfbEKo

In Atom Cmd+Shift+p and search for gitplus commands

## Maintaining the submodules
