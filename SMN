
%%  Tzurudo  : ) 

vaire= .3;% Velocidad maxima en (m) 

% Parámetros del sistema

m = 0.1; % masa de la esfera (kg)
g = 9.81; % aceleración debido a la gravedad (m/s^2)
r = 0.015; % radio de la esfera (m)
A_bola = pi * r^2; % área frontal de la esfera (m^2)
rho = 1.225; % densidad del aire (kg/m^3)
C_d = 4; % coeficiente de arrastre

V_aire_max = vaire*100; % Velocidad máxima en porcentaje

% Parámetros del tubo
d_tubo = 0.047; % diámetro del tubo (m)
A_tubo = pi * (d_tubo / 2)^2; % área del tubo (m^2)

% Parámetros de la simulación
t_final = 30; % tiempo de simulación (segundos)
y0 = 0; % posición inicial (m)
v0 = 0; % velocidad inicial (m/s)

% Función para calcular la velocidad del aire en función de la altura
V_aire = @(z) max(0, V_aire_max * (1 - z)); % Velocidad del aire depende de la altura (no negativa)

% Sistema de ecuaciones diferenciales
f = @(t, y) [y(2); 
    (1/2) * C_d * rho * A_bola * (V_aire(y(1)) - y(2))^2 / m - g]; % [dy/dt; dv/dt]

% Resolver la ecuación diferencial usando ode45
[t, sol] = ode45(f, [0 t_final], [y0, v0]);

% Extraer la posición y la velocidad
y = sol(:, 1); % posición de la esfera
v = sol(:, 2); % velocidad de la esfera

% Limitar la altura máxima del tubo a 0.25 m
y(y > 0.32) = 0.32;

% Gráficos de resultados
figure;
subplot(2, 1, 1);
plot(t, y);
title('Altura vs Tiempo');
xlabel('Tiempo (s)');
ylabel('Altura (m)');


subplot(2, 1, 2);
plot(t, v); 
title('Velocidad vs Tiempo');
xlabel('Tiempo (s)');
ylabel('Velocidad (m/s)');


% Animación de la esfera
figure;
axis([-.2 d_tubo+.2  -0.1 max(y) + 0.05]); % Ajuste dinámico de los límites para la animación
hold on;
xlabel('Posición (m)');
ylabel('Altura (m)');
title('Simulación de Levitation Neumática');

% Graficar la esfera en su posición inicial
h = plot((d_tubo/2), y(1), 'o', 'MarkerSize', 20, 'MarkerFaceColor', 'b');

hold on
%Tubo
plot([d_tubo , 0], [0, 0], 'k-', 'LineWidth', 2); % Línea fondo tubo
plot([0, 0], [0, max(y)], 'k-', 'LineWidth', 2); % Lineadere
plot([d_tubo, d_tubo], [0, max(y)], 'k-', 'LineWidth', 2); % Línea izq
%Ventilacion


% Animación
for i = 1:length(t)
    % Actualizamos la posición de la esfera
    set(h, 'YData', y(i));
    drawnow;
    pause(0.05); % Pausa para la animación
end

% Resultado final
disp(['Altura final de la esfera: ', num2str(y(end)), ' m']);
