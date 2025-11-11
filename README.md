# EXP 1 A : COMPUTATION OF DFT USING DIRECT AND FFT

# AIM: 

# To Obtain DFT and FFT of a given sequence in SCILAB. 

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 
# DFT:

clc; 
clear; 
xn=[1 2 3 4 4 3 2 1]; 
 
n1=0:1:length(xn)-1; 
subplot(3,1,1); 
plot2d3(n1,xn); 
xlabel('Time n'); 
ylabel('Amplitude xn'); 
title('Input Sequence'); 
j=sqrt(-1); 
N=length(xn); 
Xk=zeros(1,N); 
for k=0:N-1 
for n=0:N-1 
Xk(k+1)=Xk(k+1)+xn(n+1)exp((-j*2%pi*k*n)/N); 
end   
end 
disp(Xk) 
K1=0:1:length(Xk)-1; 
magnitude=abs(Xk) 
subplot(3,1,2); 
plot2d3(K1,magnitude); 
xlabel('frequency(Hz)'); 
ylabel('magnitude(gain)'); 
title('magnitude spectrum'); 
angle = atan(imag(Xk),real(Xk)) 
subplot(3,1,3); 
plot2d3(K1,angle); 
xlabel('frequency(Hz)'); 
ylabel('Phase'); 
title('Phase spectrum');

# FFT:

clear; 
clc; 
close; 
xn = [0.5 0.5 0.5 0.5 0 0 0 0] 
 
n1=0:1:length(xn)-1; 
subplot(2,2,1); 
plot2d3(n1,xn); 
xlabel('Time n'); 
ylabel('Amplitude'); 
title('Input Sequence'); 
 
Xk = fft(xn); 
 
K1=0:1:length(Xk)-1; 
magnitude=abs(Xk) 
subplot(2,2,2); 
plot2d3(K1,magnitude); 
xlabel('frequency(Hz)'); 
ylabel('magnitude(gain)'); 
title('magnitude spectrum'); 
angle = atan(imag(Xk),real(Xk)) 
subplot(2,2,3); 
plot2d3(K1,angle); 
xlabel('frequency(Hz)'); 
ylabel('Phase'); 
title('Phase spectrum') 
y= ifft(Xk) 
 
n2=0:1:length(y)-1; 
subplot(2,2,4) 
plot2d3(n2,y) 
xlabel('Time n'); 
ylabel('Amplitude'); 
title('Inverse FFT OF X(K)');




# OUTPUT: 
# DFT:
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/045b071f-98ef-411a-a0de-c11535126be2" />

# FFT:
 <img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/eb1118da-8e75-4f52-84fd-95fe02de75e6" />


# RESULT: 
The DFT of the given sequence using Direct method and FFT method are obtained.
