---
title: Hardware
permalink: /hardware/
feature_text: |
feature_image: "https://static.igem.wiki/teams/5569/description/hdwe.webp"
excerpt: ""



images02:
  - src: https://static.igem.wiki/teams/5569/hw2/absah.webp
    alt: Turn clockwise to open the flow switch
    caption: Turn clockwise to open the flow switch
  - src: https://static.igem.wiki/teams/5569/hardware/jiaosoconvert.webp
    alt: Reverse continuous stirring
    caption: Reverse continuous stirring

---

## Overview
In the current fields of molecular biology, synthetic biology, proteomics, and biopharmaceuticals, microbial cultivation and the extraction of intracellular active substances constitute fundamental and critical experimental steps. However, existing technical workflows face significant bottlenecks:

  **1. High equipment cost:** Our field research indicates that mainstream micro-fermentation tank equipment on the market is expensive, creating a significant barrier to entry.

  **2. Complex operation and challenging real-time monitoring:** During experiments, we found that real-time monitoring remains difficult with such equipment. Researchers must still invest significant time in manual operations and prolonged monitoring, especially requiring continuous oversight during nighttime hours. This substantially impacts experimental efficiency and increase researcher workload. Furthermore, existing workflows rely on multiple disparate devices working in tandem, resulting in cumbersome procedures with poor reproducibility.

  **3. High contamination risk:** Both existing shake flask and micro-fermentation methods require manual sampling, resulting in elevated overall contamination risks that severely compromise research stability and efficiency.

{% include figure.html image="https://static.igem.wiki/teams/5569/hardware/h40.webp" caption="Figure 1.1 3.1.1	Overall Presentation Diagram" %}

To systematically address these challenges, our project team innovatively proposed the design of an "**Integrated Fermentation & Processing System (iFPS)**" based on real-world research needs. This system deeply integrates mechatronics and intelligent control technologies, seamlessly combining three core functional modules---micro-fermentation culture, high-speed centrifugal collection, and mechanical agitation disruption---into a single compact benchtop device. This achieves true end-to-end automation from "post-inoculation" to "crude lysate collection." The system not only significantly enhances experimental consistency and operational safety but also keeps equipment costs around **\$100**-**just 1% of the cost of existing micro-fermentation devices.** fundamentally solving problems points in synthetic biology practice---namely high costs, low efficiency, and heavy reliance on manual labor.



## Device Development Process

Throughout development, we strictly adhered to standard hardware development procedures and the iGEM-advocated Design-Test-Learn-Build cycle, structured into five phases.

{% include figure.html image="https://static.igem.wiki/teams/5569/hardware/h36.webp" caption="Figure 1.2 R&D Process Diagram" %}

 **Phase 1: Defining Requirements and Pain Points**
The primary task in this phase is to precisely identify core issues within the current laboratory workflow. Through researcher interviews and observation of experimental procedures, we pinpointed the project's pain points Based on this, we defined the core design requirements for the device and established the ultimate objectives to be achieved. All design decisions stem from these requirements.


 **Phase 2: Existing Solutions and Technology Research**
 This phase involved a comprehensive review of existing technical solutions. We analyzed the strengths and weaknesses of commercially available stand alone equipment (shakers, centrifuges, homogenizers) and conducted in-depth research on hardware solutions related to automation and miniaturization from previous iGEM projects. This approach avoided redundant work while providing inspiration and technical feasibility validation for our innovative "single-motor-driven multi-mode switching" solution.

 **Phase 3: Mechanical and System Prototyping**
In this phase, we translated concepts into concrete engineering designs. Using SolidWorks software for 3D modeling, we meticulously considered the dimensions, materials, and compatibility of all components. This iterative process involved multiple design revisions and improvements based on team discussions and feedback.

 **Phase 4: Prototype Manufacturing and Integration Testing**
This phase marks the critical transition from virtual to physical reality. We manufacture all custom parts via methods like 3D printing, procure standard components, and complete the assembly and debugging of the first prototype. Subsequently, rigorous system integration testing is conducted in the wet lab. This testing phase is crucial for identifying any design flaws, performance limitations, or unexpected behaviors. The validation results from the wet lab provide insights for further design iterations and refinements."


 **Phase 5: Comprehensive Feedback and Design Optimization**
