# Alcoholímetro
Instrumento de evaluación 

# Alcolímetro Inteligente

## Descripción del Proyecto

El proyecto consiste en desarrollar un alcolímetro inteligente que utiliza un sensor de alcohol MQ-3 y un sensor de temperatura para determinar la ingesta de alcohol al igual que también medir su temperatura corporal. Esta proyecto tiene como objetivo principal proporcionar una herramienta precisa y eficiente para realizar pruebas de alcoholemia y control de temperatura de los estudiantes un dia despues de una fiesta.

## Integrantes

- Mayra Alejandra Galvan Garcia
- Luis Oswaldo Rodriguez Lopez

## Materiales a Utilizar

| Nombre del Componente | Descripción | Cantidad | Precio |
|-----------------------|-------------|----------|--------|
| Sensor de Alcohol MQ-3 | Sensor para detectar concentraciones de alcohol en el aire | 1 | $75.00 |
| Sensor de Temperatura | Sensor para medir la temperatura corporal de los usuarios | 1 | $55.00 |
| Arduino Uno | Plataforma de desarrollo para la programación de microcontroladores | 1 | $0.00 |
| Cables Dupont | Cables para conexión de prototipos de pruebas | 50 | $60.00 |
| Buzzer | Dispositivo para emitir sonidos | 1 | $25.00 |

## Software a Utilizar

| Nombre | Versión | Tipo de Software |
|--------|---------|------------------|
| Arduino IDE | 1.8.15 | Software Libre |
| Mosquitto | 2.0.14 | Broker MQTT de código abierto |
| Node-RED | 2.0.6 | Software de código abierto para la integración de sistemas |
| SQL Server | 2019 | Sistema de gestión de bases de datos relacional |

## Prototipo en Dibujo![Captura de pantalla 2024-03-20 185754](https://github.com/Luisgatovolador/iot-alcohol-metro/assets/116209151/1336706d-e403-45a7-8991-d46ba7d779fb)


- Fotografía de un dibujo a mano alzada del alcolímetro inteligente  
![WhatsApp Image 2024-03-20 at 7 07 17 PM](https://github.com/Luisgatovolador/iot-alcohol-metro/assets/116209151/ca4231c2-365a-4f4e-86fb-7dc87beef9a7)




## Diagrama

La arquitectura del sistema incluye el sensor de alcohol MQ-3, el sensor de temperatura, el microcontrolador Arduino Uno y el buzzer.

![Arquitectura del Sistema](https://example.com/path/to/architecture_diagram.jpg)

## Base de Datos

Se utilizará SQL Server como sistema de gestión de bases de datos

```sql
-- Tabla para almacenar lecturas del sensor de alcohol MQ-3

CREATE TABLE Alcohol (
    id INT PRIMARY KEY IDENTITY(1,1),
    valor FLOAT,
    fecha DATETIME DEFAULT GETDATE()
);

-- Tabla para almacenar lecturas del sensor de temperatura
CREATE TABLE Temperatura (
    id INT PRIMARY KEY IDENTITY(1,1),
    valor FLOAT,
    fecha DATETIME DEFAULT GETDATE()
);

-- Tabla para almacenar registros de detección de alcohol
CREATE TABLE DeteccionAlcohol (
    id INT PRIMARY KEY IDENTITY(1,1),
    id_alcohol INT,
    id_temperatura INT,
    fecha DATETIME DEFAULT GETDATE(),
    FOREIGN KEY (id_alcohol) REFERENCES Alcohol(id),
    FOREIGN KEY (id_temperatura) REFERENCES Temperatura(id)
);
```

## Codigo

## Comunicación

La comunicación con el alcolímetro inteligente se realizará a través de una aplicación móvil. Los usuarios podrán visualizar los resultados de las pruebas de alcoholemia y temperatura en tiempo real mediante la conexión Bluetooth con la aplicación.**

