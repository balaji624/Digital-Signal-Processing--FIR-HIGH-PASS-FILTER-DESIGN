# Digital-Signal-Processing--FIR-HIGH-PASS-FILTER-DESIGN
## AIM:
To generate design of High pass FIR digital filter using Window.
## Software Required:
MAT LAB R2012.
## Algorithm:
Step 1: Open MATLAB and Write the program.

Step 2: Read the values of cut off frequency wc.

Step 2: Read the values of Order of the filter N.

Step 3: Find out the desired impulse response of the hIGH Pass filter Coefficient.

Step 4: Find out the windowing sequence.

Step 5: Plot the magnitude spectrum with x-label and y-label with suitable title.

Step 6: Terminate the program.

## PROGRAM: 
```
%Balaji v 212223050008

clc;
close all;
clear all;

% INPUTS
wc = 2*pi/5;
N = 21;

alpha = (N - 1) / 2;
eps = 0.001;

% HIGH PASS FILTER COEFFICIENT
n = 0:1:N-1;
hd = (sin(pi * (n - alpha + eps)) - sin((n - alpha + eps) * wc)) ./  (pi * (n - alpha + eps));

% HANNING WINDOW SEQUENCE
wh = 0.5 - 0.5 * cos((2 * pi * n) / (N - 1));

% WINDOWED FILTER
hn = hd .* wh;

% FREQUENCY RESPONSE
w = 0:0.01:pi;
h = freqz(hn, 1, w);

% PLOT
figure;
plot(w/pi, abs(h), 'b', 'LineWidth', 2);
```

## OUTPUT:
<img width="1919" height="1020" alt="image" src="https://github.com/user-attachments/assets/44d6f633-679b-49c6-a957-a19ece11ac35" />

## RESULT:
![IMG_20260331_212319](https://github.com/user-attachments/assets/76fc2722-b70c-4be6-9ab9-4251b6bb1179)

