---
layout: "post"
title: "An Approach to quality monitoring in manufacturing using supervised machine learning on product Stat..."
author: "T. Wuest (West Virginia U.) Chris Irgens (U. of Strathclyde) K.D. Thoben (U. Bremen)"
date: "2014-08-01"
keywords: "Product State; Data; Manufacturing; Process; Quality Monitoring; Cluster Analysis; Supervised Machine Learning"
---

**Quoted as**: Wuest, T., Irgens, C., & Thoben, K.-D. (2014). An approach to monitoring quality in manufacturing using supervised machine learning on product state data. Journal of Intelligent Manufacturing, 25(5), 1167–1180. doi:10.1007/s10845-013-0761-y

#### Abstract:
Increasing market demand towards higher product and process quality and efficiency forces companies to think of new and innovative ways to optimize their production. In the area of high-tech manufacturing products, even slight variations of the product state during production can lead to costly and time-consuming rework or even scrapage. Describing an individual product’s state along the entire manufacturing programme, including all relevant information involved for
utilization, e.g., in-process adjustments of process parameters, can be one way to meet the quality requirements and stay competitive. Ideally, the gathered information can be directly analyzed and in case of an identified critical trend or event, adequate action, such as an alarm, can be triggered.  

Traditional methods based on modelling of cause-effect relations reaches its limits due to the fast increasing complexity and high-dimensionality of modern manufacturing programmes. There is a need for new approaches that are able to cope with this complexity and high-dimensionality which, at the same time, are able to generate applicable results with reasonable effort. Within this paper, the possibility to generate such a system by applying a combination of Cluster Analysis and Supervised Machine Learning on product state data along the manufacturing programme will be presented. After elaborating on the different key aspects of the approach, the applicability on the identified problem in industrial environment will be discussed briefly.

###  1 INTRODUCTION
Increasing market demand and customer requirements towards higher product and process quality and efficiency (Kovacic & Sarler, 2009) force companies to think of new and innovative ways to optimize their production. At the same time, high-tech engineering products become more and more optimized (e.g., gear wheels for offshore wind turbines, aerospace products working at the physical limits of materials). The growing importance of quality for competitive success has been demonstrated over the last 30 years by various companies, which successfully understood and consequently translated customer requirements into final products (Holcomb, 1995; Robinson & Malhotra, 2005). Facing these trends, manufacturing companies have to deal with rapidly increasing complexity within their manufacturing and business processes to achieve the expected quality of their products.

Quality is the degree to which a set of inherent characteristics fulfils requirements (in accordance with DIN EN ISO 9001:2008 definition). Requirements in this context are understood as the need or expectation that is stated, generally implied or obligatory. On this foundation product quality in manufacturing can be defined by the extent to which the manufacturing company is capable to offer products which fulfil customer requirements (Koufteros, Vonderembse & Doll, 2002; Boonitt, 2010). When looking at the manufacturing programme, customers are not necessarily the end
customer of the final product, but can also represent internal customers of another department of the manufacturing firm or of another collaborating company within the manufacturing network.

To meet the customer requirements, at first it has to be ensured that the manufacturing programme is designed so that it is able to produce the desired product properties (Mohanty, 2004). Such a manufacturing programme consists of a process chain with each process having a number of
operations. In the chain, processes may be linked one-to-one, disjunctively or conjunctively to preceding or subsequent processes. Each process may have a chain of operations similarly linked within the process. After ensuring the general suitability of the manufacturing programme, the
process quality comes into play. Today, even in advanced manufacturing programmes, there is always a degree of variation of the input parameters of individual products during the various manufacturing processes and operations (Yu & Wang, 2009). As the processes are not independent of each other, these variations can, even being tolerable from an individual (isolated) process perspective, lead to an unacceptable accumulation causing failure of the final product to meet the customer requirements. For example, even though bar steel is ordered according to DIN/ISO specification, there is actually a variation range within the specifications/standards (Siyasiya, Rooyen, Stumpf, 2005). A batch produced from steel from the same producer can cause no quality problems during manufacturing but a later batch can fail due to batch variations. For example, a variation in the homogeneity of the melt can influence the hardening capabilities and the distortion behaviour (Kessler, Prinz, Sackmann, Nowag, Surm, Frerichs, Lübben & Zoch, 2006; Clausen, Frerichs, Goch, Klein, Lübben, Nowag, Prinz, Sackmann, Stöbener, Surm & Zoch, 2006) or a difference in the titanium ratio within the melt can have an impact, in combination with the different previous processes, on the behaviour during heat treatment and result in quality problems like rework or scrapage.

As process quality in manufacturing is directly connected to product quality (Brinksmeier, 1991; Jacob & Petrick, 2007) improvements of the manufacturing processes can have an impact on various levels, e.g., efficiency improvements and/or product quality improvements (Pavletic, &
Sokovic, 2009). Especially during the manufacturing of engineering products with a high added value, rework and scrapage due to problems within the processes cannot only be very costly, but also damage the reputation of a company within a distributed production network. Along a
manufacturing programme, parts as well as information are exchanged between the interfacing processes. As manufacturing processes become increasingly more complex, the handling of information plays an important role in the management of product and process quality (Albino, Pontrandolfo & Scozzi, 2002; Hicks, Culley & McMahon, 2006). Tracking individual products along the manufacturing programme and managing their product quality becomes more and more relevant and leads to large amounts of information and data that has to be handled. As too much information can mean a threat to the process quality (Jansen-Vullers, van Drop & Beulens; 2003), it is desirable to know what information and data needs to be gathered, how it can be structured
and finally, how it can be applied with maximal impact.

Using product and/or process data to monitor and/or forecast certain events, chains of events and/or outcomes is a topic widely discussed among scholars for more than the last 20 years. Du, Elbestawi & Wu (1995) describe monitoring as an act of identification of characteristic changes of a process by evaluating process data without interfering running operations. In their research they
find that monitoring based on learning from examples turns out to be more effective in manufacturing programmes than learning from instructions.

