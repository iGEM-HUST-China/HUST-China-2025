---
title: Hardware
permalink: /hardware/
feature_text: |
  ## Hardware
  This page introduces the hardware design of our project, including three parts: **enrichment**, **fermentation**, and **modular design**.
feature_image: "https://static.igem.wiki/teams/5175/resources/background/bg-hardware.jpg"
excerpt: "This page introduces the hardware design of our project, including three parts: **enrichment**, **fermentation**, and **modular design**."
---

## Background

After confirming the change in the treatment environment from soil to water, it was urgent to design a controlled closed system for the collection and decomposition of microplastics at this stage, and this year's work on the hardware was carried out accordingly. In order to help our laboratory results to move towards industrial application as soon as possible, we designed a microplastic enrichment device; built a set of *E. coli* and *P. Putida* co-culture fermenter based on the modular design proposed last year, and further improved the design of the modular fermenter, to ensure the convenience and replicability of our design, and continue to help synthetic biology technology in the presentation of hardware.

## Enrichment

### Principle

Although microplastics are already widespread in the environment, one of the difficulties in treating them at present lies in the fact that plastic products physically decompose in the environment to form small-sized particles that are difficult to be recycled and reused. In order to improve the recycling and fermentation efficiency of our system, the first task of the hardware part is to enrich and pre-recycle the microplastics in the environmental samples. We found that the common microplastic enrichment methods include foam flotation, shaker sieve, and dielectric electrophoresis by reviewing relevant information. In order to control the cost of the instrument and avoid the use of too many chemical reagents during enrichment to affect the subsequent reaction, we finally chose to use a bipolar electrode (BPE) and introduce Faraday ion concentration polarization (fICP) to achieve the enrichment of microplastics in the electric field (Fig 2.1): when enough voltage is applied across the length of the microfluidic channel, hydroelectrolysis occurs at the end of the BPE and the cathode and anode produce different ion depletion, and the water in the cathode undergoes reduction to form $\mathrm{OH^-}$:

<center>
  $$
    \mathrm{2H_2O} + 2 e^- \rightarrow \mathrm{H_2} + \mathrm{OH^-}
  $$
</center>
At the anode, water then oxidizes to produce $\mathrm{H^+}$, ensuring that the BPE is electrically neutral:

<center>
  $$
    \mathrm{2H_2O} \rightarrow \mathrm{4H^+} + 4 e^-
  $$
</center>

At the same time, if Tris buffer is present in the solution, $\mathrm{OH^-}$ in the cathode region reacts with TrisH to form neutral Tris, and such a neutralization reaction reduces the number of charge carriers in the vicinity of the cathode, generating a corresponding ion depletion zone (IDZ) with a relatively high solvation resistance:

<center>
  $$
    \mathrm{OH^-} + Tris\mathrm{H^+} \rightarrow Tris + \mathrm{H_2O}
  $$
</center>

Therefore, the trajectory of the microplastic particles can be changed by positioning the BPE and IDZ.

{% include figure.html image="https://static.igem.wiki/teams/5175/resources/hardware/hardware-2-1.webp" caption="Fig 1.1 Principle of operation of bipolar electrodes" %}

### Testing

Regarding the scheme of microplastic enrichment through BPE, modeling has been carried out by related research groups in recent years, but most of these works are centered around polystyrene (PS)[^1] [^2]. Compared with polyethylene terephthalate (PET), which is the treatment object of our project, PS is a lighter material with lower density, which can maintain a certain suspension in liquid; and these models are basically simulated at the scale of 5000 μm, which makes the change of the electric field gradient more stable, and it is convenient to realize the change of the trajectory of the plastic molecules under the condition of lower voltage (30-50 V). When directly changing PS into PET to validate the model, we found that under the same voltage level, we could not achieve the same better separation effect for PET particles; and the scale of these models that have been completed construction is too small, which will bring some difficulties in the process of actual assembly of the microfluidic chip, to which we further optimized the structure and adjusted the voltage of the two sides, so as to make it more suitable for the enrichment of PET. We designed the microfluidic chip as shown below (Fig. 2.2 A, B), which requires five layers to complete the installation, including the base plate (0.5mm), BPE layer (0.3mm), runner layer (0.3mm), storage layer (2mm), and top cover (0.5mm). We add copper foil to the BPE layer and connect the two electrodes, while the other pair of electrodes outside the chip is inserted vertically into the chip through the hole reserved in the top cover and into the storage layer. The upper channel of the flow channel layer is the enriched high-concentration microplastic sample liquid, and the middle channel is the liquid after removing microplastics.

