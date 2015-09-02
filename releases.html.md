---
title: RabbitMQ for Pivotal Cloud Foundry
---

Release notes for [RabbitMQ for Pivotal Cloud Foundry](https://network.pivotal.io/products/pivotal-rabbitmq-service)

### 1.4.3
**Release Date: 29th July 2015**

Features included in this release:

* Updated stemcell to 3026 to resolve CVE-2015-3290

### 1.4.2
**Release Date: 16th July 2015**

Features included in this release:

* Updated HAProxy to latest version in the 1.5.x branch to resolve CVE-2015-3281
* Requires stemcell 3012

**Note:** You may need to upload stemcell version 3012 to your OpsManager installation. [These are available here](https://network.pivotal.io/products/pivotal-cf#/releases/293/file_groups/278)

## Known Issues:

* The `manage` button for your RabbitMQ instance in Apps Manager will not automatically log you into the RabbitMQ Dashboard. You need to press `logout` and then login with your `username` and `password` which can be obtained from inspecting the environment variables for your instance.

### 1.4.1
**Release Date: 6th July 2015**

Features included in this release:

* Support for OpsManager 1.5.x or 1.4.x
* Support for Elastic Runtime 1.5.x or 1.4.x
* Support for HTTPS only environments
* Support for vSphere or AWS Deployments
* Requires stemcell 2989

## Known Issues:

* The `manage` button for your RabbitMQ instance in Apps Manager will not automatically log you into the RabbitMQ Dashboard. You need to press `logout` and then login with your `username` and `password` which can be obtained from inspecting the environment variables for your instance.

## 1.4
**Release Date: 10th April 2015**

Features included in this release:

* Support for multiple availability zones
* Ability to remove HAProxy SPOF
* Ability to configure an external load balancer
* Syslog output from RabbitMQ Nodes
* Queues mirrored to two nodes by default
* Requires OpsManager 1.4.0 and Elastic Runtime 1.4.0 or greater
* Support for vSphere and AWS

**Important:** You may experience a **small window of downtime** during this particular deployment as the cluster nodes are renamed. We recommend that you communicate with your application owners in advance to minimize the impact of this downtime.

Additional known issues:

* On AWS, this version supports deployments in the US-East region. Multi-region support is coming in a future release.
* The experimental HTTPS-only feature in Elastic Runtime 1.5 may cause issues with this version of the product. Full support for HTTPS-only traffic is coming in a future release.

<p class="note"><strong>Note</strong>: BOSH Stemcell 2865.1 is required for installation on Ops Manager 1.5.x and above.</p>

### 1.3.6
**Release Date: 23rd March 2015**

Features included in this release:

* Updated stemcell to 2889 to resolve [these OpenSSL CVE alerts](http://pivotal.io/security/usn-2537-1)

## 1.3.5
**Release Date: 6th March 2015**

Features included in this release:

* Updated version of Jetty to 9.2.9

## 1.3.4
**Release Date: 30th January 2015**

Features included in this release:

* Updated stemcell to 2824 to resolve [CVE-2015-0235 Ghost](http://www.pivotal.io/security/cve-2015-0235)
* Upgraded RabbitMQ version to 3.4.3
* Developers can add policies for their Vhost (instance)
* Admin username and password changes through OpsManager are reflected correctly in RabbitMQ for the admin dashboard
* Bug fix for package dependencies and installation errors
* Bug fix for OAuth integration with UAA
* Bug fix to ensure config changes in OpsManager are correctly reflected in RabbitMQ in a redeployment
* Ability to disable TLS V1.0

## 1.3.3.2
**Release Date: 14th November 2014**

Features included in this release:

* Management dashboard uses a registered route


## 1.3.3.1
**Release Date: 4th November 2014**

Features included in this release:

* Fix for increased RAM usage on the service broker

## 1.3.3.0
**Release Date: 31st October 2014**

Features included in this release:

* Disables SSLv3 to address the POODLE vulnerability

## 1.3.2.2
**Release Date: 27th October 2014**

Features included in this release:

* Corrects installation errors on some Ops Manager versions

## 1.3.2.1
**Release Date: 24th October 2014**

Features included in this release:

* Resolves issue with idle client connections being closed very quickly

### Upgrading from 1.2.0
It is unfortunately **not** possible to upgrade from any prior versions to this tile version or greater.
E.g. from 1.2.0 to 1.3.2.1

This is because tile versions 1.2.0 and earlier use v1 of the Services API, whilst all newer tiles use v2.
The migration between the versions would have being risky and complicated due to the way RabbitMQ was using service names, therefore the decision was taken to not support tile upgrades.

We always aim for tiles to be upgradeable from previous versions where possible.

### Options
We recommend the following:

* Backup any persisted data (if required)
* Stop any applications / services that are publishing to the queues
* Delete the existing 1.2.0 tile
* Deploy the >= 1.3.2.1 tile version
* Restore any data
* Restage any applications to refresh the binding information, as the IPs may have changed

## 1.2.0
**Release Date: 16th May 2014**

Features included in this release:

* RabbitMQ 3.2.4

## 1.1.0
**Release Date: 11th March 2014**

Features included in this release:

* RabbitMQ 3.2.2

## 1.0.0
**Release Date: 22nd November 2013**

Features included in this release:

* RabbitMQ 3.1.5