Yet, as in manufacturing programmes, a wide variety of potential errors can influence the quality characteristics of a product. The product end quality is finally determined by all stages of the manufacturing program (Zantek, Wright & Plante, 2006; Jiang, Jia, Wang & Zheng, 2012).    Whereas quality and condition monitoring is well established and partly already successfully implemented, mostly monitoring only one manufacturing process at a time (e.g., Silva, 2009; Jenab & Ahi, 2010), concepts taking the importance of the system view (e.g., Babiceanu & Chen, 2006) into account, thus monitoring of the whole manufacturing programme, are still rare and need more attention from the research community (e.g., Choudhary, Harding & Tiwari, 2009). Additionally, some researchers like Ding, Ceglarek & Shi (2002) recognize the importance of the
system view for monitoring but focus on a specific characteristic, in that case diagnosing fixture faults. Other research, also taking the whole manufacturing programme into account, focusses on the identification of the critical manufacturing process causing a deviation from the planed characteristics (e.g., Zantek, Wright & Plante, 2006). Jiang, Jia, Wang & Zheng (2012) and Sukchotrat, Kim & Tsung (2009) are both presenting novel approaches tackling similar issues as this paper to monitor multistage manufacturing programmes using either error propagation networks (Jiang, Jia, Wang & Zheng, 2012) or multivariate control charts (Sukchotrat, Kim & Tsung, 2009) on a conceptual level with further research still ongoing.

Within this paper, an approach to increase process and product quality in manufacturing through monitoring of product state based data and utilizing a combination of Cluster Analysis and Supervised Machine Learning will be presented. Through this approach, an individual product can be described in a structured way along the manufacturing programme. The derived product state data, which is reflecting the increasing complexity of modern manufacturing programmes, is highly complex and characterised by a large number of influences and thus statistically of highdimensionality.
This makes it difficult, or even impossible to affect conventional modelling of cause-effect relations in an efficient and goal-oriented way. Therefore, the analytical power of machine learning theory is utilized within this approach, having the advantage to be designed to handle large amounts of complex and high-dimensional data. The goal is, whenever a product’s state shows too much variations, the system will trigger an adequate action, e.g., utilizing expert systems, either to adjust the interfacing processes to reach the required quality or to scrap the
individual product to avoid unnecessary processes and thus a waste of resources.

In the following section, the theory behind the product state based view in manufacturing will be introduced. Based on that, section three matches the requirements of using product state based data
with the advantages of a combination of cluster analysis and supervised machine learning, capable of handling the high-dimensional, complex and large sets of data and information accruing in this
context. In section four, these tools are applied and a theoretical example is given to make the approach more feasible. The paper concludes with a discussion and a brief summary of the results,
limitations and a short outlook on further research planed within this context.

### 2 CONCEPT OF PRODUCT STATE
A manufacturing programme transforms raw material to final products through different value adding processes in order to deliver to the customer the desired product. Consequently, the goal of
every manufacturing programme is to add value to a work piece, component or product (Kalpakjian & Schmid, 2009) (hereinafter the term product will be used comprehensively) with
each process. Adding value in manufacturing implies physical transformation of the product (e.g., transformation of form, hardness, chemical composition, etc.). The specific purpose of every
process and operation is to execute a part of the physical transformation of the product. Thus, the state of the product is changed at least with every (value adding) process. Looking at a product by its state has the advantage to being able to describe or record the transformation. Therefore, looking at the product state along the whole manufacturing programme accumulates a complete
picture of realized measures and transforming processes.

#### 2.1 Product State & State Characteristics
The concept of the product state based view describes a product at certain times during a manufacturing programme or after, through a combination of relevant state characteristics. As
definable and ascertainable measures, state characteristics can be described in a quantitative or qualitative way. The state of a product changes due to external influence, be it intentionally, for
example through machining, or unintentionally, e.g., through corrosion, from one point in time to another when at least one descriptive state characteristic changes (Wuest, Klein & Thoben, 2011).


_Fig. 1 a product state change is illustrated highlighting state characteristics changed during the process X in gray on the right hand side_

![SL_Quality_fig1.PNG](/Digital_for_Industry/images/SL_Quality_fig1.PNG)

Within this concept, it is inalienable to identify information with an impact on the individual product and process to create a set of relevant state characteristics. **In today’s ever more complex
industrial manufacturing programmes, there are many factors, e.g., machinery used, type of material, later application area, etc., which have to be considered. Today, not all influencing
factors for an individual manufacturing process chain are known** . Nevertheless, these (unknown) factors may have an influence on the final product quality. Therefore, there is a need for new
methods and approaches to include their influence in monitoring and warning/forecasting models within the domain of quality management.

Product state characteristics explicitly include measures of the inner work piece state such as internal stress allocation (Wuest, Klein & Thoben, 2011). Being hard to measure especially during
manufacturing, such measures have a proven influence on processes and thus the quality of the final product (Zoch, 2012). Today, these measures are not adequately considered yet, partly as
they are difficult to measure and their influence is just moderately known (Zoch & Lübben, 2011).
In the spirit of a holistic system view on the manufacturing programme it is nevertheless important to consider such measures for quality improvement initiatives. Thus, the product state based view
consists not only of a conception of the product state itself. The product state has to be seen in the environment of the whole manufacturing programme, the different processes and operations. In the following section, this essential connection between process and product state is described in more detail.

#### 2.2 Product State in Manufacturing
As stated above, a **multi-stage manufacturing programme** consists of different processes and operations, each with a certain very specific task and goal. To transform a raw material to a final
product all processes are necessary and have to be executed in a certain order. Fig. 2 shows an exemplary industrial manufacturing programme with four main processes: casting, forging,
machining and heat treatment. In industrial practice, a manufacturing programme involves generally more processes and/or some have to be executed multiple times at different stages of the
whole manufacturing programme. To build a foundation for the following concept, the authors chose to use a simple example in order to focus on the main ideas instead of getting lost in details.
Today, it has to be taken into consideration that manufacturing programmes are not executed by a single company at a single location any longer but rather in collaboration with other companies
(Seifert, 2009). This includes extra interfaces and interdependencies between stakeholders as well as manufacturing and business processes. For example, the casting (process 1) in the exemplary
manufacturing programme (see Fig. 2) could be done by company A in country X, whereas the processes forging (2) and machining (3) are executed by company B’s department C (country Y)
and D (country Z). As this adds further complexity to the manufacturing itself by involving additional logistics and information exchange, there is an indispensible need for a clear structure to
identify, share/distribute and use product and process information (Merali & Bennett, 2011).
At this point, the product state based view (Wuest, Klein & Thoben, 2011) offers a structuring of product and process data for such already highly complex distributed manufacturing programmes.
First of all, in a production network, different companies and firms are working closely together, therefore, the information exchanged has to be in a format that all stakeholders can derive and use
with their individual systems. Thus, product state data is ideally not interpreted and therefore exchangeable between different systems. Connecting the product state data/information to the
individual product and process is in line with today’s ambition to ensure the quality of every single product. This is especially true for safety critical products in e.g., aerospace industry and/or
products with expensive manufacturing programmes/processes. Through time-dependency, the whole value adding process and the changes can also be tracked and used as a product history,
which is already expected in some industries (e.g., automotive industry).