During this phase, we invited target users (other iGEM teammates, lab peers, faculty members) to experience the device operation and gathered feedback on **human- machine interaction, operational safety,** and structural stability. This feedback directly informed the final design iterations. Ultimately, all design files, code, and bill of materials were finalized, and comprehensive assembly guides and user manuals were developed to ensure project replicability.

## Requirement and Cost Analysis

Through interviews with multiple laboratory researchers, we discovered that the process of extracting substances in laboratories consumes significant time.Simultaneously, the need to move between different instruments significantly increases the error rate. Based on this, we conducted research into traditional laboratory processes and the problems inherent within them.


{% include figure.html image="https://static.igem.wiki/teams/5569/hardware/h24.webp" caption="Figure 1.3 Flowchart for Laboratory Shaker Culture and Miniature Fermentation Methods" %}

| **Evaluation Criteria**     | **Existing Traditional Solution (Micro-fermentation tank + Centrifuge + Grinder**)                                                                                                                                                                                                                             |
| :----------------------- | :---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Time Cost**            | **Extensive manual operations** (aliquoting, transferring, resuspending, balancing, setting up equipment) require approximately **60--75 minutes of active handling time**. <br> T**he experiment requires continuous operation**: Monitoring fermentation conditions necessitates 24-hour uninterrupted sampling and experimentation. The prolonged continuous work and disrupted sleep patterns are difficult for researchers to endure. <br> **Total process duration:** Approximately **1.5--2.5 hours** from culture completion to obtaining lysate. |
| **Equipment Cost**       | **High initial procurement cost:** The price of a miniature fermenter is at least **\$10,000.** The combined cost of three separate pieces of equipment---a rocking incubator, centrifuge, and shaker---is approximately **\$5,000**.                                                                         |
| **Laboratory Space Occupancy** | **Significant space requirements:** Three large devices occupy at least **2--3 square meters** of valuable laboratory space.                                                                                                                                                                                |
| **Labor and Training Costs** | **High demands:** Personnel must be trained to proficiently operate three instruments and master aseptic techniques. <br> **Value wastage:** PhD students and researchers spend time on repetitive tasks.                                                                                                     |
| **Result Consistency and Risk** | **Poor consistency:** Manual operations inevitably introduce errors, resulting in high coefficient of variation**. <br> **High Risk:** Multiple sample transfers increase **cross- contamination** hazards. Moreover, manual sampling from conical flasks and miniature fermenters carries a high risk of contamination.     |


Thus, we identified three major pain points: **cumbersome and time-consuming operations, high equipment costs and space requirements, and poor result reproducibility**. Based on this, we defined the core design requirements for the equipment: achieving full automation and integration of the three key functions:** fermentation, centrifugation, and agitation/disruption. The goal is to reduce manual operation time by over 90% and significantly enhance data consistency. All design decisions stem from these requirements.

## Project Philosophy and Design

### Project Overview

Our hardware team has consistently focused on addressing practical challenges encountered in synthetic biology micro-fermentation, aiming to provide solutions and fresh perspectives for tackling specific problems. Our design philosophy centers on "**integration, automation, and miniaturization,** **Modular**." The system appears as a compact desktop unit internally divided into two modules: an upper fermentation module and a lower integrated centrifugal agitation module. Controlled by a single STM32 chip, the system utilizes multiple control chips to drive motor rotation. An OLED display shows culture temperature, pH, and motor parameters for real-time monitoring of cultivation conditions. It also comes equipped with numerous components and modules for users to choose from, catering to diverse needs and practical situations.We have backed up all the models and codes for others to refer to and reproduce.


<div class="video">
<iframe title="HUST-China: Hardware-Exploded view (2025)" width="560" height="315" src="https://video.igem.org/videos/embed/sQaX8CospmmN3LUYnY1ixy" allow="fullscreen" sandbox="allow-same-origin allow-scripts allow-popups allow-forms" style="border: 0px;"></iframe>
</div>
### Core Module Function Design and Testing

**a. Fermentation Culture and Fluid Control: Enables strain expansion culture and employs flow switches to control two liquid release stages for microbial enrichment and transfer of concentrated culture.**

- **Fermentation Condition Control Module:** Multiple designs at the top of the device primarily enable real-time monitoring and control of fermentation conditions.

