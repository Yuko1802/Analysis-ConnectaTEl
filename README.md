# Analysis-ConnectaTel
# 📊 Análisis de clientes y patrones de uso — ConnectaTel 📱
## ✏️Descripción del Proyecto
Este proyecto presenta un análisis exploratorio y de segmentación de clientes de ConnectaTel, con el objetivo de identificar patrones de comportamiento, niveles de uso y oportunidades comerciales que permitan mejorar la oferta de planes de telecomunicaciones.

**El análisis se enfoca principalmente en:**
- La revisión y Limpieza de los datos.
- Distribución de clientes según edad.
- Comportamiento de uso de llamadas y mensajes.
- Comparación entre los planes Básico y Premium.
- Identificación de patrones de uso extremo (outliers).
- Generación de recomendaciones orientadas a la toma de decisiones.

## 🎯Objetivos del Negocio
El objetivo principal es transformar los datos de clientes y uso de servicios en insights accionables para ConnectaTel.

**A partir del análisis se busca responder:**
- ¿Qué problemas de calidad presentaban originalmente los datos?
- ¿Qué segmentos de clientes existen según edad y nivel de uso?
- ¿Qué segmentos pueden representar mayor valor para ConnectaTel?
- ¿Qué patrones de uso extremo se presentan?
- ¿Qué oportunidades existen para mejorar los planes actuales o crear nuevas ofertas?

# 🗂️ Datasets utilizados
**Users**
- user_id
- first_name
- last_name
- age
- city
- reg_date
- plan
- churn_date

**Usage**
- id
- user_id
- type
- date
- duration
- length
 
## 🔤 Las etapas del análisis realizadas
**El análisis se desarrolló mediante las siguientes etapas:**

## **a. Exploración inicial**
Se revisó la estructura de los datasets, tipos de datos, valores únicos y presencia de valores faltantes.

## **b. Calidad y limpieza de datos**

**Se identificaron y trataron diferentes situaciones:**
- Valores nulos en city.
- Valor sentinel -999 en age.
- Valores nulos en churn_date.
- Valores faltantes en usage.date.
- Valores nulos en duration y length.
- Fechas futuras en reg_date.
  
Los valores faltantes de duration y length fueron interpretados considerando el tipo de interacción: los mensajes no requieren duración y las llamadas no requieren longitud de mensaje.

## 👥Segmentación de clientes
**Segmentación por edad**
**Se definieron tres grupos:**
| Segmento | Rango de Edad | Clientes | Participación (%) | 
|:---:|:---:|:---:|:---:|
| 🧒 Jóvenes | < 30 años | 760 | 19.00% |
| 👨 Adultos | 30 a 59 años | 2,018 | 50.45% |
| 👴 Adultos Mayores | ≥ 60 años | 1,222 | 30.55% |

El segmento Adulto concentra la mayor cantidad de clientes, seguido por los adultos mayores. Esto indica que las estrategias comerciales deberían considerar especialmente las necesidades y patrones de consumo de estos grupos.

## Segmentación por nivel de uso
Los clientes fueron clasificados de acuerdo a su cantidad de llamadas y mensajes:
| Nivel de Uso | Clientes | Participación (%) | 
|:---:|:---:|:---:|
| Bajo uso |  778 | 19.45% |
| Uso medio | 2,943 | 73.58% |
| Alto uso |  279 | 6.98% |

Los clientes de Uso medio son los que predominan con tres cuartas partes del total.

## 🔍 Principales hallazgos
**Concentración de clientes adultos y adultos mayores**
La suma de ambos segmentos es del 81% siendo los adultos con un 50.45% y adultos mayores con un 30.55% por lo cual se recomiendan estrategias de fidelización. 

**Concentración en clientes de uso medio**
Siendo la mayoría de clientes con un 73.58%. lo cual pudiera indicar una oportunidad para revisar los planes actuales.

**Clientes de alto consumo**
Aunque en porcentaje es bajo con un 6.98% pudiera considerarse un segmento a crecer

**Clientes de bajo consumo**
Al igual que los de alto uso con un 19.45% se pudiera incrementar mediante campañas temporales de incrementos de minutos o cantidad de mensajes de texto.

## 📊 Análisis de Outliers
**Dentro del análisis realizado se detectaron valores extremos en las variables de consumo:**
- 46 outliers en cantidad de mensajes.
- 30 outliers en cantidad de llamadas.
- 109 outliers en total de minutos de llamadas.

Estos registros no se deben tomar como error ya que pueden ser clientes con un nivel de consumo superior al promedio para cantidad de llamadas y texto no fue mucha la diferencia por lo que se decidió mantener.

Para los de cantidad de minutos de llamada se hizo la recomendación de windsorizar ya que esos valores si eran extremos y podían distorsionar las estadísticas.

## ✅ Recomendaciones

**1. Revisar el plan Básico vs Premium por segmento de edad**
En los histogramas el Plan Básico tiene más volumen que Premium. Valdría la pena diseñar un plan intermedio o beneficios específicos para migrarlos a Premium sin fricción de precio.

**2. Sobre el segmento de "bajo consumo" (19.45%)**
Verificar si el bajo consumo es por elección o por necesidad no cubierta (ej. cobertura, no data plan solo voz/SMS).

**3. Sobre el segmento de "alto consumo" (6.98%)**
Es tu segmento de mayor riesgo de fuga si no está bien atendido (suelen ser los más rentables pero también los más exigentes). Recomendaría:
Cruzarlo con churn_date para ver si tienen tasa de cancelación distinta al resto.
Ver si están concentrados en Premium o si hay usuarios de alto consumo "atrapados" en Básico (posible oportunidad de upsell directa).

## 🛠️ Tecnologías utilizadas

**El análisis fue desarrollado utilizando:**

Python
- Pandas — manipulación y análisis de datos.
- NumPy — operaciones numéricas.
- Matplotlib — visualización de datos.
- Seaborn — visualización estadística.
- Jupyter Notebook / Google Colab — desarrollo y documentación del análisis.
- GitHub — almacenamiento y versionamiento del proyecto.
  
## 🔓 Cómo ejecutar el notebook
Opción 1 — Google Colab
Puedes abrir y ejecutar el notebook directamente en Google Colab:

<img width="117" height="20" alt="image" src="https://github.com/user-attachments/assets/45bb99ea-5ae3-428c-8f81-b893f04b1c5a" />


**Para reproducir el análisis**
- Abrir S7 Version-Estudiante-Project-ConnectaTel.ipynb
- Ejecutar las celdas en orden