{% include figure.html image="https://static.igem.wiki/teams/5175/resources/hardware/hardware-2-2.webp" caption="Fig 1.2<br> (A) Schematic diagram of microfluidic chip layering;<br> (B) Schematic diagram of microfluidic chip assembly" %}

We used a buffer system to test the performance of the microfluidic chip shown above to verify the feasibility of the design. We equipped Tris-HCl buffer with ph=8.0 and filtered it through bacterial filter membrane to remove insoluble impurities to avoid affecting the experimental results. By reviewing relevant literature, we found that particles smaller than 50 μm dominated the microplastics in tap water in China[^3]. In order to observe the enrichment process by naked eyes, we mixed 50 μm PET particles with Tris buffer to simulate the initial sample, and added a small amount of Caulmers Brilliant Blue reagent to color the PET particles blue. We added 80 V on both sides of the chip to realize the effective separation of PET particles (Fig 2.3A). Finally, we measured the same volume of the initial sample, the enriched high-concentration microplastic sample solution and the low-concentration sample solution, respectively, and filtered them through qualitative filter paper (pore size of 10-12 μm), dried them to a constant weight and then weighed the mass of the filter residue, and took the average values after repeating three times, which were 0.11 g, 0.19 g and 0.01 g, respectively, and basically realized the enrichment of PET particles.

{% include figure.html image="https://static.igem.wiki/teams/5175/resources/hardware/hardware-2-3.webp" caption="Fig 1.3 Enrichment device test<br> (A) Enrichment channel in the test;<br> (B) results of one of the drying to constant weight. a, b, and c represent the initial sample, the enriched high-concentration microplastic sample, and the post-processing results of the low-concentration sample, respectively." %}

### Points for improvement

During our tests, we also found some problems and areas for improvement, mainly stemming from the high voltage and the corresponding high energy loss. The longer channel length and the change of the enrichment plastic material made us have to prefer the pressurized solution in the short term to force a higher driving force; however, at the same time, due to the increase of the device impedance, it makes the chip heat up significantly; the high voltage also affects the ion depletion region at the cathode, where a slight instability in the feed rate produces a large number of bubbles in the channel on the cathode side, as shown in Fig. 2.3A, affecting the subsequent liquid flow.

Our work verifies the feasibility of achieving flow-through enrichment of PET with a bipolar electrode, and also demonstrates that enrichment of different types of microplastics can be achieved by adjusting the voltage interval. From this, we also propose the hypothesis that within a stable voltage interval, can we realize the enrichment of multiple microplastics in the liquid at the same time, providing a basis for subsequent detection or recovery? This may be one of the next research directions for microplastic enrichment using bipolar electrodes, and we look forward to making more attempts in the future.

## Fermentation

### Overview

{% include figure.html image="https://static.igem.wiki/teams/5175/resources/hardware/hardware-3-1.webp" caption="Fig 2.1 Overall diagram of fermenter" %}

In order to realize the co-culture of *P. Putida* KT2440 and *E. coli* BL21 and complete the reaction, we designed the structure of the fermenter as shown in the figure above. We ensured its structural integrity and airtightness by designing threads that engage with each other. From the appearance, the fermenter presents a top and bottom symmetrical structure, like an hourglass, with geometric aesthetics. We have protected all liquid exchange openings in the tank with a bacterial filter membrane and covered all entrances and exits of the tank with UV light to ensure that the bacteria do not escape into the outside environment, ensuring safety.

### Structure

The fermenter as a whole is a bi-directional flow system, including a top-to-bottom temperature differential incubation system and a left-to-right flow system for the samples to be processed, which can be divided into four parts: upper tank, lower tank, interlayer and stirring rod rod.

