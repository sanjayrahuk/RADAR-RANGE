## EVALUATION OF RADAR RANGE USING PYTHON

## Aim:
To calculate the maximum range of a radar system using the Radar Range Equation and verify the results through Python programming.

## Theory:
The Radar Range Equation is a fundamental formula used in radar system design to determine the maximum range at which a radar can detect a target. It is given by:


## Procedure
1.	Set Up the Python Environment: Ensure that Python is installed on your system. You can use Anaconda for managing Python packages and environments, or any other Python IDE of your choice.
2.	Import Necessary Libraries: Import the math library in Python.
3.	Define the Radar Range Equation Function: Create a function to calculate the maximum range using the Radar Range Equation.
4.	Input Parameters for the Radar System: Define the input parameters such as transmitted power, transmitter gain, receiver gain, radar frequency, radar cross section, and minimum detectable power.
5.	Calculate the Maximum Range: Use the function to calculate the maximum range of the radar.
6.	Execute the Program: Run the Python script to calculate and display the maximum range of the radar.


## CODE 
```
clear;
clf();

c = 3e8;
f = 3e9;
lambda = c / f;
G_dB = 30;
G = 10^(G_dB / 10);
sigma = 1;
Pt_fixed = 100e3;
Pr_min = 1e-12;
R = 1000:500:100000;

num1 = Pt_fixed * (G^2) * (lambda^2) * sigma;
den1 = ((4 * %pi)^3) * (R.^4);
Pr = num1 ./ den1;
Pr_dBm = 10 * log10(Pr / 1e-3);

num2 = Pr_min * ((4 * %pi)^3) * (R.^4);
den2 = (G^2) * (lambda^2) * sigma;
Pt_req = num2 ./ den2;
Pt_req_dBW = 10 * log10(Pt_req);

subplot(2, 1, 1);
plot(R / 1000, Pr_dBm, "r-", "linewidth", 2);
xtitle("Received Power vs. Radar Range", "Range (km)", "Received Power (dBm)");
xgrid();

subplot(2, 1, 2);
plot(R / 1000, Pt_req_dBW, "b-", "linewidth", 2);
xtitle("Required Transmitted Power vs. Radar Range", "Range (km)", "Required Transmitted Power (dBW)");
xgrid();
```


## OUTPUT 

<img width="1918" height="1111" alt="image" src="https://github.com/user-attachments/assets/e39d1b6a-93c4-4b6f-aa5e-8a7f849932ff" />


## Result:

Thus, the maximum range of a radar system using the Radar Range Equation is verified through a Python program.
