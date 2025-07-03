clc;
clear;

disp('--- Continuous-Time Basic Signals ---');

T = input('Enter time range limit : ');

t = -T:0.01:T;

delta = (t == 0);  

% Unit Step Signal: u(t)
u = double(t >= 0);

% Unit Ramp Signal: r(t)
r = t .* (t >= 0);

% Unit Parabolic Signal: p(t) = 0.5 * t^2 for t >= 0
p = 0.5 * (t.^2) .* (t >= 0);

% Plot all signals in subplots

figure;

% 1. Unit Impulse
subplot(4,1,1);
stem(t, delta, 'filled', 'r');
title('Unit Impulse Signal \delta(t)');
xlabel('time(seconds)'); ylabel('unit impulse');
grid on; ylim([0 1.2]);

% 2. Unit Step
subplot(4,1,2);
plot(t, u, 'b', 'LineWidth', 2);
title('Unit Step Signal u(t)');
xlabel('time(seconds)'); ylabel('unit step');
grid on; ylim([-0.2 1.2]);

% 3. Unit Ramp
subplot(4,1,3);
plot(t, r, 'g', 'LineWidth', 2);
title('Unit Ramp Signal r(t)');
xlabel('time(seconds)'); ylabel('unit ramp');
grid on;

% 4. Unit Parabolic
subplot(4,1,4);
plot(t, p, 'm', 'LineWidth', 2);
title('Unit Parabolic Signal p(t)');
xlabel('time(seconds)'); ylabel('unit parabolic');
grid on;

# basic-signal-in-MATLAB
