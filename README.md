<!--
SPDX-FileCopyrightText: 2021 IDM Südtirol Alto Adige <info@idm-suedtirol.com>

SPDX-License-Identifier: CC0-1.0
-->

# Webcomponent How To Arrive in South Tyrol 

[![REUSE Compliance](https://github.com/noi-techpark/webcomp-howtoarriveinsouthtyrol/actions/workflows/reuse.yml/badge.svg)](https://github.com/noi-techpark/odh-docs/wiki/REUSE#badges)
[![REUSE status](https://api.reuse.software/badge/github.com/noi-techpark/webcomp-boilerplate)](https://api.reuse.software/info/github.com/noi-techpark/webcomp-boilerplate)

This Webcomponent shows all data from Opendatahub Article Endpoint of type SpecialAnnouncement. Currently there are shown the lGeneral informations on how to arrive in South Tyrol by car, train, bus or with the airplane.....

## Table of contents

- [Usage](#usage)
- [Gettings started](#getting-started)
- [Tests and linting](#tests-and-linting)
- [Deployment](#deployment)
- [Docker environment](#docker-environment)
- [Information](#information)

## Usage

ToDo: Include the webcompscript file `dist/js/widget.js` in your HTML and define the web component like this:

```html
 <odh-howtoarriveinsouthtyrol-widget data-color="#333" data-lang="de"></odh-howtoarriveinsouthtyrol-widget>
```

### Attributes

#### data-color

Color of the Sliderarrows.

Type: string


#### data-lang

Widget Language.

Type: string
Options: "de", "it","en","nl","cs","pl","fr"

#### data-filter

Article Filter.

Type: multiselect
Options: "Airplane", "Train","Bus","Transfers","LocalMobility","Dolomitipasses","TrafficRestrictions"

Articles are listed in the order of the selected tags, unless data-random is set to true, in which case the order is randomized.

#### data-hideaccommodations

Hides Accommodations on Targetarticle if true.

Type: checkbox

#### data-random

Shuffles Articles if true

Type: checkbox

## Customizations

### Use a custom font

Using a custom non standard font.  
For the Placeholder 'Suedtirol' you can add a custom font to your html page and the widget will use it
```html
<style>
		@font-face {
			font-family: 'Suedtirol';
			src: url('./fonts/SuedtirolNext-Regular.woff2') format('woff2');
			font-weight: 300;
			font-display: swap;
		}
	</style>
```

## Getting started

These instructions will get you a copy of the project up and running
on your local machine for development and testing purposes.

### Prerequisites

To build the project, the following prerequisites must be met:

- ToDo: Check the prerequisites
- Node 12 / NPM 6

For a ready to use Docker environment with all prerequisites already installed and prepared, you can check out the [Docker environment](#docker-environment) section.

### Source code

Get a copy of the repository:

```bash
ToDo: git clone https://github.com/noi-techpark/webcomp-howtoarriveinsouthtyrol.git
```

Change directory:

```bash
ToDo: cd webcomp-howtoarriveinsouthtyrol/
```

### Dependencies

Download all dependencies:

```bash
npm install
```

### Build

Build and start the project:

```bash
npm run start:dev
```

The application will be served and can be accessed at [http://localhost:9000](http://localhost:9000).

## Tests and linting

The tests and the linting can be executed with the following commands:

```bash
npm run test
npm run lint
```

Currently there are no tests available.

## Deployment

To create the distributable files, execute the following command:

```bash
npm run build
```

## Docker environment

For the project a Docker environment is already prepared and ready to use with all necessary prerequisites.

These Docker containers are the same as used by the continuous integration servers.

### Installation

Install [Docker](https://docs.docker.com/install/) (with Docker Compose) locally on your machine.

### Dependenices

First, install all dependencies:

```bash
docker-compose run --rm app /bin/bash -c "npm install"
```

### Start and stop the containers

Before start working you have to start the Docker containers:

```
docker-compose up --build --detach
```

After finished working you can stop the Docker containers:

```
docker-compose stop
```

### Running commands inside the container

When the containers are running, you can execute any command inside the environment. Just replace the dots `...` in the following example with the command you wish to execute:

```bash
docker-compose run --rm app /bin/bash -c "..."
```

Some examples are:

```bash
docker-compose run --rm app /bin/bash -c "npm run test"
```

## Information

### Support

For support, please contact [help@opendatahub.com](mailto:help@opendatahub.com).

### Contributing

If you'd like to contribute, please follow the following instructions:

- Fork the repository.

- Checkout a topic branch from the `development` branch.

- Make sure the tests are passing.

- Create a pull request against the `development` branch.

A more detailed description can be found here: [https://github.com/noi-techpark/documentation/blob/master/contributors.md](https://github.com/noi-techpark/documentation/blob/master/contributors.md).

### Documentation

More documentation can be found at [https://opendatahub.readthedocs.io/en/latest/index.html](https://opendatahub.readthedocs.io/en/latest/index.html).

### Boilerplate

The project uses this boilerplate: [https://github.com/noi-techpark/webcomp-boilerplate](https://github.com/noi-techpark/webcomp-boilerplate).

### License

The code in this project is licensed under the GNU AFFERO GENERAL PUBLIC LICENSE Version 3 license. See the [LICENSE.md](LICENSE.md) file for more information.

### REUSE

This project is [REUSE](https://reuse.software) compliant, more information about the usage of REUSE in NOI Techpark repositories can be found [here](https://github.com/noi-techpark/odh-docs/wiki/Guidelines-for-developers-and-licenses#guidelines-for-contributors-and-new-developers).

Since the CI for this project checks for REUSE compliance you might find it useful to use a pre-commit hook checking for REUSE compliance locally. The [pre-commit-config](.pre-commit-config.yaml) file in the repository root is already configured to check for REUSE compliance with help of the [pre-commit](https://pre-commit.com) tool.

Install the tool by running:
```bash
pip install pre-commit
```
Then install the pre-commit hook via the config file by running:
```bash
pre-commit install
```

