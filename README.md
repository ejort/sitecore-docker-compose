# Sitecore with Docker Compose

Some bits I put together to spin up an OOTB Sitecore site using Docker Compose to create a container for each of it's dependencies - asp.net/iis, sql server and mongodb.

Could definitely be made better, but it works :)

## Setup

1. Clone / download repo
2. Download Sitecore distribution
3. Unzip as *Sitecore* in root of repo
4. Copy license.xml into Sitecore\Data
5. Copy web\Connectionstrings.config -> Sitecore\Website\App_Config
6. Copy web\z.DockerConfig.config -> Sitecore\Website\App_Config\Include


## Usage

    docker-compose up

This will start 3 services:

* **web** - asp.net container with 2 volumes mapped from the host
 * .\Sitecore\Website -> c:\site
 * .\Sitecore\Data -> c:\site-data

* **mssql** - sql server 2016 express container with 1 mapped volume mapped from host with db files
 * .\Sitecore\Databases -> c:\dbs

* **mongo** - mongodb container
