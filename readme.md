# Mobile Backend for Bluemix
[![](https://img.shields.io/badge/bluemix-powered-blue.svg)](https://bluemix.net)
[![](https://img.shields.io/badge/mobile-app%20builder-orange.svg)](https://bluemix.net/catalog/services/mobile-app-builder/)

### IBM Mobile App Builder Store Catalog Backend
The Store Catalog Mobile Backend uses an  **API Connect** Node.js runtime with the **Cloudant NoSQL DB**, **Object Storage**, **Mobile Client Access**, **Push Notifications**, and **Mobile Analytics** services on Bluemix. The template exhibits common architectural design patterns that developers can use to model their backend on Bluemix for mobile applications. This backend has been created to support the [new](https://developer.ibm.com/bluemix/2016/05/03/mobile-app-builder-now-available/) IBM Mobile App Builder Store Catalog template. It has the the ability to browse a list of products and supports the viewing of images for each item in the product list.

The backend uses the following IBM Bluemix services and runtime:

**Runtime**
* **API Connect** for a single point of REST integration using Loopback with Node.js

**Services**
* **Cloudant NoSQL DB** to hold a list products in a NoSQL database
* **Object Storage** to store product images
* **Mobile Client Access** for protecting resources using authentication
* **Push Notifications** for sending notifications to customers
* **Mobile Analytics** for monitoring trends and performance of the application

### Data architecture
<img src="readme/data.gif" alt="backend architecture" width="400px"/>

## Configuring the Backend

The backend can be easily installed using the **bluegen** command line tool. This CLI tool logs you into Bluemix and prepares the backend services for use. It automatically provisions the services and populates them with the test data required to get up to speed quickly.

### Before you begin
Ensure that you have:

* The [Cloud Foundry CLI tool](https://github.com/cloudfoundry/cli) installed
* The [API Connect CLI tool](https://www.npmjs.com/package/apiconnect) installed by typing the command:

	`npm install -g apiconnect`
* The [Bluemix Generator CLI tool](https://www.npmjs.com/package/bluemix-generator) installed by typing the command:

	`npm install -g bluemix-generator`

> **Note:** Currently the **Object Storage** service is not available in the Sydney, so this template is not operable in that region

### Create your backend from this template

1. First, clone this project into your working directory:

	`git clone https://github.com/ibm-bluemix-mobile-services/appbuilder-storecatalog-backend.git`

2. Run the following command in the root directory of your cloned project. This will create the required services on Bluemix and populate them with the necessary test data:

	`bluegen`

3. Navigate to your newly created projects folder.
4. Upload your **API Connect** backend to Bluemix by typing these commands:

	`cf login [-a API_URL] [-u USERNAME] [-o ORG] [-s SPACE]`

	`cf push`

5. If you want to configure or extend your backend you can edit the API configuration locally by running the commands:

	`npm install`

	`apic edit`

6. Redeploy data to **Cloudant NoSQL DB** and **Object Storage** by running this command in your project directory:

	`bluegen`

### License
This package contains sample code provided in source code form. The samples are licensed under the Apache License, Version 2.0 (the "License"). You may obtain a copy of the License at http://www.apache.org/licenses/LICENSE-2.0 and may also view the license in the license file within this package.