During a whole **distributed manufacturing** programme with **stakeholders in different locations** al contributing to the final product, the product state change, respectively the change of certain relevant state characteristics at that point in time can present valuable information for the following processes. These addressed processes can be either directly following processes or processes scheduled later in the manufacturing programme.

_Fig. 2. Transforming of a product during a multi-stage manufacturing programme_

![SL_Quality_fig2.PNG](/Digital_for_Industry/images/SL_Quality_fig2.PNG)

Theoretically, the product state can be derived at all times during a multi-stage manufacturing programme (see Fig. 2). In order to design a manageable and sufficiently detailed model, the
checkpoints when the product state should be derived have to be defined (see Fig. 3). In general, a higher number of defined product state checkpoints during a manufacturing programme results in
increased complexity and higher dimensionality of the model and a larger amount of data/information generated overall. Traditional forecasting methods based on modelling causeeffect
relationships tend to not handle this added high-dimensionality and complexity well.

Based on that consideration, it might make sense for such cause-effect based approaches to choose as few checkpoints as possible but as many as needed checkpoints for the task. First analyses
suggest that at least as many checkpoints (plus one) as there are processes are needed to grasp the major (intentional) product state changes. Some processes, e.g., machining, might need to be
separated in additional operations with extra checkpoints, e.g., clamping, to grasp important product and process state information. The nature of the checkpoints is partly comparable to the
concept of using quality gates to ensure quality of a process (see, e.g., Spath, Scharer, Landwehr Förster & Schneider, 2001; Giebel, Essmann, Du Preez & Jochem, 2009). A checkpoint represents
a critical control point which not only allows to assess the previous actions but to intervene in the process if necessary (Fischer & Breitenbach, 2009). Other attempts to increase quality through
looking at relations use similar arguments to define checkpoints, phases or stages (Mizuyama, 2004; Mizuyama, 2006).

The approach to utilize combined cluster analysis and supervised machine learning on product state data described in the following sections 3 and 4 is suited to handle highly complex and highdimensional
data rather well. Therefore, as many checkpoints as possible can and should be defined, theoretically increasing the granularity of the quality supervision and the results.

_Fig. 3 illustrates the introduced exemplary manufacturing programme, highlighting the process/product level and the overarching information (data) level. The information level handles the
product and process state information/data set of the individual products along the manufacturing programme._

![SL_Quality_fig3.PNG](/Digital_for_Industry/images/SL_Quality_fig3.PNG)

Analysis of this product and process state information/data describing the product state at the diferent checkpoints offers the chance to adjust process parameters of following processes
accordingly during the manufacturing programme itself. Thereby, ideally reducing the detected quality deviations of the final product. Or, on the other hand, the possibility to identify critical
product state changes early in the manufacturing programme can be used to implement an alarm system (“red flag”) which interferes if the product state changes in an unappreciated direction at a
certain checkpoint early in the manufacturing programme. Based on such a monitoring system, experts can decide if the product can still reach the final quality requirements or if it should not
receive more value adding processes. This expert decision will be supported by a provision of the needed information/data of the current product state and the received treatment so far (e.g., process
parameters). Additionally, the expert decision can be supported by IT-based expert systems if possible.

#### 2.3 Potential utilization of **product state based view**
The initial idea for the aforementioned utilization of product state information/data to create a “red flag” warning system based on modelling the dependencies between the different states or state characteristics had to be discarded due to unmanageable complexity and high-dimensionality. That approach was based on modelling dependencies, which could be either between state characteristics within a state or in between different states along the manufacturing programme. To model these dependencies in this context, large volumes of product and process data/information is needed beforehand and thus impractical, at best. Not all dependencies are known, not to mention a possible quantification of the cause-effects relations. Furthermore, there are still various causeeffect mechanisms unknown, especially when the whole manufacturing programme is in the focus (system view) and not just a single manufacturing process/operation. An example for such dependencies is the field of distortion engineering where after years of research still not all mechanisms are identified (Zoch, 2012). Much research and individual testing/experiments would be needed to get a first, partly satisfying result. At the same time this would make the approach inflexible, time-consuming and vastly expensive, thus, not applicable in a fast changing environment like industrial manufacturing.

_Fig. 4. Excerpt of a first approach to illustrate state relationships in an industrial example_

![SL_Quality_fig4.PNG](/Digital_for_Industry/images/SL_Quality_fig4.PNG)

Theoretically, assuming that most dependencies, basically cause-effect relationships, between states or state characteristics are known, it still is very resource intensive to integrate them all in a model. Fig. 4 shows a small excerpt of an attempt to model the relationships between a selection of state characteristics of a manufacturing programme in an industrial case. The different notations appearing in Fig. 4 are not further explained within this paper. The purpose of Fig. 4 is solely to support the argument of increasing complexity when modelling cause-effect relations within a manufacturing process. The result was that even so some knowledge gain and awareness was raised within the company, the process of deriving the dependencies and interdependencies and cumulating them in a cause-effect model was too time-consuming and prone to failure. As soon as one parameter of a process within the manufacturing programme is changed or the product itself changes, the whole model has to be redeveloped. And, if a company has different production lines with different products, the model has to be developed for each individual product/production line.The combination of unknown cause-effect relationships, fast increasing complexity and highdimensionality in modern manufacturing and the time-consuming and resource binding process are not reflected adequately in the achievable results.

As this first approach was unrewarding, a new approach is needed which can utilize the opportunities reflected in the product state based view on manufacturing programmes and at the same time being able to handle the occurring challenges like high-dimensionality from increased complexity within the product state data in an efficient and goal oriented way. Within the application of this new approach it has to be possible somehow to identify relevant drivers (causes) of certain product state changes in a practical and efficient way without having to analyze and having in-depth knowledge of the aforementioned relations in such great detail. Prescriptive data processing/algorithm will find this sort of complexity hard/impossible to handle because causeeffect mechanisms may be hidden and unknown by all the relations, some of which are in themselves unknown (Wuest, Irgens & Thoben, 2012).

Sequences of manufacturing operations and processes are characterised by the start and end states of each operation or process. Experiential data and information are often used to determine whether or not the states represent a desirable stage in the manufacturing of the product. Classical Statistical Process Control (SPC) is based upon the use of state process data. The usefulness of SPC lies in the ability to examine a process and the sources of variation in that process. Variations in the process that may affect the quality of the end product or service can be detected and corrected, thus reducing waste as well as the likelihood that problems will be passed on to the customer.