{% include figure.html image="https://static.igem.wiki/teams/5569/hardware/hh1.webp" caption="Figure 3.2.1 Schematic Diagram of Fermentation Condition Control Module" %}

- A 42-step motor drives the stirrer and flow switch via bevel gear transmission. Three small ports accommodate: a pH sensor for real-time monitoring, a temperature sensor for fermentation conditions, and a blue light emitter to activate the strain's suicide switch, preventing microbial leakage. Two sidewall ports allow tubing to deliver solutions from a peristaltic pump for timed feed supplementation.

<div class="video">
<iframe title="HUST-China: Hardware-Real shot of the motor (2025)" width="560" height="315" src="https://video.igem.org/videos/embed/nB2YrNVLdf8GfF9isd2DUp" allow="fullscreen" sandbox="allow-same-origin allow-scripts allow-popups allow-forms" style="border: 0px;"></iframe>
</div>

- **Leakage Control and Cell Enrichment Module:** Leakage control and cell enrichment are achieved through a nested double-layered fermentation tank system and interlocking mortise-and-tenon joints.

{% include figure.html image="https://static.igem.wiki/teams/5569/hardware/h49.webp" caption="Figure 3.2.2 Schematic of Liquid Control and Microorganism Enrichment Module (a:Leakage Control Device, b:Mortise-and-Tenon Structure)" %}



- The inner tank bottom features a 30° sector-shaped aperture aligned with two sector-shaped and circular apertures in the outer tank base plate. The outer tank's edge is concave, while its central protrusion interlocks with the inner tank bottom to create hydraulic pressure, preventing medium leakage through edge gaps.
- The inner tank's mid-section incorporates a mortise-and-tenon structure that mates with the complementary half on the bottom of the stirring rod. The top stepper motor operates in two modes: continuous clockwise rotation and counterclockwise step mode (each button press rotates 30° counterclockwise). During clockwise rotation, the inclined planes of the mortise-and-tenon joints slide against each other, preventing the inner tank from rotating. The stirring rod does not rotate the inner tank, ensuring thorough mixing of the bacterial solution. During counterclockwise rotation, the vertical surfaces of the two joints interlock. The stirring rod drives the inner tank to rotate, thereby controlling leakage.

{% include figure2.html images=page.images02 %}

- The circular opening at the bottom of the outer tank has internal threads. These are used to secure a bacterial filter membrane during the first drainage cycle. The culture medium flows directly into the waste tank via the rubber tube connected to the bottom of the drainage port, while cells are intercepted, enhancing bacterial density within the tank. The fan-shaped aperture facilitates the second drainage cycle, directing residual medium and cells downward to the centrifugal shaking module for subsequent processing.
- Under microscopic observation, the size of lipolytic yeast cells was determined (Figure 3.2.4). After averaging measurements from 20 cells, the bacterial cell's major axis measured approximately 8.4 μm, and the minor axis approximately 5.2 μm. A bacterial filter membrane with a mesh size of 3 μm was selected.

**b. Centrifugation and Agitation-Induced Lysis: Primarily separates cells from the culture medium. Adding glass beads followed by agitation lyses cells to release intracellular squalene.**

- **Centrifugation Module:** Enriched bacterial suspension enters centrifuge tubes via liquid transfer tubes. A brushless DC motor within the base, coupled with a synchronous gear set, drives the centrifuge tubes and their contents to high-speed rotation.

- During cell centrifugation, rotational speed and duration are the two most critical parameters. Increasing rotational speed significantly raises motor costs, while extending duration reduces production efficiency. To determine the conditions under which our equipment achieves maximum economic benefit, we employed Minitab to design the following response surface experiment.

- {% include figure.html image="https://static.igem.wiki/teams/5569/hardware/h37.webp" caption=" Figure 3.2.4 Experimental Design Table" %}

- The two influencing factors are rotational speed (1000 rpm--5000 rpm) and time (1min--5 min). The response variable is absorbance (A), measured at 500 nm wavelength using a spectrophotometer. The blank control group consists of pre-centrifugation solution, while the sample group comprises supernatant collected after each centrifugation run.



- According to the spectrophotometric formula:

-                                          *A* = *ε* • *c* • *l*

- *A* : Absorbance; *ε*  : Molar absorptivity (L/(mol·cm)); *c*: Solution concentration (mol/L); *l*: Optical path length (cm)

