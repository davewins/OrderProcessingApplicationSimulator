# Order Processing Simulator

This repository contains the **Order Processing Simulator** application, built using **TIBCO BusinessWorks** for deployment into the **TIBCO Platform**. This application serves as a driver for the companion [Order Processing Application](https://github.com/davewins/OrderProcessingApplication), automatically invoking its REST API endpoints to generate traffic and demonstrate various platform features like **Observability**, **Tracing**, and **Logging**.

---

## Table of Contents

* [Overview](#overview)
* [Features](#features)
* [Simulations](#simulations)
* [Setup and Deployment](#setup-and-deployment)
* [Configuration](#configuration)
* [Logging and Monitoring](#logging-and-monitoring)
* [Contributing](#contributing)
* [License](#license)

---

## Overview

The Order Processing Simulator is designed to continuously interact with the Order Processing Application by sending automated requests to its REST APIs. This allows users to observe the behavior of the Order Processing Application within the TIBCO Platform environment, particularly focusing on how platform features track and display application activity.

The simulator will start and then send a new request to one of the Order Processing Application's endpoints every second.

---

## Features

* **Automated API Invocation:** Automatically calls the REST endpoints of the Order Processing Application.
* **Traffic Generation:** Continuously generates requests to simulate real-world usage patterns.
* **Platform Demonstration:** Designed to showcase the Observability, Tracing, and Logging capabilities of the TIBCO Platform in conjunction with the Order Processing Application.

---

## Simulations

The simulator uses pre-defined, fictitious data for its requests (e.g., customer IDs, product details). These values are for demonstration purposes only and do not require specific real-world data to function.

---

## Setup and Deployment

### Prerequisites

* **TIBCO BusinessWorks Container Edition capability**: Deployed in your TIBCO Platform Dataplane.
* **TIBCO BusinessStudio**: Downloaded and installed from the TIBCO Platform.
* **Order Processing Application**: The companion Order Processing Application must be deployed and running within your TIBCO Platform Dataplane, as this simulator will interact with its exposed REST endpoints.

### Building and Deploying the Application

You have two primary options for building and deploying this application:

1.  **Build `.ear` file using BusinessStudio:**
    * Open the project in **TIBCO BusinessWorks Studio**.
    * Perform a "Clean and Build" of the project to ensure all dependencies are resolved.
    * Export the application as a `.ear` file. You will then manually deploy this `.ear` in the next step.

2.  **"Push to Platform" for Direct Deployment:**
    * Within **TIBCO BusinessWorks Studio**, utilize the "Push to Platform" option. This will directly build and deploy the application to your configured TIBCO Platform environment. If you choose this option, you can skip the "Deployment to TIBCO Platform" section below.

### Deployment to TIBCO Platform

*This section is only necessary if you chose Option 1 (building the `.ear` file) in the "Building and Deploying the Application" step above.*

1.  Log in to your **TIBCO Platform** and navigate to the appropriate Data Plane where you wish to deploy the application.
2.  Use the Platform's deployment tools to create a new BusinessWorks application.
3.  Upload the `.ear` file built in the previous step.

From this point, the configuration of the application properties is the same regardless of whether you deployed via `.ear` upload or "Push to Platform".

---

## Configuration

There are two critical application variables that need to be configured after deployment to ensure the simulator can communicate with the Order Processing Application:

* `APIHost`: Set this to the internal URL (or hostname) of your deployed **Order Processing Application**. This is typically an internal service URL within your TIBCO Platform data plane.
    * *Example:* `orderprocessing-app.your-namespace.svc` (replace `your-namespace` with the actual namespace/domain of your Order Processing Application).
* `APIPort`: Set this to `8080`, which is the standard port for the exposed REST services of the Order Processing Application.

---

## Contributing

Contributions are welcome! If you find a bug or have an improvement, please open an issue or submit a pull request.