Different types of variations occur in all manufacturing processes. Variations have in the past been typified into common cause variations consisting of the variation inherent in the process as it is designed. Common cause variations may include variations in temperature, properties of raw materials, strength of an electrical current, etc.; and assignable-cause variations, which happens less frequently than the first. With sufficient investigation, a specific cause, such as abnormal raw material or incorrect set-up parameters, can be found for assignable-cause variations. However, modern multi-variate systems have considerable complexity with high-dimensional data (Apley & Shi, 2001; Wang & Jiang, 2009), with unknown or unclear cause-effect relationships in the process(-es) and with non-Gaussian data distributions, at times exhibiting seeming chaotic behaviour (Chou, Polansky & Mason, 1998; Borror, Montgomery & Runger, 1999; Stoumbos &
Sullivan, 2002), categorical (Wang & Tsung, 2007) or mixed (categorical and numerical) variables, and numerical data with different scales of measurement. Furthermore, a monitoring technique without assumptions on the parametric forms of distributions is important in this context (Monostori, Váncza, & Kumara, 2006). In the following chapter, a combination of cluster analysis and supervised machine learning is introduced which is expected to handle the aforementioned challenges well and at the same time produce usable results for industrial application.

### 3 SUPERVISED LEARNING AND CLUSTER ANALYSIS APPLIED TO PROCESS STATES
Manufacturing processes will thus naturally exhibit states prior and subsequent to the process. In this context, the term process may be a single operation or a sequence of operations as part of an overall manufacturing programme. Such process states may be known or unknown, desirable or undesirable and imply that some form of classification method would be required to monitor andultimately facilitate process control. The problem arises with unknown and undesirable states. The unknown dimension could imply an infinite set of states and as such would make classification infeasible. Assuming that there is a finite population of desirable states it would be feasible to regard all other states as undesirable, and focussing on a finite set of states; and furthermore regard the probability of the discovery of new desirable states as small. If one was confident that it would be possible to 'discover' such new desirable states, one can assume that there is a finite and
relatively static population of desirable states. Thus we postulate that a manufacturing programme will exhibit a finite set of relatively static desirable states and that all other states are by default undesirable. On this basis it can be assumed that a suitable classification method may be applied in order to calculate process states and that once the process state is known, the basis for process monitoring and control is laid. The diagram below (Fig. 5) should illustrate this in as much as once the state is determined, the next step is to determine the 'driving' forces represented by the two types of process inputs or influences.

_Fig. 5. Determining driving forces based on process inputs_

![SL_Quality_fig5.PNG](/Digital_for_Industry/images/SL_Quality_fig5.PNG)

#### 3.1 Selection of suitable classification methods

Simple classification methods will not necessarily provide a link between the classified state and state drivers, nor will it facilitate the 'discovery' of new states. Furthermore, manufacturing processes may exhibit large dimensionality as well as non-Gaussian, pseudo-chaotic behaviour. This militates against orthodox SPC and statistical dimension reducing methods, and focuses attention on multi-variate methods and data-mining approaches. Classification methods such as Support Vector Machine (SVM) (Hamel, 2009) and various forms of Cluster Analysis could support the classification needs of large dimensionality process data, while various forms of Cluster Analysis could also support the needs for the exploration of new process states.


Cluster Analysis is an approach that finds structure in data by identifying natural groupings (clusters) within the data set. Cluster Analysis in this context should be viewed as exploratory data analysis tools because they are generally used to generate, rather than test, hypotheses about data structures, thus in this case used to generate and iterate a learning set for use in the Supervised Machine Learning process.

Constraining the manufacturing process sequence to a set of known and desirable states with the need to effect infrequent 'discovery' of new desirable states, can provide the basis for a hybrid process monitoring and control approach which uses Supervised Machine Learning together with cluster analysis to handle the requirements of high-dimensionality data, unclear or unknown cause-effect mechanisms, non-Gaussian data with various scales and types

To be able to ensure that processes, in the widest sense, are under control, there are a number of fundamental questions which must be answered and acted upon:

What is the state of the product/process?
Is the state desirable?
Is the state ‘driven’ by parameters which can be used to influence it?
What can be done if the state is undesirable and persistent?
Is it likely that the state may change thus needing no action i.e. non-persistent?

The above questions should formulate the process monitoring and control strategy. The first two questions express the fundamental need to be able to determine the product/process state and type before any further action is initiated. The desirability of the state is of the highest importance. All **undesirable states** are consigned to the one state of 'undesirable'. Question 3 addresses the need to know what process influence(s)/input(s) represent the dominant 'drivers' for the state so that potential rectification can be supported. Given the nature of the data as described above, the *actual cause-effect mechanism* may not be obvious and/or known, but over time may become clearer through the identification of the 'driving' influences. Question 4 is at this stage seen as outside the domain of the automatic process monitoring and control and is therefore seen as delegated to expert domains together with the answer to Question 3. Question 4 addresses the issue of identifying the persistence or otherwise of a given process state so that warnings can be produced if the persistence is changing in an unfavourable manner.

Increasing process scope and the need to monitor conditions which are dependent upon large numbers of parameters, high-dimensionality, (possibly in their 1000s) has made the above questions more difficult to answer. Such processes typically exhibit chaotic behaviour, thus hiding cause-effect mechanisms.

Modern data-mining methods such as Cluster Analysis and machine-learning methods have shown the ability to overcome problems in process, or product, condition monitoring by handling events with very large data dimensions and without explicitly known cause-effect models and inherent state information (Chinnam, 2002). The principle of such solutions can be expressed in Fig. 6 below:

_Fig. 6. Phases of process state monitoring using Cluster Analysis and Supervised Machine_

![SL_Quality_fig6.PNG](/Digital_for_Industry/images/SL_Quality_fig6.PNG)

The light grey phase on the left side of Fig. 6 indicates a continuous creation and updating oflearning data, while the other phases indicate a real-time condition data capture and state classification and analysis.

The product/process condition vectors xi form a population matrix X through time such that the population X is increasing incrementally with each process monitoring vector xi. It is assumed that xi has high-dimensionality and that this process monitoring vector is captured in real-time. Realtime theoretically implies immediate reaction (Shukla & Chen, 1996). In practice, the time horizon connected to real-time is depending on the application, e.g., face recognition in manufacturing
environments with <1s (Megahed & Camelio, 2010). Real-time systems in general are systems that have the ability to react to certain events or triggers within an acceptable time-frame (Sha, L., et al., 2004). Gogouvitis, S., et al. (2010) differentiate hard real-time, where the task must be completed before a certain deadline, in contrast to soft real-time, where the task should be completed accordingly. In the presented application, real-time is not defined with a hard timeframe. In this case the real-time issue is not addressed as the fundamental method is to be investigated.