- It is evident that absorbance is directly proportional to solution concentration. A lower A value indicates a lower cell concentration in the supernatant. Therefore, our optimization objective is to achieve the lowest A value using the minimum rotational speed and shortest duration. The A contour plot indicates that all regions outside the shaded area represent viable [rotational speed: time] combinations.

- The maximum speed of the purchased brushless motor under load, measured by an infrared sensor, is 840 rpm. Through a 1:3 speed reduction gear set, the speed can reach 2520 rpm. At this speed, centrifugation requires only about 3 minutes, maximizing economic efficiency.
{% include figure.html image="https://static.igem.wiki/teams/5569/hardware/h38.webp" caption="Figure 3.2.5 Contour Plot of Absorbance" %}
- **Mode Switching Module:**

- {% include figure.html image="https://static.igem.wiki/teams/5569/hardware/hh2.webp" caption="Figure 3.2.6 Schematic of the Mode Switching Module" %}
<div class="video">
<iframe title="HUST-China: Switch Bearing Schematic (2025)" width="460" height="215" src="https://video.igem.org/videos/embed/vN7xmhDkPJmwbuFQNtVP64" allow="fullscreen" sandbox="allow-same-origin allow-scripts allow-popups allow-forms" style="border: 0px;"></iframe>
</div>
- We designed the equipment based on the commonly used glass bead shaking method in laboratories to disrupt cells and extract intracellular squalene. To save space, we developed a mode switching module to integrate both shaking and centrifugation functions. The core design features a mode switching bearing (animation shown).

- **Centrifugation Mode (Motor Forward Rotation):** When the motor rotates forward, the limit device locks the switching bearing, aligning it concentrically with the main shaft. This drives the entire rotor assembly to high-speed rotation, generating strong centrifugal force that precipitates microbial cells to the bottom of the centrifuge tube**.**
- **Shaking Mode (Motor Reverse Rotation):** When the motor reverses, the switching bearing unlocks. Under mechanical force, it undergoes radial translation, creating an eccentric displacement. The motor then rotates, driving the centrifuge tube to perform high-speed eccentric shaking.

- **Motion Decoupling Mechanism---"One-Way Bearing":** To prevent centrifuge tubes from self-rotating during oscillation, we incorporated a one-way bearing between the tube holder and the rotating shaft. This achieves pure oscillation-based disruption.

<div class="video">
<iframe title="HUST-China: Switch Bearing Physical Object (2025)" width="460" height="215" src="https://video.igem.org/videos/embed/vvgN7HHYfFkn3DRL4DMzMK" allow="fullscreen" sandbox="allow-same-origin allow-scripts allow-popups allow-forms" style="border: 0px;"></iframe>
</div>

- To resolve the issue of repeatedly transferring liquid and balancing the centrifuge, we designed a communicating centrifuge tube based on the communicating vessel principle. A matching liquid connection switch was also developed to prevent circulation while facilitating easy liquid release and collection.

{% include figure.html image="https://static.igem.wiki/teams/5569/hardware/h45.webp" caption="Figure 3.2.7 CommunicatingCentrifuge Tube Kit" %}

**c. Intelligent Control System: Primarily used to automate the entire device, reducing manual operation time**

To integrate control of the entire apparatus and monitor cell culture conditions in real time, we developed the following circuit control system based on the STM32F103C8T6 microcontroller:

{% include figure.html image="https://static.igem.wiki/teams/5569/hardware/h9.webp" caption="Figure 3.2.8 Wiring Diagram" %}
### Equipment
 **Condition Monitoring Module**
    Drawing inspiration from HUST-China 2023's fermentation condition monitoring design, we employed a DS18B20 + temperature probe as the temperature monitoring module and a pH composite electrode + pH sensor as the pH detection module. ([Hardware | Huazhong University of Science and Technology - China - iGEM 2023](https://2023.igem.wiki/hust-china/hardware))

  {% include figure.html image="https://static.igem.wiki/teams/5569/hardware/h1.webp" caption=" Figure 3.2.9 pH Calibration Curve" %}

 **Motion Control Module**
 We selected distinct motors for the three key motion control points based on thorough research and analysis of each motor's characteristics, implementing optimal designs:

 **Top:** The top motor drives the stirring rod and activates the flow switch, requiring high precision. We selected the 11HS2810S stepper motor, which enables precise speed and angle control via PWM modulation and delivers substantial torque.

 **Bottom:** The bottom motor controls centrifugation and oscillation, demanding strict speed regulation. We selected the 36-3530 brushless DC motor. Its brushless design enables high rotational speeds at low power consumption.

 **External:** The external motor controls timed nutrient supplementation to regulate nitrogen levels in the culture medium. We fabricated a simple peristaltic pump that achieves timed supplementation (of ammonium sulfate) by adjusting the motor's speed and rotation status. For the peristaltic pump's control motor, we selected the MG996R servo motor. It is easy to program, allows precise specification of rotation angles, and consumes minimal power.

