<a name="readme-top"></a>
[![Service Build Status][service-build-badge]][service-build-status]
[![Client Build Status][client-build-badge]][client-build-status]
[![Service overage Status][service-coverage-badge]][service-coverage-status]
[![Client overage Status][client-coverage-badge]][client-coverage-status]

# Metadata Assignment GUI Providing Ingest and Export App

The *Metadata Assignment GUI Providing Ingest and Export (MAGPIE) App*, consisting of a service back-end and a client front-end, is developed and maintained by [Texas A&M University Libraries][tamu-library].

Using this repository requires loading a submodule, such as one of these methods:
```shell
# Method 1: Checkout with submodule recursion.
git clone https://github.com/TAMULib/Magpie.git Magpie --recurse-submodules

# Method 2: Initialize submodule for already checked out repository.
cd Magpie/
git submodule init
```

<div align="right">(<a href="#readme-top">back to top</a>)</div>


## Deployment

A quick and easy deployment method using `docker-compose` is described in the [Deployment Guide][deployment-guide].

For _advanced use cases_, or when `docker-compose` is unavailable, the use of `docker` or `npm`/`mvn` is also described in the [Deployment Guide][deployment-guide].

Deployment, in general, may look something like this:

```shell
cp example.env .env
cp example.env.client .env.client
cp example.env.service .env.service

# Make any changes to the .env, .env.client, and .env.service files before here.
docker-compose up
```

<sub>_* Note: It may be necessary to disable caching during build by passing `--no-cache` to the `docker-compose up` command._</sub>

<div align="right">(<a href="#readme-top">back to top</a>)</div>


## Additional Resources

- [Contributors Documentation][contribute-guide]
- [Deployment Documentation][deployment-guide]
<!-- - [API Documentation][api-docs]-->

Please feel free to file any issues concerning *MAGPIE App* to the issues section of the repository.

Any questions concerning *MAGPIE App* can be directed to helpdesk@library.tamu.edu.

Copyright © 2022-2025 Texas A&M University Libraries under the [MIT license][LICENSE].

<div align="right">(<a href="#readme-top">back to top</a>)</div>


<!-- LINKS -->
[service-build-status]: https://github.com/TAMULib/MagpieService/actions?query=workflow%3ABuild
[service-build-badge]: https://github.com/TAMULib/MagpieService/workflows/Build/badge.svg
[service-coverage-status]: https://coveralls.io/github/TAMULib/MagpieService
[service-coverage-badge]: https://coveralls.io/repos/github/TAMULib/MagpieService/badge.svg

[client-build-status]: https://github.com/TAMULib/MagpieUI/actions?query=workflow%3ABuild
[client-build-badge]: https://github.com/TAMULib/MagpieUI/workflows/Build/badge.svg
[client-coverage-status]: https://coveralls.io/github/TAMULib/MagpieUI
[client-coverage-badge]: https://coveralls.io/repos/github/TAMULib/MagpieUI/badge.svg

[tamu-library]: http://library.tamu.edu
[api-docs]: https://tamulib.github.io/MagpieService

[deployment-guide]: DEPLOYING.md
[contribute-guide]: CONTRIBUTING.md
[license]: LICENSE
