# Analog-Design-of-Asynchronous-SAR-ADC
This project is about the design process of an 8-bit asynchronous successive approximation register (SAR) analog-to-digital converter (ADC) using 45nm CMOS technology. SAR ADCs are attractive circuits for applications that require low power with medium resolution and medium speed like in computing-in-memory cores for AI applications and in sensors for biomedical applications. The asynchronous architecture allow the ADC to operate without the need for an oversampled clock reducing the design complexities associated with higher frequencies. The top-level block diagram of the asynchronous SAR ADC is shown below, along with the timing diagram of the important signals.


![image](https://user-images.githubusercontent.com/27668656/114318830-9ab84580-9ac3-11eb-8a2b-5f896bbff274.png)

![image](https://user-images.githubusercontent.com/27668656/114318889-d94e0000-9ac3-11eb-9388-28e767ae2eee.png)
---------------------------------

### 1) Internal Clock Generator
The internal clock generator is the block responsible for providing the rest of the system with the clock signals to operate. This block produces 2 output signals, “clk_sample” and “clk_sar”, and receives 3 inputs “clk_ext”, “Ready”, and “EOC”.

![image](https://user-images.githubusercontent.com/27668656/114318969-31850200-9ac4-11eb-97dc-1934ef31ac0b.png)
---------------------------------

### 2) Bootstrapped Sample-And-Hold Switches
The sample-and-hold circuit is basically a switch that captures the value of an analog signal at a certain moment and holds it constant for a certain amount of time. The bootstrapped switch help mitigate some of the switch non-idealities by keeping the switch’s VGS fixed during the sampling phase. 

![image](https://user-images.githubusercontent.com/27668656/114319007-6d1fcc00-9ac4-11eb-93b6-e5cae31b35f9.png)
---------------------------------

### 3) Capacitive DAC
The capacitive DAC uses charge redistribution to convert the digital code coming from the SAR logic into the corresponding analog voltage level to be compared by the comparator. 

![image](https://user-images.githubusercontent.com/27668656/114319050-a35d4b80-9ac4-11eb-82e9-c75bdbfd28ec.png)
---------------------------------

### 4) Dynamic Comparator
The comparator’s function is to compare the analog input levels coming from the DAC and to produce a digital output bit (either high or low) representing the result of the comparison. A high-speed low-power strongarm comparator is used. 

![image](https://user-images.githubusercontent.com/27668656/114319490-a0fbf100-9ac6-11eb-9b88-bee932862fe6.png)
---------------------------------

### 5) SAR Logic
The SAR logic generates the digital code for the DAC in each comparison stage. At the end of the conversion cycle, the final digital code is outputted by an output register. The flipflops used are TSPC flipflops with asynchronous set and reset inputs.

![image](https://user-images.githubusercontent.com/27668656/114319769-bfaeb780-9ac7-11eb-83eb-407b34210043.png)
---------------------------------
---------------------------------

## * Analysis & Results:

![image](https://user-images.githubusercontent.com/27668656/114320368-888dd580-9aca-11eb-812a-cc6f0e7eb8e4.png)

![image](https://user-images.githubusercontent.com/27668656/114320459-de627d80-9aca-11eb-967c-09585b8be926.png)

![image](https://user-images.githubusercontent.com/27668656/114320546-25507300-9acb-11eb-9ffc-bc37b3eb29ba.png)

*****************
### Key References:

[1] O. Kardonik, "A study of SAR ADC and implementation of 10-bit asynchronous design," M.S. Thesis, Department of Electrical and Computer Engineering, University of Texas at Austin, 2013.<br/>

[2] P. J. A. Harpe et al., "A 26 uW 8 bit 10 MS/s Asynchronous SAR ADC for Low Energy Radios," IEEE Journal of Solid-State Circuits, vol. 46, no. 7, pp. 1585-1595, July 2011.<br/>

[3] M. Al-Qadasi, A. Alshehri, A. S. Almansouri, T. Al-Attar, and H. Fariborzi, "A High Speed Dynamic StrongARM Latch Comparator," 2018 IEEE 61st International Midwest Symposium on Circuits and Systems (MWSCAS), Windsor, ON, Canada, 2018, pp. 540-541.<br/>

[4] M. Dessouky and A. Kaiser, "Very low-voltage digital-audio Δ∑ modulator with 88-dB dynamic range using local switch bootstrapping," IEEE Journal of Solid-State Circuits, vol. 36, no. 3, pp. 349-355, March 2001.<br/>

*****************
For more info, check the project's report & ppt: ([Report](https://github.com/muhammadaldacher/Analog-Design-of-Asynchronous-SAR-ADC/blob/main/%5BReport%5D%20Design%20of%20a%20Low-Power%20Asynchronous%20SAR%20ADC%20in%2045%20nm%20CMOS%20Technology.pdf)) ([PPT](https://github.com/muhammadaldacher/Analog-Design-of-Asynchronous-SAR-ADC/blob/main/%5BPPT%5D%20Design%20of%20a%20Low-Power%20Asynchronous%20SAR%20ADC%20in%2045%20nm%20CMOS%20Technology.pdf))<br/>

My project on google drive: ([Drive](https://drive.google.com/drive/folders/1zEzuneabBBtgcV0V-nYb4Kvp_cLarDpZ?usp=sharing)) <br/>