{% include figure.html image="https://static.igem.wiki/teams/5569/hardware/hh3.webp" caption="Figure 3.2.10 Peristaltic Pump" %}


### Software

We developed the program using Keil5. The primary functional code is as follows:

{% include figure.html image="https://static.igem.wiki/teams/5569/hardware/h46.webp" caption="Figure 3.2.11 Main Code" %}


## Product Iteration

This section documents the challenges encountered during hardware development and their corresponding solutions.

### Version 1.0

Initially, our device design comprised only an upper chamber for fermentation and a lower chamber for enrichment and lysis. In the upper chamber, we incorporated a stirring rod. Two openings were added to the chamber's side, each equipped with a slide valve for controlled liquid addition and removal. At the tank bottom, a drain pipe allowed the concentrated bacterial solution to be sequentially transferred into centrifuge tubes below via a plug-screw mechanism upon fermentation completion, followed by removal for weighing. After centrifugation in the lower tank, the shaft was manually switched from concentric to eccentric mode, and grinding beads with buffer solution were added to initiate agitation and cell disruption.

However, this version still required significant manual labor, leading us to develop V2.0.
{% include figure.html image="https://static.igem.wiki/teams/5569/hardware/hh4.webp" caption="Figure 3.3.1 Schematic of the First-Generation Model" %}


### Version 2.0
{% include figure.html image="https://static.igem.wiki/teams/5569/hardware/hh5.webp" caption=" Figure 3.3.2 Schematic of the second-generation model" %}

Compared to the first generation, we introduced a mortise-and-tenon structure to mechanically link the flow switch and stirrer rod. The top knob can drive either the stirrer rod or the flow switch depending on its rotation direction. Simultaneously, we designed an automatic switching bearing that alters the motor's rotation direction to toggle between centrifugal and agitation modes.

However, during practical testing, we encountered the following issues:

1.  Leakage at the bottom requires liquid to be evenly distributed into the centrifuge tubes below, making it impossible to ensure proper balancing;
2.  Subsequent processing of microbial cells required multiple rounds of liquid removal and addition within the centrifuge tubes, making the operation cumbersome;
3.  The mode-switching bearing only altered the radius of circular motion during oscillation mode, failing to achieve true centrifugation.

To address these issues, we continuously optimized the design and launched V3.0.

### Version 3.0


{% include figure.html image="https://static.igem.wiki/teams/5569/hardware/hh6.webp" caption="Figure 3.3.3 Schematic Diagram of Third-Generation Model" %}
{% include figure.html image="https://static.igem.wiki/teams/5569/hardware/h39.webp" caption="Figure 3.3.4 Third-Generation Circuit Wiring Diagram" %}


In the third-generation design, we introduced an automated control system. A DC motor-driven stirring rod was added to the top of the upper tank, along with two small openings for pH and temperature sensors to enable real-time monitoring of fermentation conditions.

To address the challenges of unbalanced centrifuge tubes and cumbersome liquid removal, we introduced a communicating centrifuge tube kit.

To ensure the mode-switching bearing achieves true oscillation functionality, we installed a one-way bearing on the drive shaft to transmit unidirectional motion, enabling selection between centrifugal and oscillation modes.
<div class="video">
<iframe title="HUST-China: Third Vision Model (2025)" width="560" height="315" src="https://video.igem.org/videos/embed/hnytwZsPjAqQcComMRBuPU" allow="fullscreen" sandbox="allow-same-origin allow-scripts allow-popups allow-forms" style="border: 0px;"></iframe>
</div>

