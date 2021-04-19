---
layout: "post"
title: "Asset Performance Management"
date: "2018-07-23 23:37"
---

## 1. What is it ?
Asset performance management is a set of capabilties. Namely: data capture, integration, visualization and analytics. Tied together with the **primary goal of optimising reliability and availability of physical assets** and/or reducing maintenance cost. However as time and technology progresses we have come to expect systems and application to not only extract from it's ecosysystem. We today expect APM methodology and solutions to contribute to the **optimisation production and product quality too**. Thus forming an integral part of what we at Capgemini have dubbed the Digital Factory Platform.

![APM Elements](https://fprisse.github.io/Digital_for_Industry/images/APM-Solution-Elements.PNG)

Core of the concept is creating a comprehensive view across operations and maintenance, by making use of the same base information and performance metrics. Rather than reporting to each other.

This does not require fully Integrating production management and asset management in terms of business processes and organization. APM when done right does however fascilitate further intergration of activies in the production and maintenance realm.

APM:
- includes the concepts of condition monitoring, predictive forecasting and reliability-centered maintenance (RCM).
- is a manner to run maintenance operations as an intergral part of your daily (production) operations
- is not about *switching* from preventive maintenance to condition monitoring but it aims to *add* **sensory and operational data** to the equasion.

![Capgemini Digital Maturity](https://fprisse.github.io/Digital_for_Industry/images/Digital_Maturity.PNG)

**History:** The methodology and terminology originates mainly from asset intensive continuous process industry with a homogenous product such as upstream oil & gas / electricity production and utilities. Industries where the uptime component was the most important of the OEE equasion.

|   | In context with other Maintenance and Asset Management systems |
| --- | --- |
| APM | APM is designed for data drive decision making and planning to realize safe, reliable, and efficient operation of equipment and  infrastructure |
| EAM | EAM is designed for maintenance execution. A two-way link between the two is key for 1) Using maintenance execution history to gauge likelihood of failure 2) To trigger the creation or re-scheduling of work-orders |
| AIP | Asset investment planning (AIP) AIP takes data on asset condition, maintenance costs, criticality,  budgets and risks, to produce a CAPEX forecast for asset replacement or decommissioning |

