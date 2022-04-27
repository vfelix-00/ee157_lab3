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
- Analog Discovery and Impedance Analyzer for Analog Discovery
- Auxiliary inductor (5 mH)
- USB isolator module
- Thermal camera

## Fabrication

The coil was winded (20 turns) on the plastic bobbin according to design. The insulation was scraped off the ends to make a good connection. The core was assembled with gapping material (paper) to achieve the designed gap size of 1.19 * 10^-4 m. Since there were two gaps, the length of one gap was approximately 0.6 * 10^04 m, so one sheet of paper was used because of it's 0.05 mm thickness. Tape was used to hold it together. 

![IMG_2509](https://user-images.githubusercontent.com/71578472/165446006-2bb56abd-e7bf-4a3e-b97c-0c6fa25d3058.jpeg)

Figure 1: Inductor designed with 495-5429-ND Core (E25 Core, N27 material), 495-5375-ND Bobbin, and #20 AWG copper wire scaled with nickel.

## Results 

### Characterization

The Impedance Analyzer was used for Analog Discovery to measure the inductance and resistance of our inductor. The Digilent Waveforms software was downloaded and installed. The Analog Discovery was then connected to our computer using the USB isolator module, which protected our computer from unwanted overvoltages and overcurrents. The Impedance Analyzer for Analog Discovery measured the impedance of two port elements. DC resistance and inductance was measured using the Analog Discovery. 

#### DC Resistance 

#### Inductance 

![inductance](https://user-images.githubusercontent.com/71578472/165452239-1d6de2c8-e705-4029-8dca-95cc943c3d2f.jpeg)

#### Measuring inductance with a superimposed DC current

The test setup diagrammed in Fig. 1 was used to measure the inductance with the superimposed DC current between 0 and 3 A. The auxiliary inductor was used to decouple the LCR meter measurement from the power supply, which can interfere with the inductance measurement. 


<img width="615" alt="Screen Shot 2022-04-26 at 11 11 50 PM" src="https://user-images.githubusercontent.com/71578472/165452821-d2fa217b-6890-4ca6-b083-1d60a9d8233a.png">

Figure 1: Test setup used for measuring inductance with a superimposed DC current. The ‘LCR Meter’ represents the Impedance Analyzer for Analog Discovery.

