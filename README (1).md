# Invernadero en observación

Parcial 2 – Programación I

Programa que registra las lecturas de temperatura y humedad de un invernadero de fresas, decide en qué estado está el cultivo y muestra un resultado final con mínimos, máximos, promedios y las secuencias de lecturas.

## Integrantes

- [Nombre del integrante 1]
- [Nombre del integrante 2]
- [Nombre del integrante 3]

## Información del curso

| Dato | Información |
| --- | --- |
| Asignatura | Programación I |
| Docente | Carlos Carrascal |
| Universidad | [Universidad] |
| Fecha | Octubre de 2026 |

## Video explicativo

[Enlace al video](https://enlaceAlVideo)

## Cómo funciona

El programa pide la temperatura y la humedad de cada lectura y las valida. Si algún valor está fuera del rango válido del sensor, muestra «Dato inválido» y vuelve a pedir la lectura sin contarla.

Con una lectura válida, el programa decide el estado:

1. **Crítico:** la temperatura o la humedad está fuera del rango crítico. Termina con «Alerta crítica».
2. **Óptimo:** ambas variables están dentro del rango óptimo. Termina con «Condiciones óptimas» si es la primera lectura, o con «Cultivo estabilizado» si no.
3. **Observación:** cualquier otro caso. Muestra la acción correctiva y pide otra lectura. Si se completan 8 lecturas, termina con «Revisión técnica».

## Rangos

| Variable | Rango óptimo | Valor crítico | Rango válido del sensor |
| --- | --- | --- | --- |
| Temperatura [°C] | Entre 18 y 26 | Menor que 12 o mayor que 32 | Entre -10 y 60 |
| Humedad relativa [%] | Entre 60 y 80 | Menor que 40 o mayor que 90 | Entre 0 y 100 |

## Acciones correctivas

| Situación | Acción |
| --- | --- |
| Temperatura mayor que 26 °C | Ventilar |
| Temperatura menor que 18 °C | Encender calefacción |
| Humedad mayor que 80 % | Deshumidificar |
| Humedad menor que 60 % | Nebulizar |

Si las dos variables están fuera de rango en la misma lectura, se muestran las dos acciones, por ejemplo «Encender calefacción y deshumidificar».

## Cómo ejecutarlo

Requiere Python 3.

```bash
python3 invernaderoObservacion.py
```

El programa pide los valores con coma o con punto decimal.

### Ejemplo (caso 1: cultivo estabilizado)

```text
INVERNADERO EN OBSERVACION
Ingrese la temperatura: 29
Ingrese la humedad: 75
Lectura 1 | 29 | 75 | Observación | Ventilar
Ingrese la temperatura: 28
Ingrese la humedad: 72
Lectura 2 | 28 | 72 | Observación | Ventilar
Ingrese la temperatura: 27
Ingrese la humedad: 70
Lectura 3 | 27 | 70 | Observación | Ventilar
Ingrese la temperatura: 25,5
Ingrese la humedad: 70
Lectura 4 | 25,5 | 70 | Óptimo | Cultivo estabilizado

Resultado: Cultivo estabilizado. Lecturas tomadas: 4.
Temperatura: mínima 25,5 – máxima 29 – promedio 27,38.
Humedad: mínima 70 – máxima 75 – promedio 71,75.
Secuencia de temperaturas: 29; 28; 27; 25,5. Secuencia de humedades: 75; 72; 70; 70.
```

## Convención de nombres

Todos los identificadores y archivos usan camelCase.

| Tipo | Ejemplos |
| --- | --- |
| Constantes | `tempOptMin`, `humCritMax`, `maxLecturas` |
| Variables | `numLectura`, `sumTemp`, `secHum`, `accionesList` |
| Funciones | `formatear`, `formatearDecimales` |

## Archivos del repositorio

| Archivo | Contenido |
| --- | --- |
| `invernaderoObservacion.py` | Código fuente del programa |
| `README.md` | Descripción del proyecto |