**The total manufacturing programme**, which consists of the sequence of individual processes, can therefore be seen as a sequence of classifiable states, and as the total manufacturing programme progresses towards the conclusion, the overall manufacturing programme's state can be seen as the accumulated X matrix. This matrix and the individual xi condition vectors thus form the working data for the classification methods. Once learning data has been established, incremental process
state classification and monitoring can take place in real-time.

#### 3.2 The learning phase
Supervised Machine Learning methods display great strength in their ability to handle large amounts of high-dimensionality data quickly and reliably. The perceived cost of such methods is the need to create learning data. The learning data is used to create a model through which the realtime monitoring vectors xi are processed to classify the implied state. The benefit of the use of learning data is that it can easily be updated thus facilitates continuous learning. This will in turn be useful as a process changes with time through wear and tear, maintenance, increased operator skills, changes is raw-material supply, etc.

In order to create the learning model it is necessary to identify characteristic data vectors and label these as representative for a state. This phase is the initial phase for setting up the machine learning framework, and can subsequently be used to incorporate maturing and changing knowledge. The above diagram (Fig. 6.) shows two complementing methods by which this is achieved; clustering and adjustment by user specialist.

Cluster Analysis or clustering is the assignment of a set of observations into subsets, or clusters, so that observations in the same cluster are similar in some sense. Clustering is a method of unsupervised learning, and a common technique for data analysis used in Machine Learning, Data Mining and Pattern Recognition.
Clustering techniques apply when there is no class to be predicted but rather when the instances are to be divided into natural groups. These clusters presumably reflect some mechanism at work in the domain from which instances are drawn, a mechanism that causes some instances to bear a stronger resemblance to each other than they do to the remaining instances.

In producing obvious clusters it is possible to name them and typify the cluster characteristics in terms of the implied process/product states. Consequently, the biggest gains are likely in knowledge-poor environments, particularly when there are large amounts of unlabelled, unclassified data. Indeed clustering techniques can be viewed as a way of generating taxonomies for the classification of objects. Thus clustering is seen as useful for the generation of learning data for Supervised Machine Learning methods.

There are various clustering methods. In this context, the hierarchical approach is seen as the best candidate. This is so because this form of cluster representation provides inter cluster relationships in terms of similarity scores at various levels. It is important to establish clusters which are a
maximum distance apart as these would represent vectors which are the most different and as suchare likely sources for learning data. Therefore, hierarchical cluster formation is considered suitable as a basis for selection of yi instances. This is the principle of Kennard-Stone data sampling (de Groot, 1999).

_ Fig. 7. Agglomerative clustering output showing natural cluster trees with varying similarity values_
Fig. 7 shows a small sample population X of 12 vectors x1 - 12 , each indicated as an individual line of different shaded 'pixels' with a diagramatic tree structure on the left of the diagram, indicating the cluster relationship among the vectors, as a function of the distances between them. This is similar to the dendrogram below in Fig. 8. The top line of Fig. 7 is showing the notation ElementA_B indicating the 11 elements of each xi , that is a dimensionality of 11, while the
vertical list on the right of the diagram indicates the number of the corresponding xi, named VectorXXX. The shaded matrix indicates the value of the individual vector elements such that the darker the 'pixel' the higher the element's value, and the lighter the pixel the lower is the value, while a white pixel indicates zero value.

_Fig. 8. Cluster dendrogram_

![SL_Quality_fig8.PNG](/Digital_for_Industry/images/SL_Quality_fig8.PNG)

In Fig. 8 it is clear that the populations {x1, x2}, {x3, x4, x5} and {x6} form 3 clusters, the first 2 form a separate cluster with the 2nd highest measurements of similarity, here Euclidian distance. These 2 or 3 clusters could be possible candidates for providing learning vectors. Work is needed vis-a-vis the selection and use of linkage methods and the user needs to choose appropriate clusters from the hierarchy, see Fig. 6. Given that hierarchical cluster analysis is used for the
identification of candidate clusters for the learning data set, it is considered sufficient to complement the clustering with expert/user input.

Clustering information can be used to identify learning sets from the population X, so that clusters which exhibit 'extreme'/'undesirable'/'unusual' states different from the main mass of the population X may be included in a learning set for a Supervised Machine Learning method. This method is useful during continuing use of the process and for each product operation, so that by regular use of the Cluster Analysis of product state data, state knowledge can be updated through
adjustments in the learning set. This phase may be run as frequently as needed to reflect thegrowing knowledge and/or increasing data variance.

The learning set Y is consisting of the learning vectors yi. Each yi having the same format as the vectors xi except an additional label indicating which state it represents. The population Y can be as small as 1 for each state, but it is most desirable to include a higher number.

### 4 SUPERVISED LEARNING AND PRODUCT/ PROCESS STATES

The selected machine learning method here is Support Vector Machine (SVM). SVM methods build on developments in computational learning theory and have attracted attention, particularly
in bio-informatics applications, because of their accuracy and their ability to deal with highdimensionality data. Indeed, some appear to be relatively immune to the ‘curse of dimensionality’. These methods offer considerable potential and have already been used by the author in **condition monitoring** involving xi event vectors up to 500 dimensions (parameters per observation). SVM is originally a linear binary classification method. It is based upon the simple classification idea that an input set of values, vector xi is assigned to a positive class if g(xi )>= 0, where:

g(xi )=w * xi + b.

Fig. 9 below indicates the simple linear, binary classification principles. The classification direction is indicated as perpendicular to the class divider, the hyper-plane.

_Fig. 9. Illustration of binary classification in 2-D_

![SL_Quality_fig9.PNG](/Digital_for_Industry/images/SL_Quality_fig9.PNG)

The vector w in this aspect represents a decision hyper-plane's normal vector and is commonly named weight vector in Supervised Machine Learning literature (Hamel, 2009; Manning, Raghavan & Schütze, 2009). The hyper-plane thus described becomes the population separator,
state classifier, of xi, with g(xi ) defining whether or not the xi is positively classified.

SVM methods require learning data, Y. Y is normally compiled from selected process monitoring vectors xi . The process monitoring vectors form time series and the aim is to determine each process monitoring vector's state against the learning data. Y is furthermore an approximate  representation of the data space, and placing a decision surface, hyper-plane, equidistant from the respective class/state boundaries should increase the probability of correctly classifying the data
points, xi , not in the learning set. This leads to the maximum margin SVM. Once the learning data, Y, has been established, the SVM process can be employed to assess the state by classifying the process monitoring vector xi. Given that xi is sampled as a time series, it is then possible to generate a state time series by classifying the xi SVM needs a relatively small example of data vectors by which to typify the various types of states.

