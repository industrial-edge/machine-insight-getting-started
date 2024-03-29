# Machine Insight application example

This guide shows how to use the Industrial Edge application Machine Insight.

- [Machine Insight application example](#machine-insight-application-example)
  - [Description](#description)
    - [Overview](#overview)
    - [General task](#general-task)
  - [Requirements](#requirements)
    - [Prerequisities](#prerequisities)
    - [Used components](#used-components)
    - [TIA Project](#tia-project)
  - [Configuration steps](#configuration-steps)
  - [Usage](#usage)
  - [Documentation](#documentation)
  - [Contribution](#contribution)
  - [Licence and Legal Information](#license-and-legal-information)
  

## Description

### Overview

The application Machine Insight is a condition monitoring application which enables easy and efficient remote diagnosis of the machines. It provides global comprehensive view of assembly lines and machines and provides transparency about your machine to improve your service processes.

The Machine Insight application enables you to extract the data from the different sources. The data may be of different types: device status data, machine status data, alarms, diagnostic buffer data, and program changes or firmware updates on PLC.

This repository describes how to display important PLC data such as alarms or device status in Machine Insight.

![Overview](docs/graphics/Overview.png)

### General task

The guide shows how to use the Machine Insight Configurator for configuring the data exchange with a PLC. Data collection can be configured either for alarms or for diagnostic buffer. Furthermore a status mapping is created to collect machine status data. The data comes in via the S7 Connector and then published on the Databus, where the Machine Insight Configurator can retrieve the required data.

Using Machine Insight the PLC data can be visualized and analyzed via a Gantt chart. Here you can see differnet PLC data, e.g. diagnostic buffer data, alarms, device status or firmware updates.

## Requirements

###  Prerequisities

- Access to an Industrial Edge Management (IEM) with onboarded Industrial Edge Device (IED)
- Installed system configurators and apps (see list "Used components")
- Installed apps (see list "Used components")
- IED is connected to PLC
- TIA portal project loaded on PLC
- Google Chrome (Version ≥ 72)

### Used components

- Industrial Edge Management (IEM) V 1.5.2-4 / V 1.11.8
  - Databus Configurator V 2.0.0-5
  - Common Connector Configurator V 1.8.1-4
- Industrial Edge Device (IED) V 1.10.0.-9
  - Databus V 2.1.0-4
  - OPC UA Connector V 1.8.1-6
  - Device Scanner Service V 1.6.0
  - Machine Insight Conifgurator V 1.3.2
  - Machine Insight V 1.3.2
- Industrial Edge App Publisher V 1.10.5
- Docker Engine V 20.10.10
- Docker Compose V 1.28.5
- TIA Portal V16
- PLC: CPU 1515F-2

The **Device Scanner Service** is optional but required for using the scan functionality in Machine Insight Configurator.

The **OPC UA Connector** and the **Databus** are optional but required for using the machine status feature in Machine Insight Configurator.

### TIA Project

The used TIA Portal project can be found in the [miscellenous repository](https://github.com/industrial-edge/miscellaneous/tree/main/tank%20application) and is also used for several further application examples.

## Configuration steps

You can find the further information about the following steps in the [docs](docs/Installation.md)
- Configuration for Device Scanner Service
- Configure PLC Connection (Databus, OPC UA Connector)
- Configure Machine Insight

## Usage

Once the set up is done with the Machine Insight Configurator, you can open the UI of the Machine Insight application.

Select your device in the menu on the left side. In the overview tab you can see a Gantt chart and logbook records. The Gantt chart displays the following data:

- Machine status based on configured status mapping
- Current device status of PLC
- Notification icons (alarm data, user program change, hardware configuration change, firmware update, textlist change, fail-safe program change)

![Machine_Insight_Overview](/docs/graphics/Machine_Insight_Overview.PNG)

> Hint: PLC notifications are collected for every ten seconds and diagnostic buffer data is collected for every minute. Therefore, you may experience a delay in the Gantt chart or in the logbook.

The Gantt chart allows you to zoom in and view e.g. the machine status in detail.

![Machine_Insight_Machine_Status](/docs/graphics/Machine_Insight_Machine_Status.png)

By clicking on 'Legend' within the Gantt chart, you can see all current states.

![Machine_Insight_Legend](/docs/graphics/Machine_Insight_Legend.png)

## Documentation
- You can find further documentation and help in the following links
  - [Industrial Edge Hub]( https://iehub.eu1.edge.siemens.cloud/#/documentation)
  - [Industrial Edge Forum]( https://forum.mendix.com/link/space/industrial-edge)
  - [Industrial Edge landing page]( https://new.siemens.com/global/en/products/automation/topic-areas/industrial-edge/simatic-edge.html)
  - [Industrial Edge GitHub page]( https://github.com/industrial-edge)
  - [Industrial Edge documentation page]( https://docs.eu1.edge.siemens.cloud/index.html)
 
## Contribution
 
Thank you for your interest in contributing. Anybody is free to report bugs, unclear documentation, and other problems regarding this repository in the Issues section.
Additionally everybody is free to propose any changes to this repository using Pull Requests.
 
If you haven't previously signed the [Siemens Contributor License Agreement](https://cla-assistant.io/industrial-edge/) (CLA), the system will automatically prompt you to do so when you submit your Pull Request. This can be conveniently done through the CLA Assistant's online platform. Once the CLA is signed, your Pull Request will automatically be cleared and made ready for merging if all other test stages succeed.
 
## License and Legal Information
 
Please read the [Legal information](LICENSE.md).
