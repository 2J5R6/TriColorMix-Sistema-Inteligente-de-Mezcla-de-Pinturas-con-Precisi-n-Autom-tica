# TriColorMix  
### Sistema Inteligente de Mezcla de Pinturas  
**Manual de Usuario – Versión 1.0**

---

![TriColorMix Hero Image](https://images.unsplash.com/photo-1513364776144-60967b0f800f?q=80&w=1080)

---

# 📑 Índice

1. [Introducción](#introducción)  
2. [Características Principales](#características-principales)  
3. [Componentes del Sistema](#componententes-del-sistema)  
4. [Especificaciones Técnicas](#especificaciones-técnicas)  
5. [Instalación y Montaje](#instalación-y-montaje)  
6. [Interfaz de Usuario](#interfaz-de-usuario)  
7. [Modo de Operación](#modo-de-operación)  
8. [Seguridad](#seguridad)  
9. [Mantenimiento](#mantenimiento)  
10. [Solución de Problemas](#solución-de-problemas)  
11. [Diagrama del Sistema](#diagrama-del-sistema)  
12. [Contacto y Soporte](#contacto-y-soporte)

---

# 🟦 Introducción

La **TriColorMix** es una mezcladora de pintura semiautomática diseñada para crear colores personalizados con rapidez y precisión.  
El usuario selecciona un color desde una interfaz gráfica, y el sistema dosifica automáticamente las cantidades necesarias de pintura base (rojo, amarillo y azul), orienta la manguera correcta mediante un servomotor, y mezcla el contenido mediante una pastilla magnética impulsada por un motor DC.

El equipo es portátil, seguro, fácil de limpiar, ecológico y totalmente modular.

---

# 🟩 Características Principales

- 🎨 **Creación automática de colores personalizados**  
- ⚙️ **Bombas peristálticas de precisión** para dosificación  
- 🔄 **Servomotor rotativo** para seleccionar cada manguera  
- 🧲 **Sistema de agitación magnética** mediante motor DC  
- 🖥 **Interfaz gráfica intuitiva** con modos automático y manual  
- 🛑 **Paro de emergencia físico** incluido  
- 🔋 **Batería recargable de 12V** integrada  
- 🧩 **Tanques desmontables** para fácil recarga  
- 📡 **Final de carrera** para activación automática  
- 🔦 Compatibilidad futura con sensor IR para lectura de nivel  

---

# 🟥 Componentes del Sistema

### 🔧 Actuadores
- 3 Bombas peristálticas (Rojo, Amarillo, Azul)  
- 1 Servomotor (orientación de mangueras, pasos de 45°)  
- 1 Motor DC 5V (agitación magnética)  
- Puentes H para control de potencia de las bombas y motor  

### 📡 Sensores
- Final de carrera (activa el sistema al insertar el soporte del vaso)  
- Sensor infrarrojo (futuro para medición de nivel y estado de tanques)  

### 🧠 Microcontrolador
- **ESP32 S3** – Control general del sistema  

### 🔋 Alimentación
- Batería integrada de **12V**  
- Reguladores internos a 5V y 3.3V  

---

# 🟪 Especificaciones Técnicas

| Parámetro | Valor |
|----------|-------|
| Tanques | 3 (rojo, amarillo, azul), desmontables |
| Actuadores | Bombas peristálticas, servomotor, motor DC |
| Microcontrolador | ESP32 S3 |
| Entrada de usuario | Botones, paro de emergencia, interfaz gráfica |
| Alimentación | Batería de 12V |
| Modo | Automático / Manual |
| Activación | Final de carrera |
| Tiempo de mezcla | 5–12 s |
| Capacidad recomendada | 20–150 ml |
| Portabilidad | Sí |

---

# 🟧 Instalación y Montaje

### 1. Fijar Base  
Coloque la TriColorMix sobre una superficie estable y nivelada.

### 2. Montaje de Bombas  
Inserte las tres bombas peristálticas en el soporte vertical y asegúrese de que queden firmes.

### 3. Conectar Mangueras  
Conecte las mangueras a las bombas y selle con la tapa correspondiente.

### 4. Instalar Servomotor  
Monte el servomotor en la parte superior y asegure la pieza que sostiene las mangueras.  
Posiciones sugeridas: **0°**, **45°**, **90°**, **135°**.

### 5. Conexiones Eléctricas (sugeridas)

| Componente | Pin ESP32-S3 |
|-----------|--------------|
| Bomba Roja | GPIO 14 |
| Bomba Azul | GPIO 15 |
| Bomba Amarilla | GPIO 16 |
| Servomotor | GPIO 4 |
| Motor DC (agitación) | GPIO 17 |
| Final de carrera | GPIO 13 |
| Sensor IR | GPIO 2 |

### 6. Inserción de Pastilla Magnética  
Coloque la pastilla magnética dentro del vaso antes del proceso.

---

## 📸 Imagen del Prototipo  


---

# 🟦 Interfaz de Usuario

La interfaz ofrece:

- **Start**
- **Modo Automático / Manual**
- **Seleccionador de color**
- **Paro de Emergencia**
- Indicadores de:
  - Estado de bombas
  - Posición del servomotor
  - Mezclado en progreso
  - Nivel de batería

---

# 🟫 Modo de Operación

### 🟢 1. Inserción del vaso  
El usuario baja el brazo → el final de carrera activa el sistema.

### 🟢 2. Selección del color  
Desde la interfaz gráfica, el usuario selecciona el tono deseado.

### 🟢 3. Dosificación automática  
El algoritmo calcula proporciones y activa las bombas en orden.  
El servomotor gira hacia cada manguera necesaria.

### 🟢 4. Mezclado  
El motor DC gira los imanes → la pastilla magnética mezcla el contenido.

### 🟢 5. Finalización  
La pantalla muestra: **"Mezcla lista"**.

---

# 🟥 Seguridad

⚠ **ADVERTENCIAS IMPORTANTES**

- No introducir manos en la zona del servomotor o el mezclador.  
- No operar sin vaso ni sin pastilla magnética.  
- No sobrellenar los tanques.  
- Usar guantes al manipular pintura.  
- Mantener alejado de niños.  
- El paro de emergencia debe usarse en situaciones de riesgo.

---

# 🟩 Mantenimiento

### 🔄 Frecuencia recomendada  
Cada **300 usos** o según criterio del usuario.

### 🧼 Procedimiento de limpieza

1. Retirar los tanques desmontables.  
2. Lavar con agua tibia y jabón neutro.  
3. Secar completamente antes de reinstalar.  
4. Bombear agua destilada por las mangueras durante 5–10 s.  
5. Limpiar la pastilla magnética.  
6. Revisar fijaciones generales.  
7. Verificar nivel de batería.

---

# 🟥 Solución de Problemas

| Problema | Causa | Solución |
|----------|-------|----------|
| Motor no gira | Batería baja / cable suelto | Revisar batería y conexiones |
| Tanque no vacía | Manguera doblada | Revisar y enderezar |
| Mezcla irregular | Pastilla mal ubicada | Centrar correctamente |
| No inicia ciclo | Final de carrera no detectado | Verificar brazo y sensor |

---

# 🎛 Diagrama del Sistema


---

# 📬 Contacto y Soporte

**Autores:** Julián Andrés Rosas - Juan Manuel Moreno  
**Proyecto académico – Ingeniería Mecatrónica**  
**Universidad Militar Nueva Granada (UMNG)**  
**Año:** 2025  

---