The vectors xi are the attribute vectors as discussed above. Given the 'dot-product' nature of the classifier, it can be used as a non-linear classifier, making it particularly flexible and useful (Kernel method). Furthermore, the binary nature of the method is easily extended to a multi-class classifier. Thus in summary, the method serves as a non-linear, multi-class classifier. This allows the mapping of xi into a number of defined states with g(xi) defining the 'strength' of the
membership of the state. Given that xi is a time-series of process feature vectors, this enables a mapping of the process into a number of states. The changing of which can be represented as in Classification direction section 4.1 below. Whether this can be done in real-time is a question which can only be
determined once the approach has been investigated further.

Given the present context, this is seen as particularly valuable as inter-process product states can be given a higher resolution than just {good, bad} and a resultant nuanced corrective response can be activated.

#### 4.1 Support Vector Machine Learning and Cluster Analysis applied to Process/Product State Monitoring
By constraining the product and associated manufacturing programme monitoring to the observation of desirable and undesirable inter process states and step-by-step product work-inprogress states, it is clear that the use of a hybrid monitoring and diagnosis method can be formed from Cluster Analysis coupled to SVM. SVM is regarded as being particularly suited for this purpose due to its reliable classification of high-dimensional data and relatively cheap data processing cost for real-time or quasi real-time applications, while Cluster Analysis may assist in the definition of learning data.

Assuming that the outlined approach in section 3 with respect to the creation and updating of the learning data, Y, is possible, SVM can be applied successfully to determine, incrementally possibly in quasi real-time, the process/product states at various points in the overall manufacturing programme. Some sample output is shown below. This output shows the mapping of process states, and the states' growing and diminishing vis-a-vis being active. It is based upon the classification of the state vector xi . The 'strength' and direction which are given by g(xi).

_Fig. 10. Process state versus xi samples, thus showing state versus time_

![SL_Quality_fig10.PNG](/Digital_for_Industry/images/SL_Quality_fig10.PNG)

At approximately x110 the state defined by the current {w,b} becomes active and stays active until approximately x297 . The state then drops into inactivity rapidly.
Four different states may be determined, represented by four different {w,b} planes, thus four different hyper-planes. The vertical axis shows the values of the four different gi(xi) while the horizontal axis shows the process monitoring vector xi at different i values, thus different times. In this manner, there is a mapping of the process states over time. Such mapping of process states shows how states are changing with time.

_Fig. 11. States vs. time, showing 4 process/product states, each colour indicating different states_

![SL_Quality_fig11.PNG](/Digital_for_Industry/images/SL_Quality_fig11.PNG)

Fig. 11 shows a sample state analysis over approx 390 samples’, xi, worth of process data, each xi consisting of 60 elements. This is mapped with respect to 4 different states, that is 4 different hyper-planes. The curves show how these 4 states change with time. A state’s curve above the horizontal axis indicates, in this example, an active state. When more than one curve is above the x-axis it may indicate ‘gray zone/transition zone’ if states are mutually exclusive. States, however,
not be mutually exclusive. This depends upon the selection of the learning data Y. The y-axis indicates the strength of the state, the x-axis indicates the xi.

Careful use of the learning data Y, the real-time observed product/process data X together with the hyper-plane definition(s) {w,b} and applied Cluster Analysis such as outlier score computation, can produce a probability model showing which observed individual process/product parameters, or vector elements of xi, seem to be driving the state dynamics. An example of which is in Fig 12 below.

_Fig. 12. Importance of individual process/product parameters in the state dynamics_

![SL_Quality_fig12.PNG](/Digital_for_Industry/images/SL_Quality_fig12.PNG)

Fig. 12 illustrates an example of the 60 different process parameters from the example above. The data is analysed to find out which are current 'drivers' for a specific process/product state. The y-axis shows the relative importance of process parameters, while the x-axis indicates the individual process parameter's id. In short, the greater the value, the stronger the 'driver'. Negative values in this case, indicate that the parameter 'drives against' the state membership. The parameters are sorted according to decreasing state influence. This type of information could assist in the diagnosis of the actual state and its corrective action and as such would be important.

#### 4.2 Data Requirements
There are a few assumptions that form the data collection for the successful construction and use
of a hybrid product/process state monitoring system:

1. The partitioning of the whole manufacturing programme into a sequence of processes, each process responsible for the product states of each manufacturing step. The product state is thus the proxy measurement for the process state,
2. the population of product states and consequently process states by proxy, is characterised by high-dimensionality and cause-effect mechanisms are not fully known or understood,
3. there is variability present at least due to variability in product raw-material and process changes,
4. collection of data across a wide spectrum of product and process information is possible.

Given that the proposed methodological approach described above, the data collection, should benefit from the data flexibility inherent in the chosen methods. The assumption is that the total manufacturing programme is likely to exhibit pseudo-chaotic behaviour in as much as each individual process will contribute to the high state dimensionality. Data collection should therefore try to include all parameters considered having any state influence. The practical problems can
thus easily render the proposed methodological approach impractical. On the other hand, the strength of the Supervised Machine Learning approach is that its output will identify the most important discriminant 'drivers' and in this manner, at least potentially identify process domains of concern. Based on this, **the data collection should follow the following principles**:

1. All possible product data from each process within the manufacturing programme should be collected such as inspection data, material data, etc.;
2. all available process parameters should be collected across as wide a spectrum as possible, such as tool information, timing, physical process information;
3. any concerns noted before and/or after the process.

Given these assumptions, regular state data should be collected from the product manufacturing
stages. Given that cause-effect mechanisms between multi-variate process data and the product
states are largely unknown, it is considered necessary to collect process information. The wider
this collection can be made, the richer the ability of the cluster-supervised machine learning and
analysis method will be.


#### 4.3 Discussion
The methodological approach described in this paper is based upon the same method used in another high-dimensionality, chaotic process domain to determine in effect process state and 'drivers' in real-time, although the time base for real-time in this case was hours rather than seconds. The data collection in this other application case was relatively easy in as much as the data was available in electronic form and needed a suitable database interface to download the available data. The available data was also quite extensive in terms of including parameters which could have process influences, although the process exhibited typical chaotic behaviour. The process dimensionality was found to be between 200-300 and the condition vector population was of a similar order of magnitude. The examples shown in Section 4 are from that specific application. In the case of applying this same methodology to the manufacturing sector, it is realised that the supply of data would be more problematic. Some process data would typically be available in electronic form as would most inspection data, at least in high value manufacturing
such as aero-space and parts of the automotive industry. There is an argument for including what may be termed adjunct data such as time, date, operator characteristics, process equipment maintenance records and use in order to cover probable process influences. This will of course increase data collection complexity as well as problems ensuring data integrity.
Another issue is the creation of learning data for the supervised methods. In this case, it is envisaged that the use of agglomerative Cluster Analysis can be used to identify potential undesirable states by isolating extreme states, thus using a Kennard-Stone type data sampling method. Over time, this use should decrease as the population of undesirable state cases increase from the normal running of the manufacturing processes.