Although we successfully resolved the issues encountered in the third version, we now face a new challenge:

1.  The brushed DC motor proved difficult to control for precise angular rotation, causing the inner plate to frequently stop at undesirable positions and preventing successful single-pass liquid discharge.
2.  The 3D-printed servo gears proved too flexible to effectively rotate the outer tank for secondary drainage.

### Version 4.0

Ultimately, we iterated to V4.0 as the final hardware product for this project. Through research, we discovered that stepper motors can simultaneously achieve continuous rotation and precise angle control. By positioning both discharge outlets on the base plate and utilizing the stepper motor's fixed-angle rotation, we resolved the issues present in the third version.

## Modularity

Our device continues last year's modular and "building block" design philosophy, enhancing tank interchangeability and portability. Different modules can be easily swapped based on varying scenarios and fermentation requirements to maximize environmental benefits and operational efficiency while reducing costs. This year, we added several new designs, including: Stirring Module, Fermentation Tank Module, Flow Control Module, Temperature Control Module, and Aeration Module.

### Agitator Module

During fermentation, stirring rods are commonly used within fermentation tanks to mix reactants and ensure uniform reactions, facilitating efficient processes and thorough nutrient absorption. Different stirring rods are required based on the physicochemical properties of the fermentation broth, such as viscosity and dissolved oxygen levels.

{% include figure.html image="https://static.igem.wiki/teams/5569/hardware/hh7.webp" caption="Figure 3.4.1 Agitator Module" %}

Figure 3.4.1(a) shows a fan-blade agitator designed for vigorous liquid agitation. Its curved profile reduces resistance during mixing, making it suitable for environments requiring large-scale culture medium agitation.Figure 3.4.1(b) shows a spiral-rising agitator that uniformly mixes microbial cultures with nutrients. Its thin blades easily divide the liquid, making it suitable for high-viscosity culture media.


### Flow Control Module

During fermentation, scenarios often arise where controlling the flow rate or volume of fermentation broth is necessary to optimize subsequent processes. 

{% include figure.html image="https://static.igem.wiki/teams/5569/hardware/hh8.webp" caption="Figure 3.4.2 Flow Control Module" %}

Figure 3.4.2(a) depicts a flow control module featuring porous construction for uniform leakage, enabling seamless integration into our equipment. The triple-hole design enhances operational flexibility. Figure 3.4.2(b) shows a flow control valve that regulates flow from the upper to lower tubes via a rotary handle, offering simple operation suitable for infrequently used flow control valves.


### Speed Control Module

During cell centrifugation, the required rotational speed is influenced by cell size. To facilitate switching the centrifuge's rotational speed, we designed a speed adjustment module.

{% include figure.html image="https://static.igem.wiki/teams/5569/hardware/hh9.webp" caption="Figure 3.4.3 Speed Control Module" %}

Figure 3.4.3(a) shows a 7-tooth gear connected to the drive shaft. Figure 3.4.3(b) depicts a gear set designed for speed adjustment, featuring 14, 21, and 28 teeth respectively. These gears amplify the motor speed by 2x, 3x, and 4x, allowing speed switching through height adjustment for quick and convenient operation.


### Aeration Module

Lipase yeast requires substantial oxygen during fermentation, making an efficient aeration system critical for enhancing fermentation efficiency. To improve oxygen utilization, we have designed the following three aeration systems.

{% include figure.html image="https://static.igem.wiki/teams/5569/hardware/hh10.webp" caption="Figure 3.4.4 Aeration Module" %}

Figure 3.4.4(a) shows an aeration unit where gas is introduced radially through the disc. Typically used downward, it features small outlet holes and high gas pressure, suitable for systems with high oxygen demand.Figure 3.4.4(b) depicts another aeration unit connected to a long gas transport pipe. It diverts part of the gas flow into spherical chambers before diffusing outward, increasing gas-liquid contact area. This configuration serves as an ideal transfer station for multiple aeration systems.Figure 3.4.4(c) depicts an aeration line that can be laid along the tank bottom. It disperses bubbles in a fishbone pattern. As the bubbles rise, they agitate the liquid and dissolve, featuring a simple structure suitable for tubular fermenters.

### Fermentation Modules

To accommodate diverse fermentation requirements and conditions, we have concurrently designed several variants of fermentation apparatus.