#### Upper tank and interlayer

{% include figure.html image="https://static.igem.wiki/teams/5175/resources/hardware/hardware-3-2.webp" caption="Fig 2.2 Upper tank<br> (A, B) and interlayer (C) schematics" %}

The upper tank is a fermentation site for *E. coli* and consists of a top cover and a tank body. The total height of the upper tank is 185mm, the single height of the round platform part is 125mm, the upper diameter is 216mm, the lower diameter is 116mm, the thickness of the tank is 8mm. the upper part of the top cover has a diameter of 216mm, thickness of 6.38mm, the lower part of the top cover coincides with the inclination angle of the tank, thickness of 8mm. a, b, c, d, the four pipelines are of outer diameter of 30mm, inner diameter of 20mm. the whole funnel shape design not only enlarges the cultivation space, but also It is easy to realize the control of flow rate and temperature. The left and right sides of the tank are the medium renewal port a, water outlet c, and the inlet and outlet of the samples to be treated b and d respectively; the filter membrane can be fixed at the center hole plate to prevent the entry of *E. coli* but allow PETase to pass through; in the middle, there is a hollow channel connecting the upper and lower tanks, which is used for placing stirring rods. Considering the large amount of culture medium to be added in the pre-treatment period, we designed a separate top cover to guarantee safety and convenience.

The middle layer is the area through which the sample to be processed passes. Structurally, one part of it is integrated with the upper tank, while the other part is independent and is responsible for fixing the bacterial filtration membrane and connecting the upper and lower tanks.

#### Lower tank

{% include figure.html image="https://static.igem.wiki/teams/5175/resources/hardware/hardware-3-3.webp" caption="Fig 2.3 Lower tank schematic" %}

The lower tank is symmetrical with the upper tank. The lower tank consists of two parts: the tank body and the bottom plate, with a total height of 185mm, a single height of 125mm in the round table part, a lower diameter of 216mm, an upper diameter of 116mm, and a tank body thickness of 8mm, which is the incubation place for *P. Putida* KT2440. The inverted funnel shaped design allows the whole system to remain stable and ensures that the vertical liquid flow is carried out properly, and can also be threaded in the center through-hole design for engaging the upper tank piping. The upper part of the bottom plate is 216mm in diameter and 6.38mm thick, while the lower part matches the inclination of the tank and is 8mm thick. the bottom plate utilizes a snap type structure to fit the tank to ensure that the culture liquid will not overflow, and also to facilitate the renewal of the overall culture liquid and the replacement of the tank for inspection. a pipe is the renewal port for the medium; in order to facilitate the release of the rhamnolipid-containing solution after the fermentation, the b pipe is designed to have a screw thread with a pitch of 6mm. for connecting the subsequent irrigation device.

#### Stirring rod

{% include figure.html image="https://static.igem.wiki/teams/5175/resources/hardware/hardware-3-4.webp" caption="Fig 2.4 Schematic diagram of stirring rod" %}

The total length of the stirring bar is 356mm, and the diameter of the center partition is 100mm, with an access position. The whole system adopts the upper and lower tanks linkage stirring system. Since the medium renewal port of the upper tank is continuously fed with culture liquid, we designed a single rotatable stirring device at the inlet, with a hook underneath, which can be directly connected to the stirring plate of the lower tank (Fig. 3.3C); in order to prevent the failure of the self-driven system in the case of a small flow rate, we additionally added a tenon and mortise structure (Fig. 3.3B), which ensures that the stirring plate can be rotated freely along clockwise and also can be rotated counterclockwise with the help of external force through the upper connecting rod. In addition, a flow control function is integrated into the connecting rod (Fig. 3.3A), so that the culture solution in the upper tank can be cooled down in the middle layer and then be suitable for the culture of Pseudomonas aeruginosa in the lower tank. Further flow and temperature control can be achieved by rotating the kit on the top lid of the upper tank (Fig. 3.3A(a)) and using the snap fasteners to fix the height (Fig. 3.3A(b)) to control the rise or fall of the septum on the stirring rod.

###  Design process