## 2. Why is it good ?
In Capital-intensive industries success is for the greater part defined by the balancing act of risk of undesirable events and the cost of preventing them. Today most organizations rely on preventive maintenance regimes and basic monitoring (mostly alarm systems provided by OEM's) for realizing safety, uptime and reliability at acceptable cost. Based on failures specific components may be prioritized for overhauls. Some do even adopt the maintenance and inspections intervals to take into account deviations in load & runtime based on reports provided by operations.

Asset performance management is first and foremost about doing the above in a more data-drive manner and making use of advanced analytics for failure-mode modeling to improve maintenance regimes.

Furthermore: more accurate determination of the likelihood of failure is possible by structurally broadening the scope of real-time data that is taken into account by:
- using load and runtime data from the machines
- adding raw material and product specifications
- relating product quality reporting to machine performance

When well translated into component specific agenda's this allows for (on average) longer intervals for inspections and overhauls AND prevention of undesirable events (failure, contamination or quality issues) by advancing maintenance work when models indicate a heightened likelihood of failure.

| Benefits |
| --- |
| Maximize output, Longer production runs with confidence: Fewer unplanned disruptions due to equipment breakdowns increases your OEE and means you can consistently meet production targets and achieve or exceed revenue goals.|
| Optimize maintenance cycles. Move toward predictive and prescriptive maintenance strategies to address known sources of failure and performance degradation without driving up costs due to just-in-case preventative part replacements. |
| Reduce overall cost of ownership: Drive down maintenance cost due reduced unplanned work, improved sparepart inventory and longer lead times for contracted work |
| Improve root-cause analysis. Advanced analytics, data mining and data visualization tools enable engineers to identify real root causes and develop ideal corrective action plans faster and more effectively.|
| Help comply with regulations: EG: ISO 55001 |

## 3. How does APM work ?
APM is not one *thing*. APM is a set of well **orchestrated capabilities, involving business logic, governance, technology and procured services**

### 3.1  A comprehensive set of cross discipline metrics

For a coordinated effort to balance optimization of production, asset performance, product quality and cost, a shared measure of the most desirable outcome is key.

Image: APM Analystics framework integrated in OEE KPI Tree

![APM_KPI_TREE](https://fprisse.github.io/Digital_for_Industry/images/APM_KPI_TREE.PNG)

*Source: Capgemini Digital Manufacturing - Asset Management Solutions*



### 3.2 Data Model: Collect and make Available

- Cross discipline:
  - Maintenance: WO records, regimes, inspection reports
  - Operations: Performance, raw materials, product specs.
  - Quality Management: Quality reports, rejects
  - Machine data eg. RPM, Amps, vibration
  - Extra sensor data
- Provided in both event as stored format
- Environmental Data

### 3.3 Static data repository : Shared or synchronized
In order for data to be relate-able a foundation of well maintained registry of assets and individual products is needed.
- Asset tree
- As-built documentation
- Asset dependency tables

Good thing about running real live data through these registries is that faulty entries become very apparent. In fact there are APM solution providers that have (partly) automated the work flow for correcting anomalies.

### 3.4 A predictive analysis workbench to flesh out complex relations
- Tools to build predictive models
- Correlation, regression & clustering
- Exportable probability models

Image: Example of analytical toolbox - IBM - Predictive Solutions
![Example of Analytical Toolbox by IBM](https://fprisse.github.io/Digital_for_Industry/images/IBM_prescriptive_Maintenance.PNG)

*Source: IBM Cloud: Predictive Solutions*



### 3.6 Asset Health Dashboard

- Health: Likelihood of Failure (incl. forecast)
- Criticality: Impact of failure or other undesirable event
- Display geographic dispersion of assets



Image: Example of asset health dashboard - Capgemini APM on MS-Azure
![Example asset Health dashboard](https://fprisse.github.io/Digital_for_Industry/images/CapgeminiAPM5.PNG)

*Source: Capgemini Smart Assets Solutions*



### 3.7 Reporting and publishing Tools

- Customizable templates
- Web-based & interactive
- Distributable format

### 3.8 Model implementation (real-time analysis & alarms)
- Score: Asset health (LOF)
- Act on events: Alarms & notifications
- Attribution of alarms to relevant discipline
- Create events: workorders & re-scheduling

### 3.9 Advanced analytics capability
- Platform & application governance
- Multivariate analysis skills
- Procured training & specialist support



Image: Example of Advanced analytics support framework - Capgemini Consulting
![Advanced Analytics Capabilities](https://fprisse.github.io/Digital_for_Industry/images/Data_Capabilty.PNG)

*Source: Capgemini Consulting - Insights & Data 2017*

### 4.0 Connectivity

- Performance management systems (OEE, Product data & Quality)
- EAM (Maintenance planning & execution)
- Machine bus
- IoT sensors
- Environmental data (API)

Image: Example of sensoring and connectivity solution - "Smart Knob"  - Sogeti High Tech
![Sogeti Smart Knob](https://fprisse.github.io/Digital_for_Industry/images/Smart_Knob.PNG)



## 5.0 Extra: IOT Agenda:
As the APM dashboard provides such a broad view it is a very appropriate starting point for pinpointing for determining where adding datasources will have the most value. Thereby setting the priorities for an IOT agenda based on a balanced view upon opeartional and asset management priorities

IoT is a gamechanger especially for older assets: whereas intergrating and acting such a wide breadth of data and cross-discipline was deemed to be only realistic for companies with newer facilities now the upgrading of sensors and such has become a relatively small investment

## 6.0 What makes it hard ?
- imperfection (at start) of base data such as asset registries
- Choosing the right level of detail
- Making it work as a management tool AND making it work at shop floor level
- Must produce a plan/agenda /schedule for people to act upon

It thus requires a mix of

1. top down standard
2. bottom up analytics & learning exercises
3. Networked development

### 6.1 Critical success factors
- Approach: non isolated approach: part of the concept
- A structured manner to deal with inconsistency
- Tooling: use available data first
  - reported input such as visual inspections
- Must track execution
- Take on board wide breadth of newly available information without throwing the basis overboard
  - preventive maintenance
  - work-order optimization
- Joint performance metrics:
  for a coordinated effort to balance optimization of production, asset performance, product quality and cost, you had better have a shared measure for these
- Make data relate-able
  - Time stamped performance data
  - Track-able materials & product
  - Shared static data
- Should not only integrate but also allow itself to be integrated:
  This is where most ready made solutions fall short

## 7.0 Links
[Comparison Chart for APM Offerings][24033b3f]

  [24033b3f]: https://github.com/fprisse/Digital_for_Industry/raw/master/_includes/APM_Solutions_Rated.xlsm "Click to download chart"