{% include figure.html image="https://static.igem.wiki/teams/5569/hardware/hh11.webp" caption="Figure 3.4.5 Fermentation Modules" %}


Figure 3.4.5(a) A 200 ml fermentation vessel enables larger-scale fermentation and extraction.Figure 3.4.5(b) shows a fermenter with baffles added to increase oxygen supply during agitation.


### Product Usage Procedure:

1.  Install communicating centrifuge tubes and sterile filters; close all flow switches
2.  Open the top lid, add the culture medium, and inoculate the microbial strain.
3.  Connect the power cord and press buttons in sequence to activate corresponding functions.

{% include figure.html image="https://static.igem.wiki/teams/5569/hardware/h2.webp" caption="Figure 4.1 Button Layout Diagram" %}

The red button powers on the device and illuminates the display. The yellow button activates the upper motor for continuous clockwise rotation. The left white button controls the upper motor for 30° counterclockwise rotation. The blue button controls the lower motor rotation. The white button reverses the lower motor rotation direction. The green button activates the nutrient replenishment system.

## User Feedback

**Throughout the design and development process, we actively engaged with multiple experts and users in the field, extensively gathering feedback to continuously optimize the device. This valuable input provides crucial support for our ongoing product iterations**.

### Expert Recommendations: Equipment Architecture Design Direction

We first consulted Professor Yang Xuezhi from the National Bio-Manufacturing Industry Innovation Center. He systematically introduced common design approaches for industrial equipment and pointed out: integrated hardware design is suitable for fixed, single-process workflows, while scenarios requiring higher flexibility should adopt industry-standard modular connection methods. Based on this advice, we established an integrated hardware-centric design direction and ultimately successfully developed the iFPS device.

### Initial Prototype Testing and Key Improvements

We presented the initial prototype to Professor Wang Jinchun at the Engineering Practice Innovation Center of Huazhong University of Science and Technology. While acknowledging the device's innovation, he proposed the following critical improvements from a practical application perspective:

- **Structural Strength and Stability**: Common PLA or ABS materials are prone to deformation or fatigue fracture under sustained vibration, particularly during high-speed centrifugation.
- **Cleaning and Contamination Prevention**: Micro-pores on 3D-printed components can harbor bacteria, making thorough sterilization difficult. Enhanced device sealing is also required to prevent contamination by extraneous microorganisms during cultivation.
- **Control System Reliability**: The DuPont wire-to-breadboard connection method is only suitable for experimental validation. In complex environments involving temperature/humidity fluctuations and electromagnetic interference, exposed electronic components and tangled wiring may compromise long-term stable operation.

To address these issues, we have developed corresponding improvement plans: After structural validation, critical bearings and moving parts will be replaced with metal materials to enhance longevity and operational stability; a removable, independently sterilizable "reaction inner chamber" will be designed to effectively resolve cleaning and sealing challenges; a dedicated PCB board will be developed to integrate circuits, improving system safety and anti-interference capabilities.

{% include figure.html image="https://static.igem.wiki/teams/5569/hardware/h44.webp" caption=": Figure 3.5.1 Discussion with Professor Wang Jinchun" %}


### Expanding Application Scenarios and Functional Optimization

We also invited Dr. Chen Yulong from the Institute of Resource Biology and Biotechnology at Huazhong University of Science and Technology to participate in testing. He provided valuable suggestions from the perspectives of synthetic biology and large-scale fermentation:

- **Fermentation Module Improvements**: Recommend adding baffles to the fermentation section to prevent vortex formation while expanding fermentation volume to ensure adequate oxygen supply.
- **New Application Scenarios**: Initial drainage can be utilized to collect bacterial extracellular secretory products. Prompt separation of these products mitigates feedback inhibition, thereby enhancing fermentation efficiency.

Based on these recommendations, we redesigned the fermentation module by incorporating baffled fermentation vessels of multiple specifications and integrating an oxygen supply unit. Dr. Chen's proposed application scenarios also guided us toward new R&D directions. We are currently exploring the use of this equipment for exosome collection, further validating its scalability and practical value in bioprocessing.

{% include figure.html image="https://static.igem.wiki/teams/5569/hardware/h3.webp" caption="Figure 3.5.2 Exchange with Dr. Chen Yulong" %}

