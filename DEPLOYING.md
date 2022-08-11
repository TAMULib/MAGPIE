<a name="readme-top"></a>
# Metadata Assignment GUI Providing Ingest and Export App Deployment Guide

## Production Deployments

For **production** deployments, deploy using `docker-compose`.
This is the recommended method of deployment for production systems.

Perform the following steps to deploy:

```shell
git clone https://github.com/TAMULib/Directory.git Magpie --recurse-submodules

cd Magpie/

cp example.env .env
cp example.env.client .env.client
cp example.env.service .env.service

# Make any changes to the .env, .env.client, and .env.service files before here.
docker-compose up
```

The **development** deployment may also use `docker-compose` in the same way.

<div align="right">(<a href="#readme-top">back to top</a>)</div>


## Development Deployments

For **development** deployments, deploy using `docker-compose`, `docker`, or using `npm`/`mvn`.

The **development** process using `docker-compose` is identical to the **production** deployment.
The difference may be in how the `.env` files are configured.

The **development** process using `docker` or using `npm` may also be deployed following the steps outlined in the individual repositories:

1. [Metadata Assignment GUI Providing Ingest and Export UI Repo][ui-repo], represented by the `client/` directory.
2. [Metadata Assignment GUI Providing Ingest and Export Service Repo][service-repo], represented by the `service/` directory.

Performing the deployment using `docker` should be something similar to the following:
```shell
git clone https://github.com/TAMULib/Directory.git Magpie --recurse-submodules

# For service:
cd Magpie/service/
docker image build -t service .
docker run -it service

# For client:
cd Magpie/client/
docker image build -t client .
docker run -it client
```

Performing the deployment using `npm`/`mvn` should be something similar to the following:
```shell
git clone https://github.com/TAMULib/Directory.git Magpie --recurse-submodules

# For service:
cd Magpie/service/
mvn clean spring-boot:run

# For client:
cd Magpie/client/
npm install
npm run build
npm run start
```

<sub>_* Note: `-t project` and `-it project` may be changed to another tag name as desired, such as `-t developing_on_this` and `-it developing_o
n_this`._</sub><br>
<sub>_** Note: An additional step may be required, such as deploying alongside a [Weaver UI Core][weaver-ui] instance using [Verdaccio][verdaccio]._</sub>

<div align="right">(<a href="#readme-top">back to top</a>)</div>


<!-- LINKS -->
[ui-repo]: https://github.com/TAMULib/MagpieUI
[service-repo]: https://github.com/TAMULib/MagpieService
[weaver-ui]: https://github.com/TAMULib/Weaver-UI-Core
[verdaccio]: https://verdaccio.org