In the process of designing the fermenter, we raised many ideas and possible problems in discussions with teachers and related technicians, and improved them one by one. Here, we would like to briefly introduce a few nodes in our design process.

#### Fermenter 1.0

{% include figure.html image="https://static.igem.wiki/teams/5175/resources/hardware/hardware-3-5.webp" caption="Fig 2.5<br> (A) Schematic; (B) sectional views of fermenter 1.0" %}

First, we tried to realize the co-culture of two bacteria in one main tank, simplify the design and reduce the cost of the instrument, so we chose a tank that can be divided into two parts from the inside, separated by a filtering bacterial membrane in the middle (Fig 3.5). The left side of the channel allows the entry of samples and media, which is the culture site of *E. coli* BL21, and the products of the initial degradation of PET pass through the filter membrane to the right side, where they are supplied to *P. Putida* KT2440 for the production of rhamnolipids, and the fermented liquid passes through the filter membrane and out of the fermenter. Two holes on the upper side of the tank are used to place ph and temperature sensors for real-time detection of the fermentation environment inside the tank. However, when we exchanged the preliminary design of the fermenter in the project design with Mr. Yan Yunjun in the summer, he shared many innovative points and attention points of the fermentation process with his research experience, and we found that the design would face the following problems after further understanding the fermentation conditions:

  1. The optimum temperature for the growth of the two types of bacteria is different and cannot be satisfied in this environment at the same time; 
  2. The bacteria will naturally settle at the bottom of the tank and the medium cannot be fully utilized. 

In response to these two problems, we subsequently made adjustments.

#### Fermenter 2.0

{% include figure.html image="https://static.igem.wiki/teams/5175/resources/hardware/hardware-3-6.webp" caption="Fig 2.6<br> (A) Schematic; (B) sectional views of fermenter 2.0" %}

In order to solve the problem of different culture temperatures of two kinds of bacteria, we divided the tank into two and built in a stirring bar respectively (Fig 3.6). The part connecting the pipes in the middle incorporated a flow controller to control the flow rate, which largely solved the above problem. However, the temperature adjustment of the unidirectional flow is limited and there will be some delay, and the two stirring bars need to be driven separately, which will increase the energy loss of the instrument, and such a unidirectional flow device will also affect the fermentation efficiency and the rate of medium renewal. In this regard, we continue to improve the design.

#### Fermenter 3.0

{% include figure.html image="https://static.igem.wiki/teams/5175/resources/hardware/hardware-3-7.webp" caption="Fig 2.7<br> (A) Schematic; (B) sectional views of fermenter 3.0" %}

During our visit with Hubei Nitrogen Energy Biotechnology Co., we and the company's technicians also discussed the design features and application considerations of the fermentation tanks in the production chain that we observed, and the technicians shared with us the characteristics of the cultivation conditions of different soil microorganisms and their connections. Combining the design experience and ingenuity of the company, we changed the original left and right horizontal distribution of the two tanks to vertical distribution, and proposed a set of two-way control of the fermentation system (Fig 3.7), and the connection between the upper tank and the middle level also used a flow control device, which is convenient for controlling the temperature changes in the tank. However, it is also such a flow control scheme that makes the stirring bar only work in the upper tank, and the nutrient utilization of the medium in the lower tank is still a problem, prompting us to make some new attempts.

#### Fermenter 4.0

{% include figure.html image="https://static.igem.wiki/teams/5175/resources/hardware/hardware-3-8.webp" caption="Fig 2.8<br> (A) Schematic; (B) sectional views of fermenter 4.0" %}

In the end, we came up with a final solution (Fig 3.8): we added a channel through the upper and lower tanks, which allowed the mixing function to be connected up and down; at the same time, we added a baffle plate on the mixing bar of the upper tank, which could be used to further regulate the flow rate according to the control lift of the upper thread. This design basically solved many of the above problems, and also provided the basis for the subsequent addition of temperature, pH, flow rate monitoring and other functions.

## Modular design

Our fermenter design continues the modular and "building block" design concept of last year, which enhances the interchangeability and portability of the tanks, making it easy to change different modules according to different scenarios and fermentation needs, in order to achieve the maximum environmental benefits and efficiency, and reduce costs. This year, we have added some designs on this basis, which generally include: stirring module, fermenter module, flow rate control module, temperature control module, and irrigation module.

