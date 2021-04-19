---
layout: "post"
title: "Machine Learning for Applications in Manufacturing"
author: "Michal Romaniuk and Barbara Rutkowska (deepsense.ai)"
publication: "blog.deepsense.ai"
date: "2017-02-17"
---

Modern manufacturing technology is starting to incorporate machine learning throughout the production process. Predictive algorithms are being used to plan machine maintenance adaptively rather than on a fixed schedule. Meanwhile, quality control is becoming more and more automated, with adaptive algorithms that learn to recognize correctly manufactured products and reject defects. In this post we look at some recent advancements in industrial applications of machine learning, including the work of our Machine Learning Team at deepsense.ai.
Predictive maintenance

The computerization of industrial machinery is increasing – it’s becoming equipped with numerous sensors and connected to the rest of the factory via Internet of Things (IoT) platforms. Besides passive monitoring, it enables application of predictive monitoring, with machine learning algorithms forecasting equipment breakdowns and scheduling maintenance before they occur. With adaptive maintenance, unplanned downtime and waste due to machinery failure can be reduced.

Predictive maintenance is also expected to become an important technological component of autonomous vehicles. Self-driving cars are likely to follow a service business model (rather than the ownership model of today’s car industry), which means that cars will have to monitor their own condition rather than rely on their owner-driver to spot problems and take the vehicle to a service station.
Quality control

Machine learning is also being adopted for product inspection and quality control. Computer vision algorithms based on machine learning can learn from a set of samples to distinguish the “good” ones from the flawed ones. In particular, semi-supervised anomaly detection algorithms only require “good” samples in their training set, which means that a library of possible defects is not necessary. Alternatively, a solution can be developed that compares samples to typical cases of defects. These technologies have been applied to the inspection of fabrics, solar panels and machined parts.


#### Examples of machine learning applications in manufacturing

Here are some specific cases where machine learning was used to develop new products or improve existing ones:
One of **automotive plants** implemented a predictive maintenance solution for a hydraulic press used in vehicle panel production. Detailed studies of the maintenance process showed that a lot of engineers’ time was consumed by attending breakdowns instead of allocating resources for planned maintenance. The new solution enabled them to predict equipment failure with an accuracy of 92% and plan maintenance more effectively. Overall equipment efficiency increased from 65% (industry average) to 85%. As a result, the optimization improved the scheduling and planning process as well as asset reliability and product quality.

A manufacturer of **industrial equipment** for the beverage industry decided to fit their machines with a monitoring and prediction system to help engineers plan better preventative maintenance. This solved the problem of inefficient, reactive customer service and helped to optimize equipment maintenance schedules, previously dependent on defined time intervals, rather than real needs. The application of machine learning increased business scalability and optimized the cost structure of the company.

Another manufacturer of **packing equipment for agricultural products** has recently introduced a high-performance fruit sorting machine that uses computer vision and machine learning to classify skin defects. The operator can teach the sorting platform to distinguish between different types of defects and sort the fruit into sophisticated pack grades. The solution combining hardware, software and operational optimization reduces complexity of the sorting process.

At deepsense.ai we also use machine learning techniques to tackle challenges in the production area. For one of our clients, a global machinery manufacturer, we have developed a predictive maintenance solution using sensor data to predict failures of complex medical equipment and alert the engineers to perform an early repair. Despite the noisy and scarce data and different types of anomalies, we designed a model of the system and successfully implemented probabilistic models for monitored quantities. As a result, our solution was able to detect anomalous behavior up to two weeks before the equipment failure.

#### Rising interest in machine learning applications in the manufacturing industry

Manufacturing companies now sponsor competitions for data scientists to see how well their specific problems can be solved with machine learning. A recent one hosted by Kaggle, the most popular global platform for data science contests, challenged the participants to predict which manufactured parts will fail quality control, based on thousands of measurements and tests made for each component earlier along the assembly line. The competition was sponsored by Bosch and its outcome is aimed at helping them trace causes of manufacturing defects back to specific steps in the production process, as well as support waste reduction by rejecting faulty components at early stages. As a whole, the competition results will add up to improve product quality and lower costs.

deepsense.ai’s Machine Learning Team also participates in data science competitions focussed on industrial applications. Our team won the AAIA’16 Data Mining Competition “Predicting Dangerous Seismic Events in Active Coal Mines”. The goal was to predict the likelihood of an energy warning level being exceeded in the following 8 hours, based on seismic activity records. Having accurate predictions can help the mines to improve the safety of personnel and expensive equipment and plan work more efficiently. Our solution won the competition, achieving an AUC score of 0.94 (where 1.0 is the theoretical maximum) and outperforming 200 other teams. The method used to win this competition was also presented as a paper at the FedCSIS’16 conference.