Thinking about over-fitting problems within this approach, it has to be considered that clustering is only used for generating the learning set complemented by the expert user, and SVM is basically very resistant against over-fitting given that the learning data has no massive class imbalance
(Scheidat, Leich, Alexander & Vielhauer, 2009) and a specific hyper-plane is chosen among the many separating the data (Vapnik, 1998). It is the norm to select the 'maximum margin hyperplane'.

### 5 CONCLUSIONS
In this paper, first the concept of describing an individual product by its product state along the whole (distributed) manufacturing programme was presented (product state based view). After deriving the requirements and challenges of utilizing product state data in modern manufacturing, having to cope with high complexity and high-dimensionality, conventional methods based on modelling cause-effect relations are suspended. Being able to handle large sets of highly complex
and high-dimensional data, a combination of Cluster Analysis and SVM is introduced as a possible way to achieve the goal of improved quality monitoring. Following, a theoretical example of an application of the introduced methods on a similar case illustrates the potential of the approach to have a significant impact on quality monitoring in manufacturing. Finally, a short discussion on challenges arising from application of the presented approach within an industrial manufacturing
environment and eventual data gathering in that field is presented.

Concluding, the approach on using a combination of Cluster Analysis and Supervised Machine Learning on product state based data as an option to monitor and thus laying the foundation to increase quality in manufacturing is very promising. As of today, first discussions with industrial representatives have been carried out focussing on how to apply the presented approach in a reallife industrial environment. In a next step, the approach will be developed further theoretically and
first practical tests will be conducted using synthetic data sets to initial testing of the hypotheses. In parallel, an exemplary industrial manufacturing case will be identified and the approach will be applied to get feedback from real-life conditions and to evaluate the theoretical results.

#### ACKNOWLEDGEMENTS:
The authors would like to thank the “Deutsche Forschungsgemeinschaft” for financial support via the funded project “Informationssystem für werkstoffwissenschaftliche Forschungsdaten”.

