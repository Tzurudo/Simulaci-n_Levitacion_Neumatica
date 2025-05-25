# Simulación de Levitación Neumática

Este proyecto presenta una simulación del fenómeno de **levitación neumática** de una esfera ligera dentro de un tubo vertical, utilizando MATLAB. El sistema modela la interacción entre la esfera y un flujo ascendente de aire, considerando fuerzas como la gravedad y el arrastre aerodinámico.

## 📘 Descripción General

El archivo `SMN.m` contiene una simulación basada en métodos numéricos, utilizando el solver `ODE45` de MATLAB, para calcular la posición y velocidad de una esfera en un tubo con flujo de aire vertical. El objetivo es observar cómo la esfera alcanza una **altura de equilibrio** debido al empuje del aire.

### Características principales:
- Simulación física detallada del sistema esfera–flujo de aire.
- Cálculo en tiempo real de las principales fuerzas actuantes: gravedad y arrastre.
- Visualización gráfica de la evolución temporal de la altura y la velocidad de la esfera.
- Animación del movimiento de la esfera dentro del tubo.

## ⚙️ Parámetros del Sistema

| Parámetro               | Valor         | Unidad     |
|------------------------|---------------|------------|
| Masa de la esfera      | 0.1           | kg         |
| Radio de la esfera     | 0.015         | m          |
| Densidad del aire      | 1.225         | kg/m³      |
| Coeficiente de arrastre| 4             | —          |
| Diámetro del tubo      | 0.047         | m          |
| Tiempo de simulación   | 30            | s          |

> Puedes modificar estos parámetros directamente en el script `SMN.m` para analizar distintos escenarios del sistema.

## 💻 Requisitos

- **MATLAB** (versión recomendada: R2016a o superior)
- No requiere toolboxes adicionales

## ▶️ Instrucciones de Uso

1. Descarga el archivo [`SMN.m`](./SMN.m).
2. Abre MATLAB y navega hasta el directorio donde se encuentra el archivo.
3. Ejecuta el script escribiendo en la consola:
   ```matlab
   SMN
