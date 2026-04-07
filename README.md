# EVALUATION-OF-RADAR-RANGE-USING-PYTHON-

__Aim__:

To calculate the maximum range of a radar system using the Radar Range Equation and verify the results 
through Python programming.

__Theory__:

The Radar Range Equation is a fundamental formula used in radar system design to determine the maximum 
range at which a radar can detect a target. It is given by:

<img width="573" height="442" alt="image" src="https://github.com/user-attachments/assets/ba374d30-d11f-41e5-a4fc-a42dde71d8e7" />

__Procedure__:

1. Set Up the Python Environment: Ensure that Python is installed on your system. You can use 
Anaconda for managing Python packages and environments, or any other Python IDE of your choice. 
2. Import Necessary Libraries: Import the math library in Python. 
3. Define the Radar Range Equation Function: Create a function to calculate the maximum range using 
the Radar Range Equation. 
4. Input Parameters for the Radar System: Define the input parameters such as transmitted power, 
transmitter gain, receiver gain, radar frequency, radar cross section, and minimum detectable power. 
5. Calculate the Maximum Range: Use the function to calculate the maximum range of the radar. 
6. Execute the Program: Run the Python script to calculate and display the maximum range of the radar.


   ___Algorithm__:
   Define constants: Pt, Gt, Gr, λ, σ, Pmin
   
   Use Radar Range Equation to compute Rmax
   
   Vary parameters (Pt, Gt, Pmin)
   
   Plot Rmax against each parameter
   
   Analyze variation

__Program__:
```
clc;
clear;

// Given values
Gt = 6;
Gr = 7;
w = 8;
sigma = 9;
Pmin = 1e-9;

// -------- Case 1: Vary Pt --------
Pt = 0.5:0.5:100;

Rmax1 = ((Pt .* Gt .* Gr .* (w^2) .* sigma) ./ ((4 * %pi)^3 * Pmin)).^(1/4);

subplot(3,1,1);
plot(Pt, Rmax1);
xtitle("Rmax vs Pt");
xgrid();

// -------- Case 2: Vary Gt --------
Pt = 20;
Gt = 0.1:0.1:9;

Rmax2 = ((Pt .* Gt .* Gr .* (w^2) .* sigma) ./ ((4 * %pi)^3 * Pmin)).^(1/4);

subplot(3,1,2);
plot(Gt, Rmax2);
xtitle("Rmax vs Gt");
xgrid();

// -------- Case 3: Vary Pmin --------
Gt = 7;
Pmin = [1e-14 1e-13 1e-12 1e-11 1e-10 1e-9];

Rmax3 = ((Pt .* Gt .* Gr .* (w^2) .* sigma) ./ ((4 * %pi)^3 .* Pmin)).^(1/4);

subplot(3,1,3);
plot(Pmin, Rmax3);
xtitle("Rmax vs Pmin");
xgrid();
```

   __Output graph__:
   
<img width="610" height="460" alt="image" src="https://github.com/user-attachments/assets/1a0bee44-f964-42b3-9792-8b5a3c9f1ca7" />


   __Tabulation__:

<img width="1076" height="1548" alt="image" src="https://github.com/user-attachments/assets/36c34002-0532-450a-90ec-ab2c458dd41e" />




   __Result__:
   
<img width="1464" height="928" alt="image" src="https://github.com/user-attachments/assets/01d69a0a-cd34-43c0-9dd5-520f6ba8a92a" />




