%% README file for Supplemental File 3 | Code for calculation of setpoints
% Code was written by Prof Brody H Foy. Contact: brodyfoy@uw.edu

%% Code takes in two inputs:
% x | The timing of each patient measurement, expressed in days
% y | The value of the marker at each timepoint in x

% It then fits a multi-component Gaussian mixture model (up to 3 components)
% to estimate the patient setpoint, and associated coefficient of variation (CV). 
%
% The function returns two outputs:
% setpoint | The estimate of the setpoint of the the x + y data
% setpoint_cv | The associated CV estimate
%
% Given reliance on protected health information, actual patient data cannot be shared.
% Instead we share an artificial dataset ('Toy data.xlsx') designed to resemble
% typical patient data for platelet count
%
% The code is written in MATLAB, and should work on any version of MATLAB with the
% 'Statistics and Machine Learning Toolbox' installed. To run the code, excude the
% following two commands: 
Data = readtable('Toy data.xlsx'); 
[setpoint, setpoint_cv] = CalculateSetpoint(Data.x, Data.y); 

% This should output the following answers: 
setpoint = 309.4167
setpoint_cv = 0.0612

% Note that by default, CV is expressed as a decimal percentage (i.e., the above is 6.12%). 

% The code is provided under fully free license for any purpose. The code is provided as an
% explanation of a statistical analysis in its associated paper, and is for research purposes
% only. The authors make no claims of accuracy or performance of any aspect of the code, and 
% are not liable for any damages resulting from use of the code in any setting. 
%
% For any questions related to the code, please contact Dr Brody H Foy: brodyfoy@uw.edu  