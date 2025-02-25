# Project-Megaline-Telecomunicaciones
## 📌 Análisis de Tarifas de Megaline: Identificación del Plan Más Rentable

### 📄 Descripción del proyecto:
Este proyecto analiza el comportamiento de los clientes de la empresa de telecomunicaciones Megaline con el objetivo de determinar cuál de sus dos planes de prepago, Surf y Ultimate, genera más ingresos. Se trabajó con datos de 500 clientes, incluyendo registros de llamadas, mensajes y uso de datos, para evaluar la rentabilidad de cada plan.

### 🎯 Objetivo del proyecto:
Identificar cuál de los dos planes de prepago de Megaline es más rentable, utilizando análisis de datos y técnicas estadísticas para optimizar la estrategia de inversión en publicidad.

### Descripción de las tarifas
Nota: Megaline redondea los segundos a minutos y los megabytes a gigabytes. Para llamadas, cada llamada individual se redondea: incluso si la llamada duró solo un segundo, se contará como un minuto. Para tráfico web, las sesiones web individuales no se redondean. En vez de esto, el total del mes se redondea hacia arriba. Si alguien usa 1025 megabytes este mes, se le cobrarán 2 gigabytes.

A continuación puedes ver una descripción de las tarifas:

- Surf
  - Pago mensual: 20$.
  - 500 minutos al mes, 50 SMS y 15 GB de datos.
  - Si se exceden los límites del paquete:
  - 1 minuto: 3 centavos.
  - 1 SMS: 3 centavos.
  - 1 GB de datos: 10$.
  
- Ultimate
  - Pago mensual: 70$.
  - 3000 minutos al mes, 1000 SMS y 30 GB de datos.
  - Si se exceden los límites del paquete:
  - 1 minuto: 1 centavo.
  - 1 SMS: 1 centavo.
  - 1 GB de datos: 7$.

### Diccionario de datos
En este proyecto, trabajarás con cinco tablas diferentes.

- La tabla users (datos sobre los usuarios):
 
  - user_id: identificador único del usuario.
  - first_name: nombre del usuario.
  - last_name: apellido del usuario.
  - age: edad del usuario (en años).
  - reg_date: fecha de suscripción (dd, mm, aa).
  - churn_date: la fecha en la que el usuario dejó de usar el servicio (si el valor es ausente, la tarifa se estaba usando cuando fue extraída esta base de datos).
  - city: ciudad de residencia del usuario.
  - plan: nombre de la tarifa.

- La tabla calls (datos sobre las llamadas):
 
  - id: identificador único de la llamada.
  - call_date: fecha de la llamada.
  - duration: duración de la llamada (en minutos).
  - user_id: el identificador del usuario que realiza la llamada.

- La tabla messages (datos sobre los SMS):
 
  - id: identificador único del SMS.
  - message_date: fecha del SMS.
  - user_id: el identificador del usuario que manda el SMS.

- La tabla internet (datos sobre las sesiones web):
 
  - id: identificador único de la sesión.
  - mb_used: el volumen de datos gastados durante la sesión (en megabytes).
  - session_date: fecha de la sesión web.
  - user_id: identificador del usuario.

- La tabla plans (datos sobre las tarifas):
 
  - plan_name: nombre de la tarifa.
  - usd_monthly_fee: pago mensual en dólares estadounidenses.
  - minutes_included: minutos incluidos al mes.
  - messages_included: SMS incluidos al mes.
  - mb_per_month_included: datos incluidos al mes (en megabytes).
  - usd_per_minute: precio por minuto tras exceder los límites del paquete (por ejemplo, si el paquete incluye 100 minutos, el operador cobrará el minuto 101).
  - usd_per_message: precio por SMS tras exceder los límites del paquete.
  - usd_per_gb: precio por gigabyte de los datos extra tras exceder los límites del paquete (1 GB = 1024 megabytes).

### 📊 Conclusiones finales:
- El plan Ultimate tiene ingresos más consistentes, con un ingreso promedio de $72.31 y menor variabilidad en comparación con el plan Surf ($60.70 de ingreso promedio con mayor desviación estándar).
- El 41% de los usuarios de Megaline consumen más datos de los incluidos en su plan, lo que representa una oportunidad de ingresos adicionales para la empresa.
- Los usuarios del plan Surf generan ingresos más variables, con casos en los que superan ampliamente el pago base debido al consumo extra de minutos, mensajes y datos.
- El plan Surf, en total, generó más ingresos que el Ultimate ($95,491 vs. $52,066), pero su rentabilidad mensual promedio es inferior.
- Se realizó una prueba estadística para validar si las diferencias en ingresos entre ambos planes eran significativas, y se confirmó que los ingresos mensuales promedio entre Surf y Ultimate son significativamente distintos (p-valor < 0.05).

## 🛠️ Skills obtenidas:
- Análisis Exploratorio de Datos (EDA)
- Manejo y limpieza de datos con pandas y numpy
- Visualización de datos con matplotlib y seaborn
- Pruebas estadísticas con scipy
- Análisis de rentabilidad y comportamiento del usuario
- Creación de funciones personalizadas para cálculo de ingresos y costos adicionales

## 📚 Lecciones aprendidas:
- El equilibrio entre ingresos fijos y variables es clave en la rentabilidad de un servicio. Aunque el plan Surf generó mayores ingresos totales, Ultimate ofreció ingresos más predecibles.
- El análisis de datos permite optimizar estrategias comerciales. Los hallazgos pueden ayudar a Megaline a diseñar mejores campañas de retención y promoción de tarifas.
- Las pruebas estadísticas son esenciales para validar diferencias. Sin ellas, podríamos haber llegado a conclusiones incorrectas sobre la rentabilidad de cada plan.