###  Stirring module

{% include figure.html image="https://static.igem.wiki/teams/5175/resources/hardware/hardware-4-1.webp" caption="Fig 3.1 Stirring module<br> (A) spiral stirring rod; (B) square page stirring rod; (C) double spiral stirring rod" %}

During the fermentation process, in order to ensure the full utilization of the nutrients in the culture medium in the tank, it is necessary to increase the contact area by stirring to promote nutrient uptake and reaction. Due to the different viscosity and flow rate requirements of the liquids, the stirring bars have to be adapted to the specific application scenarios. We have designed three types of stir bars to meet different stirring needs and liquid conditions. The three types of stirring bars can be adapted to different stress levels in order to meet the needs of industrialization.  

As shown in Fig 4.1A, we designed a stirring bar with a spiral ascending blade, which can mix the bacteria and culture liquid more evenly and promote the horizontal circulation of the fermentation liquid; Fig 4.1B shows a stirrer installed at the bottom of the fermentation tank similar to a "fan", which can promote the up and down flow of the liquid; Fig 4.1C shows a strip stirrer that connects the upper and lower tubes, and its slim tubular structure is suitable for stirring liquids with high viscosity, which can effectively reduce energy loss.

###  Fermenter module

{% include figure.html image="https://static.igem.wiki/teams/5175/resources/hardware/hardware-4-2.webp" caption="Fig 3.2 Fermenter module<br> (A) lower tank variant; (B) upper tank variant" %}

In order to adapt the model to different application scenarios, we have also experimented with some variants of the fermenter. For example, with the help of the relatively stable stabilization in the soil below the shallow layer, we designed the conical lower tank variant shown in 4.2A, which can fix the fermenter inside the soil, maintain a relatively constant incubation temperature, and release the synthesized rhamnolipids directly into the soil. In addition, we can adjust the size or shape of the tank to achieve differentiated cultivation of multiple bacteria. As shown in Fig 4.2B, the columnar top jar is more convenient for fixing multiple sensors to realize real-time monitoring of the growth status of the bacteria.

###  Flow rate control module

{% include figure.html image="https://static.igem.wiki/teams/5175/resources/hardware/hardware-4-3.webp" caption="Fig 3.3 Flow rate control module<br> (A) built-in speed control module; (B) channelized speed control module" %}

For the flow control, we also proposed two schemes. The first (Fig. 4.3A) uses a completely built-in control scheme, where we dig away holes of the same area in three equal-sized circular plates and fasten them together by means of a fixing bar that passes through the center axis. By changing the relative angle of rotation between the three plates, we can vary the flow of liquid and thus control the reaction rate. The second type of speed control module (Fig. 4.3B) can be connected directly to external piping and has two parts to realize the assembly, one side is threaded to the channel or tank and the other can be rotated to change the area of the sector where the two overlap to achieve control of the fluid flow rate.

###  Temperature control module

{% include figure.html image="https://static.igem.wiki/teams/5175/resources/hardware/hardware-4-4.webp" caption="Fig 3.4 Temperature control module<br> (A) straight heat exchanger tube; (B) spiral heat exchanger tube" %}

Our current fermenter needs to control the culture medium at a constant temperature of 37 degrees Celsius for further temperature regulation. To further improve the robustness of the temperature control system, we supplemented two different structures of cooling tubes to achieve the stabilization of the culture temperature in the tank through heat exchange. The straight heat exchanger tube shown in Fig 4.4A, where the water flows in from the lower tube and out from the upper tube, and the middle vertical tube enlarges the contact area with the fermentation broth to help realize the heat exchange. The spiral heat exchanger tube in Fig 4.4B, on the other hand, allows for a spiral cylindrical water pipe to be coiled at the center shaft pipe to achieve temperature regulation of the fermentation broth in the tank. 

###  Irrigation module

After *P. Putida* synthesizes rhamnolipids in the lower tank, we need to release them into the environment to achieve our fertility-enhancing effects. Therefore, we have designed the following types of irrigation nozzles for different application scenarios and requirements.