## Equipment Component List and Cost

| Serial No. | Name                              | Unit Price | Quantity | Total Price |
| :--------- | :-------------------------------- | :--------- | :------- | :---------- |
| 1          | Consumables                       | 0.2￥/g    | 1703.74g | 340.74￥    |
| 2          | MG995 996R Metal Standard Servo   | 19.16￥    | 1        | 19.16￥     |
| 3          | Micro 28 Stepper Motor            | 38￥       | 1        | 38￥        |
| 4          | MUH Unidirectional Bearing        | 18.37￥    | 1        | 18.37￥     |
| 5          | DS-430 Self-Resetting Non-Locking Button | 0.5￥      | 2        | 1￥         |
| 6          | One-way Bearing                   | 3.58￥     | 1        | 3.58￥      |
| 7          | KCD Mini Boat-Shaped Pushbutton   | 1.75￥     | 4        | 7￥         |
| 8          | L298N Chip                        | 6.86￥     | 1        | 6.86￥      |
| 9          | STM32F103C8T6 chip                | 6￥        | 1        | 6￥         |
| 10         | 830-hole breadboard               | 4.1￥      | 1        | 4.1￥       |
| 11         | Temperature + pH Sensor           | 104￥      | 1        | 104￥       |
| 12         | Brushless DC Motor                | 110￥      | 1        | 110￥       |
| 13         | Metal Components, Wires           |            |          | 5￥         |
| **Total**  |                                   |            |          | **663.81￥≈93.2＄** |

## Discussion

### Contributions to Synthetic Biology and the iGEM Community

**Significance of the Integrated Automated Cultivation and Lysis Mechanism**

This integrated automated cultivation and lysis mechanism will benefit all teams focused on protein expression screening, metabolite engineering, and cell factory optimization. Our device establishes a mechanism that automates the process from cultivation to lysis on a low-cost benchtop platform, enabling easy replication by other teams. In this way, it introduces the option of "desktop-scale automated sample preparation" for subsequent teams and projects beyond iGEM, thereby broadening the application scope of synthetic biology in rapid iteration and standardized characterization.

**Significance of the Single-Motor Reversible Multi-Mode Drive Mechanism**

As a device capable of automatically switching between centrifugation and shaking modes using a single power source, it will assist all teams in developing compact, cost- controlled automated biological experimental equipment. One advantage of its modular integrated design is the ability to simplify control systems and reduce manufacturing costs, enabling complex functionality even under resource constraints.

**Significance of the Device's Self-Balancing Centrifuge Tubes**

Achieving balance during centrifugation is a critical challenge in automated experimental systems. Our self-balancing centrifuge tubes, based on the communicating vessels principle, instantly achieve mass equilibrium upon liquid injection. This innovation eliminates the cumbersome, time-consuming manual weighing and balancing steps required in traditional centrifugation, providing essential support for true "one-button start" fully automated workflows.


## Conclusion

Our device is designed to precisely address real-world issues through human-practice feedback loops, meeting diverse needs while continuously optimizing performance. Furthermore, its versatility and replicability unlock broader application potential.

([Overview](#overview), [Requirements and Cost Analysis](#requirement-and-cost-analysis), [Project Philosophy and Design](#project-philosophy-and-design) , [Discussion](#discussion))

Core functions and structure performed well in the prototype, demonstrating the device's practicality and functionality. This strongly indicates that with further refinement, it can evolve into a commercialized and practical model in the future.

([Project Philosophy and Design](#project-philosophy-and-design), [Product Usage Procedure](#product-usage-procedure), [Discussion](#discussion))

We conducted multiple user tests and interviews, gathering diverse feedback on the entire device. This feedback was either incorporated into the device's actual production or integrated into plans for future enhancements and implementation.

([Requirement & Cost Analysis](#requirement-and-cost-analysis), [User Feedback](#user-feedback))

All design information, 3D printing data, electronic schematics, parts lists, and assembly instructions for the final prototype have been fully documented and released in a format easily accessible for replication.

In summary, we have developed and demonstrated an automated crude cell extraction device integrating fermentation, centrifugation, and shaking, effectively addressing challenges in synthetic biology development and application.

We are more than willing to provide the source code and model for reference by future iGEM teams. You can contact us via email.

