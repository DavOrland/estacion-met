# DATOS PROCESADOS

Detecto air_quality_data_4 que las coordenadas no definen donde se encuentran los sensores, podemos inferir que todos los sensores son de una misma estacion sin embargo hay diferentes coordenadas en este csv, supondre una sola coordenada "19.414782,-99.167183"

IAS IAQ No estan bien definidos.

## ERRORES

Se detecta el siguiente error en el funcionamiento del sensor, fallo durante un periodo de 2024 **Puede llegar a funcionar este error como una alarma de fallo del sistema y conocer el comportamiento del dispositivo y/o entrenar alertas del fallo del mismo**
![image](https://github.com/DavOrland/estacion-met/blob/main/reports/figures/error_data.png?raw=true)

# Análisis de los datos

*Correccion*
El proceso de captura si es consistente y gradual dia a dia, sin embargo el ruido en las graficas se empieza a notar bastante a la semana de estar trabajando.
**Queda a considerar si es buena idea utilizar un filtro ya que en realidad lo que el sensor hace es captar de forma correcta el valor real** el filtro puede ayudarnos a trabajar de forma mucho mas precisa y sencilla como lo comento el Dr. Ruben con un FFT. Otra opcion que puede ser viable es un EMA ya que estos filtros ayudan a atenuar el proximo valor que captura el sensor (parte que nos interesa... prediccion).

![medicion dia y semana](/reports/figures/med_semana_dia.png)

 ***Hipótesis***

 * H1: Las mediciones sin filtrar tiene un mejor desempeño en un modelo de prediccion que las mediciones filtradas.
 * H0: Las mediciones sin filtrar no tienen un mejor desempeño en un modelo de prediccion que las mediciones filtradas.

   |

 * H1: Las mediciones filtradas con FFT tienen un mejor desempeño en un modelo de predicion que las mediciones filtradas con EMA.
 * H1: Las mediciones filtradas con EMA tienen un mejor desempeño en un modelo de predicion que las mediciones filtradas con FFT.
 * H0: No hay diferencia en el modelo de prediccion usando mediciones filtradas con FFT vs EMA.

## Correlaciones

De forma general
* Correlacion negativa entre Humedad/Temperatura
* Correlacion positiva entre PM2.5/PM10

![heatmap](https://github.com/DavOrland/estacion-met/blob/main/reports/figures/heatmap.png?raw=true)