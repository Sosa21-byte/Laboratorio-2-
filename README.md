# Laboratorio 2 – Interacción Inicial con el Robot Pepper

Este laboratorio documenta la primera interacción con el robot **Pepper** en el salón de robótica. Se investigaron librerías clave, se utilizó el software **Choregraphe** para crear una coreografía sencilla y se accedió al robot mediante **SSH** para programar un movimiento básico con Python.

---

## 🔧 Librerías investigadas

- **qi**: Comunicación con los servicios de NAOqi (framework de Pepper).  
- **argparse**: Manejo de argumentos desde consola.  
- **sys**: Acceso a variables y funciones del intérprete de Python.  
- **os**: Funciones del sistema operativo (directorios, procesos, etc.).  
- **almath**: Operaciones matemáticas avanzadas para robótica.  
- **math**: Funciones matemáticas estándar.  
- **motion**: Control de movimientos y posturas del robot.  
- **httplib**: Comunicación HTTP con servicios externos.  
- **json**: Manejo de datos en formato JSON.  

---

## 🖥️ Instalación y uso de Choregraphe

1. Instalar **Choregraphe** desde la página oficial de SoftBank Robotics.  
2. Conectar Pepper y el PC a la misma red.  
3. Configurar la IP del robot en Choregraphe.  
4. Crear una secuencia simple (ejemplo: saludo moviendo brazos).  
5. Probar en el simulador y luego ejecutar en el robot real.  

---

## 🔑 Acceso mediante SSH

1. Abrir la terminal en Linux/Mac o PowerShell en Windows.  
2. Conectarse al robot:  
   ```bash
   ssh nao@ip_Pepper