{% include figure.html image="https://static.igem.wiki/teams/5175/resources/hardware/hardware-4-5.webp" caption="Fig 3.5 Irrigation module<br> (A) sprinkler head<br> (B) pressurized sprinkler head:<br> (a) side top view of sprinkler head; (b) cross section view of sprinkler head;<br> (C) drip irrigation head" %}

Spray cans utilize spray nozzles to achieve a greater atmosphere of watering and coverage, and we have designed two types of spray nozzles for sprinkler irrigation. The sprinkler head shown in Fig 4.5A is similar to a showerhead in that the number and size of the fine holes at the bottom can be controlled to meet different irrigation speeds and coverage. Based on this, we further propose the pressurized sprinkler head (Fig. 4.5B(a, b)), which is internally supplemented with channels spreading from the center to the periphery, and the diameter of the channels ranges from large to small from the center to the periphery to achieve the acceleration of the liquid in order to expand the irrigation range and achieve higher irrigation efficiency.

Compared to sprinkler irrigation, drip irrigation can save water while inhibiting weed growth to a certain extent, and realize precise irrigation, so we also supplemented the drip irrigation head. The drip irrigation sprinkler head (Fig. 4.5C) is overall a long straight pipe with many small holes drilled into it to allow the liquid to flow out, and the length and bifurcation of the pipe can be adjusted according to irrigation needs. This type of irrigation meets the development needs of our green agriculture and also expands the scenarios that the system should be used for.

## Future

{% include figure.html image="https://static.igem.wiki/teams/5175/resources/hardware/hardware-5-1.webp" caption="Fig 4.1 Bidirectional flow temperature control system" %}

In order to ensure the optimal growth of the two bacteria in the fermenter, we designed a two-way flow temperature control system (Fig 5.1). After completing the design and 3D printing the fermenter, we've conducted some initial testing, including testing for water resistance and verifying the key functions of agitation and flow control. However, due to time constraints, this part of the work still needs to be improved in order to realize automated control. We plan to add a level sensor in the upper tank to detect the height of the fermentation liquid level in the upper tank; supplement the temperature sensor in the lower tank to monitor the temperature TL in the tank in real time; and also add a valve to control Q0 at the medium entry port of the upper tank, and supplement the control element at the top cover of the upper tank to realize the automated rotation of the kit b. We designed the temperature control process as follows:

  1. First, we in the upper tank medium entry port, stable replenishment of 37 °C culture fluid, baffle c is in an open state, the middle layer of samples to be treated through, on the upper tank flow down the culture fluid cooling, and then jointly into the lower tank; 
  2. When the detection of the TL is lower than the minimum of the set temperature interval (25-30 °C), the top cover control element drives the baffle c up, Q1 increases, to help the TL effectively rise; conversely, when the When TL is detected to be higher than the set temperature range, the control element drives the baffle c down and TL down; 
  3. In order to prevent the liquid in the upper tank from entering the lower tank by the hollow pipeline, the water level height is detected with the help of the level sensor, if the water level is higher than the control line, the valve is adjusted and the baffle c is lifted up to control the Q0 down and the Q1 up until the water level reaches the safety line.

Co-cultivation of multiple bacteria is becoming more and more common in synthetic biology, and how to realize the cultivation of different strains of bacteria at different optimal temperatures is still a major challenge to be solved in the current hardware design. We hope to provide new ideas for hardware design in synthetic biology through this bi-directional flow temperature control system.

---

## References

[^1]: DAVIES C D, CROOKS R M. Focusing, sorting, and separating microplastics by serial faradaic ion concentration polarization [J]. Chemical Science, 2020, 11(21): 5547-58.
[^2]: SUN Z, MA C, YU C, LI Z. Microplastic separation and enrichment in microchannels under derivative electric field gradient by bipolar electrode reactions [J]. Scientific Reports, 2024, 14(1): 4626.
[^3]: TONG H, JIANG Q, HU X, ZHONG X. Occurrence and identification of microplastics in tap water from China [J]. Chemosphere, 2020, 252: 126493.