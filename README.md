# Inductor Design and Characterization Lab

## Overview 

In this the lab, we fabricated an inductor that we designed and verified that it met the design specifications which were as followed:
- 200 μH inductance ±5 percent
- 2 A dc current
- Current to saturate at 100 degrees C: 3 A (minimum)
- 0.40 W maximum power dissipation
- Operating at 10 kHz

We conducted tests to measure the DC resistance and inductance of our inductor at various operating points to verify if it met the specifications.

## Materials 

- 495-5429-ND Core (E25 Core, N27 material)
- 495-5375-ND Bobbin 
- Magnet wire (#20 AWG copper wire)
- Gapping material (paper)
- Analog Discovery 
- Impedance Analyzer for Analog Discovery
- Auxiliary inductor (5 mH)
- USB isolator module
- Thermal camera

## Background Calculations 

We chose the 495-5429-ND E25 core with N27 material. For N27 material, Bsat = 410mT when temperature T = 100°C and frequency f  = 10kHz.

The volume of the gap is given by the equation:
Vg = u_o * L * (I_max)^2 / B_max^2 = 4πx10^−7*210μH*(2A)^2 / (410mT)^2 = 6.28x10^−9 m^3 for our operating DC current, magnetic field, and desired inductance. 

From the specification for the E25 core, the cross-sectional area is Ac = 52.5mm^2 = 52.5x10^−6 m^2. 
Dividing the desired Vg by our specified cross-sectional area, we got that our desired gap length was lg = 1.19 ∗ 10^−4 m.

For the desired inductance and given dimensions, we calculated the number of turns necessary, with N = sqrt(L*lg/u_o*A_c) to get a minimum of 19.4 turns. 

We rounded up to 20 turns, given a window area of 56.99mm^2 in the core and a packing factor of 0.4. The max bare area of the wire was A_w * 0.4 /N = 56.9 mm^2 * 0.4 / 20 = 0.0138cm^2.

We choose a #20 AWG wire with bare area .005188cm^2. For the #20 AWG wire and given average length per turn from the E25 core datasheet, the resistance of the coil is calculated to be 33.23 * 10^−6 Ω/mm ∗ 20 turns ∗ 50mm/turn = 0.0332 ohms. 

We checked for power with the equation, P = I^2R. At this calculated resistance and max power dissipation of 0.4 W, the max current is 3.47 A. Thus, a minimum saturation current of 3 A is reasonable.

In summary, we used the core 495-5429-ND E25 core, N27 material, bobbin 495-5375-ND, a #20 AWG wire, had 20 turns, and a gap size of 1.19 ∗ 10−4 m. 

## Fabrication

The coil was winded (20 turns) on the plastic bobbin according to design. The insulation was scraped off the ends to make a good connection. The core was assembled with gapping material (paper) to achieve the designed gap size of 1.19 * 10^-4 m. Since there were two gaps, the length of one gap was approximately 0.6 * 10^04 m, so one sheet of paper was used because of its 0.05 mm thickness. We cut the paper and placed it between the 495-5429-ND E25 cores. We then wrapped Kapton tape around the core and bobbins to hold the inductor together. Lastly, we scraped the insulation off the ends of the terminals.

![IMG_2509](https://user-images.githubusercontent.com/71578472/165446006-2bb56abd-e7bf-4a3e-b97c-0c6fa25d3058.jpeg)

Figure 1: Inductor designed with 495-5429-ND Core (E25 Core, N27 material), 495-5375-ND Bobbin, and #20 AWG copper wire scaled with nickel.

## Results 

### Characterization

The Impedance Analyzer was used for Analog Discovery to measure the inductance and resistance of our inductor. The Digilent Waveforms software was downloaded and installed. The Analog Discovery was then connected to our computer using the USB isolator module, which protected our computer from unwanted overvoltages and overcurrents. The Impedance Analyzer for Analog Discovery measured the impedance of two port elements. DC resistance and inductance was measured using the Analog Discovery. 

#### DC Resistance 

The DC resistance was measured with respect to frequency using the Impedance Analyzer for Analog Discovery. An USB isolator module was used to protect our computer from the unwanted overvoltages and overcurrents. At 0 Hz, the DC resistance was around 0.0332 ohms. 

However, at higher frequencies, the current traveled through a smaller cross-sectional area of the wire. The physical result of this was that the impedance increased as the frequency increased. This phenomenon is known as the skin effect and happens as the current flows closer to the surface of the wire.

<img width="499" alt="Screen Shot 2022-05-09 at 6 21 22 PM" src="https://user-images.githubusercontent.com/71578472/167523752-76f93da4-6ad1-4413-8995-a387c15aa688.png">


#### Inductance 

The inductance was measured with respect to frequency using the Impedance Analyzer for Analog discovery.

![inductance](https://user-images.githubusercontent.com/71578472/165452239-1d6de2c8-e705-4029-8dca-95cc943c3d2f.jpeg)


<img width="497" alt="Screen Shot 2022-05-09 at 6 33 00 PM" src="https://user-images.githubusercontent.com/71578472/167524858-c482c14f-7ef8-434f-99d3-9c0d25dfa3cf.png">

Figures: Inductance varying with frequency with a current of 0 A.

The inductance increased with frequency as expected. This happens because the current flowing through the coils induces a magnetic field which causes a back emf voltage opposing the current flow. This relationship is given by the equation V = L di/dt. The higher the frequency, the higher the rate of change of the current,the higher the back emf voltage, leading to a higher inductance.

#### Measuring inductance with a superimposed DC current

The test setup diagrammed in the figure below was used to measure the inductance with the superimposed DC current between 0 and 3 A. The auxiliary inductor was used to decouple the LCR meter measurement from the power supply, which can interfere with the inductance measurement. 


<img width="615" alt="Screen Shot 2022-04-26 at 11 11 50 PM" src="https://user-images.githubusercontent.com/71578472/165452821-d2fa217b-6890-4ca6-b083-1d60a9d8233a.png">

Figure 2: Test setup used for measuring inductance with a superimposed DC current. The ‘LCR Meter’ represents the Impedance Analyzer for Analog Discovery. The auxiliary inductor is a 5 mH inductor that serves to block off any AC current. 

The inductance was measured at different values of DC current. Sample plots are included below.

Inductance with 0 A DC current

<img width="499" alt="Screen Shot 2022-05-09 at 6 50 35 PM" src="https://user-images.githubusercontent.com/71578472/167526472-d4ebc844-0738-4ae7-b49f-122d65961251.png">

Inductance with 1 A DC current

<img width="498" alt="Screen Shot 2022-05-09 at 6 52 50 PM" src="https://user-images.githubusercontent.com/71578472/167526677-b49c81ac-a2aa-48cf-9edd-ab87abee87da.png">

Inductance with 1.5 A DC current

<img width="498" alt="Screen Shot 2022-05-09 at 6 54 00 PM" src="https://user-images.githubusercontent.com/71578472/167526770-d3e8f2d7-b6ae-4906-9f00-b9048524bfed.png">

Inductance with 2 A DC current

<img width="498" alt="Screen Shot 2022-05-09 at 6 54 54 PM" src="https://user-images.githubusercontent.com/71578472/167526849-3a788f3c-5d20-4d73-b73f-d1c65a5b8d53.png">

Inductance with 2.5 A DC current

<img width="497" alt="Screen Shot 2022-05-09 at 6 55 41 PM" src="https://user-images.githubusercontent.com/71578472/167526924-f8d3a0dc-436a-40a8-b2e6-2eae652aa1ef.png">


Inductance with 3 A DC current

<img width="498" alt="Screen Shot 2022-05-09 at 6 56 06 PM" src="https://user-images.githubusercontent.com/71578472/167526977-3d407e41-15c0-4214-9e06-7b6d2ea01795.png">





