El módulo `bright_control` implementa el PWM para controlar el brillo de los LEDs RGB.

En el archivo `bright_control.cpp` se definen los pines de salida digital que se utilizan para el manejo de los LEDs:

```cpp
    PwmOut RGBLed[] = {(PB_4), (PA_0), (PD_12)};
```

# Implementación del PWM
Para implementar el PWM hace uso los generadores de PWM del microcontrolador. Notar que se utilizan los objetos de mbed PwmOut.

La implementación se encarga de actualizar los pines de salida de acuerdo con el valor de duty cycle establecido. Se nota que mejora la resolución respecto del ejemplo 8.1 al no utilizar un ticker y 
permitir establecer el duty cycle con números flotantes.


# Árbol de funciones

brightControlInit()
    ├── setPeriod()
    └── setDutyCycle()

setDutyCycle()
    └── mbed (library) para el manejo de los PWMs.

setPeriod()
    └── mbed (library) para el manejo de los PWMs.

El PWM se actualiza automáticamente y no requiere de llamar una función update() en el módulo, solo su inicialización.