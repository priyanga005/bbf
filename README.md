% FIR High-Pass Filter Design using Hamming Window
clc;
clear;

% Specifications
fs = 1000;       % Sampling frequency in Hz
fc = 200;        % Cutoff frequency in Hz
N = 51;          % Filter length (odd number for symmetric FIR filter)

% Normalize cutoff frequency
wc = 2 * pi * (fc / fs);  % Digital cutoff frequency (rad/sample)
f_cutoff = fc / (fs / 2); % Normalized cutoff frequency (0 to 1)

% Ideal impulse response (sinc function for LPF)
n = -(N-1)/2:(N-1)/2;       % Symmetric indices
h_ideal = sinc(n) - (wc/pi) * sinc(wc/pi * n);  % High-pass transformation

% Apply Hamming Window
h_hamming = h_ideal .* hamming_win
