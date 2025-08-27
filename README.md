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
Crear un script en Python con nano movimiento.py.

Ejecutar el código en el robot.

🤖 Ejemplo de código en Python
import qi, argparse, sys, almath, motion

def main(session):
    motion_service = session.service("ALMotion")
    posture_service = session.service("ALRobotPosture")
    posture_service.goToPosture("StandInit", 0.5)

    # Movimiento sencillo de brazo
    names  = ["LShoulderPitch"]
    angles = [50*almath.TO_RAD]
    motion_service.setAngles(names, angles, 0.2)

if __name__ == "__main__":
    parser = argparse.ArgumentParser()
    parser.add_argument("--ip", type=str, default="127.0.0.1")
    parser.add_argument("--port", type=int, default=9559)
    args = parser.parse_args()

    connection_url = "tcp://{}:{}".format(args.ip, args.port)
    app = qi.Application(["Example", "--qi-url=" + connection_url])
    app.start()
    main(app.session)

✅ Conclusiones

Se comprendió la utilidad de las librerías básicas para la programación en Pepper.

Se logró ejecutar una coreografía sencilla en Choregraphe.

Se verificó la conexión mediante SSH y la ejecución de un script en Python.