#### REFERENCES:
- Albino, V., Pontrandolfo, P. & Scozzi, B. (2002). Analysis of information flows to enhance the coordination of production processes. International Journal of Production Economics, 75, 7-19.
- Apley, D. & Shi, J. (2001). A Factor-Analysis Method for Diagnosing Variability in Mulitvariate Manufacturing Processes. Technometrics, 43(1), 84–95.
- Babiceanu, R., & Chen, F. (2006). Development and applications of holonic manufacturing systems: a survey. Journal of Intelligent Manufacturing, 17(1), 111–131.
- Borror, C., Montgomery, D., & Runger, G. (1999). Robustness of the EWMA Control Chart to Non-Normality. Journal of Quality Technology, 31(3), 309–316.
- Boon-itt, S. (2010). An Empirical Model of the Relationship between Manufacturing Capabilities: Evidence from the Thai Automotive Industry. NIDA Development Journal, 59(2), 19-45.
- Brinksmeier, E. (1991). Prozeß- und Werkstückqualität in der Feinbearbeitung. Fortschritt-Berichte VDI Reihe2: Fertigungstechnik Nr. 234. Düsseldorf: VDI Verlag.
- Chinnam, R. B. (2002). Support vector machines for recognizing shifts in correlated and other manufacturing processes. International Journal of Production Research, 40(17), 4449–4466.
- Chou, Y., Polansky, A. & Mason, R. (1998). Transforming Non-Normal Data to Normality in Statistical Process Control. Journal of Quality Technology, 30(2), 133–141.
- Choudhary, a. K., Harding, J. a., & Tiwari, M. K. (2009). Data mining in manufacturing: a review based on the kind of knowledge. Journal of Intelligent Manufacturing, 20(5), 501–521.
- Clausen, B.; Frerichs, F.; Goch, G.; Klein, D.; Lübben, Th.; Nowag, L.; Prinz, C.;Sackmann, T.; Stöbener, D.; Surm, H.; Zoch, H.-W. (2006). Verzugsentstehung von Wälzlagerringen - Eine
- prozesskettenübergreifende Analyse. HTM Z. Werkst. Wärmebeh. Fertigung 6(61), 309-319. 17
- Fischer, D. & Breitenbach, J. (Eds.) (2009). Die Pharmaindustrie: Einblick, Durchblick, Heidelberg: Spektrum Akademischer Verlag.
- Giebel, M., Essmann, H., Du Preez, N. & Jochem, R. (2009). Improved innovation through the integration of Quality Gates into the Enterprise and Product Lifecycle Roadmaps. CIRP Journal of Manufacturing Science and Technology, 1(3), 199-205.
- Gogouvitis, S., Konstanteli, K., Waldschmidt, S., Kousiouris, G., Katsaros, G., Menychtas, A.,Kyriazis, D., et al. (2012). Workflow management for soft real-time interactive applications in virtualized environments. Future Generation Computer Systems, 28(1), 193–209.
- de Groot, P.J., Postma, G.J., Melssen, W.J., Buydens, L.M.C. (1999). Selecting a Representative Training set for the Classification of Demolition Waste using Remote NIR Sensing. Analytica Chimica Acta 392 (1999) 67-75. Du, R., Elbestawi, M. A., & Wu, S. M. (1995). Automated Monitoring of Manufacturing Processes, Part 1: Monitoring Methods. Journal of Engineering for Industry, 117(2), 121-132.
- Hamel, L. (2009). Knowledge Discovery with Support Vector Machines. John Wiley & Sons, ISBN 978-0-470-37192-3.
- Hicks, B.J., Culley, S.J. & McMohan, C.A. (2006). A study of issues relating to information management across engineering SMEs. International Journal of Information Management, 26, 267-289.
- Holcomb, M.C. (1994). Customer service measurement: a methodology for increasing customer value through utilization of the Taguchi strategy. Journal of Business Logistics, 15(1), 29-52.
- Jacob, J. & Petrick, K. (2007). Qualitätsmanagement und Normung, S. 101-121. In: Schmitt, R. & Pfeifer, T. (Eds.) (2007). Masing Handbuch Qualitätsmanagement. München: Carl Hanser Verlag.
- Jansen-Vullers, M.H.; van Drop, C.A. & Beulens, A.J.M. (2003). Managing traceability information in manufacture. International Journal of Information Management, 23, 395-413.
- Jenab, K., & Ahi, P. (2010). Fuzzy quality feature monitoring model. International Journal of Production Research, 48(17), 5021–5030.
- Jiang, P., Jia, F., Wang, Y., & Zheng, M. (2012). Real-time quality monitoring and predicting model based on error propagation networks for multistage machining processes. Journal of Intelligent Manufacturing, (online first - 2012).
- Kalpakjian, S. & Schmid, S.R. (2009). Manufacturing engineering and technology. New Jersey: Prentice Hall.
- Kessler, O.; Prinz, Ch.; Sackmann, T.; Nowag, L.; Surm, H.; Frerichs, F.; Lübben, Th. & Zoch, H.-W. (2006). Experimental study of distortion phenomena in manufacturing lines. Mat.-wiss. U. 37(1), 11-18.
- Koufteros, X.A., Vonderembse, M.A. & Doll, W.J. (2002). Examine the competitive capabilities of manufacturing firms. Structural Equation Modelling, 9(2), 256-282.
- Kovacic, M. & Sarler, B. (2009). Application of the Genetic Programming for Increasing the Soft Annealing Productivity in Steel industry. Materials and Manufacturing Processes, (24), 369-374.
- Manning, C. D., Raghavan, P., & Schütze, H. (2009). An Introduction to Information Retrieval. Cambridge, UK: Cambridge University Press.
- Megahed, F. M., & Camelio, J. a. (2010). Real-time fault detection in manufacturing environments using face recognition techniques. Journal of Intelligent Manufacturing, 23(3), 393–408.
- Merali, Y. & Bennet, Z. (2011). Web 2.0 and Network Intelligence, p. 11 – 26. In: Warren, P., Davies, J. & Simperl E. (Eds.). (2011). Context and Semantics for Knowledge Management. Heidelberg Berlin: Springer Verlag.
- Mizuyama, H. (2004). Directing Quality Improvement Efforts in a Multi-Stage Production Process through Observational Data Analysis. Proceedings of the 8th International Conference on Manufacturing and Management, 414–421.
- Mizuyama, H. (2006). Artificial-Neural-Network-based MSQIM for Exploratory Analysis of Manufacturing Data. Proceedings of the 7th Asia-Pacific Industrial Engineering and Management Systems Conference.
- Mohanty, P. P. (2004). An agent-oriented approach to resolve the production planning complexities for a modern steel manufacturing system. International Journal of Advanced Manufacturing Technology, 24, 199-205.
- Monostori, L., Váncza, J., & Kumara, S. R. T. (2006). Agent-Based Systems for Manufacturing. CIRP Annals - Manufacturing Technology, 55(2), 697–720. 18
- Pavletic, D. & Sokovic, M. (2009). Quality Improvement Model At The Manufacturing Process Preparation Level. International Journal of Quality Research, 3(4), 309-315.
- Robinson, C.J. & Malhotra, M.K. (2005). Defining the concept of supply chain quality management and its relevance to academic and industrial practice. International Journal of Production Economics 96(3), 315-337.
- Scheidat, T., Leich, M., Alexander, M., & Vielhauer, C. (2009). Support Vector Machines for Dynamic Biometric Handwriting Classification. Proceedings of AIAI Workshops, 118–125.
- Seifert, M. (2009). Collaboration Formation in Virtual Organisations by applying prospective Performance Measurement. Dissertation at the University of Bremen, Bremer Schriften zur Integrierten Produkt- und Prozessentwicklung.
- Sha, L., Abdelzaher, T., Arzen, K.-E., Cervin, A., Baker, T., Burns, A., Buttazzo, G., et al. (2004). Real-Time Scheduling Theory: A Historical Perspective. Real-Time Systems, 28(2-3), 101–155.
- Shukla, C. S., & Frank Chen, F. (1996). The state of the art in intelligent real-time FMS control: a comprehensive survey. Journal of Intelligent Manufacturing, 7(6), 441–455.
- Silva, R. G. (2009). Condition monitoring of the cutting process using a self-organizing spiking neural network map. Journal of Intelligent Manufacturing, 21(6), 823–829.
- Siyasiya, y C., Rooyen, van G. T., & Stumpf, W. E. (2005). Metallurgical factors that affect the strand width during continuous casting of DIN 1.4003 stainless steel. The Journal of The South African Institute of Mining and Metallurgy, 105, 473–481.
- Spath, D., Scharer, M., Landwehr, R., Förster, H. & Schneider, W. (2001) Tore öffnen - Quality- Gate-Konzept für den Produktentstehungsprozess. QZ Qualität und Zuverlässigkeit, 46(12), 1544-1549.
- Stoumbos, Z. & Sullivan, J. (2002). Robustness to Non-Normality of the Multivariate EWMA Control Chart. Journal of Quality Technology, 34(3), 260–276.
- Sukchotrat, T., Kim, S. B., & Tsung, F. (2009). One-class classification-based control charts for multivariate process monitoring. IIE Transactions, 42(2), 107–120.
- Vapnik, V. (1998). Statistical Learning Theory. Wiley. Wang, K. and Tsung, F. (2007). Run-to-Run Process Adjustment Using Categorical Observations. Journal of Quality Technology, 39(4), 312–325.
- Wuest, T., Irgens, C. & Thoben, K.-D. (2012). Analysis of Manufacturing Process Sequences, using Machine Learning on Intermediate Product States (as Process Proxy Data). In: Emmanouilidis, C., Taisch, M., & Kiritsis, D. (Eds.) (2012). Competitive Manufacturing for Innovative Products and Services. Proceedings of the APMS 2012 International Conference of Advances in Production Management Systems, September 24 - September 26, 2012, Rhodes Island, Greece. (to be published by Springer)
- Wuest, T., Klein, D. & Thoben, K.-D. (2011). State of steel products in industrial production Procedia Engineering, 10, 2220-2225.
- Yu, T. & Wang, G. (2009). The Process Quality Control of Single-Piece and Small-Batch Products in Advanced Manufacturing Environment. Proceedings of the 16th International Conference on Industrial Engineering and Engineering Management, 2009. (IE&EM '09), 21-23 Oct. 2009, Beijing, China, 306-310.
- Zantek, P. F., Wright, G. P., & Plante, R. D. (2006). A self-starting procedure for monitoring process quality in multistage manufacturing systems. IIE Transactions, 38(4), 293–308.
- Zoch, H.-W. & Lübben, Th. (2011). Verzugsbeherrschung - Systemorientierter Ansatz als wesentliche Voraussetzung für den Erfolg. Tagungsband zum 26. Aachener Stahlkolloquium, Verlagshaus Mainz.
- Zoch, H.-W. (2012). Distortion engineering – interim results after one decade research within the Collaborative Research Center. Mat.-wiss. U. Werkstofftech. 43(1-2), 9-15.
