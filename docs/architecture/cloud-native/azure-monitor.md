---
title: Azure Monitor
description: El uso de Azure Monitor para obtener visibilidad en el sistema se está ejecutando.
ms.date: 01/19/2021
ms.openlocfilehash: a93b71db642e05a830b20b80d8387c24d35ea8c1
ms.sourcegitcommit: f2ab02d9a780819ca2e5310bbcf5cfe5b7993041
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2021
ms.locfileid: "99506180"
---
# <a name="azure-monitor"></a>Azure Monitor

Ningún otro proveedor de servicios en la nube ha sido maduro de una solución de supervisión de aplicaciones en la nube que la que se encuentra en Azure. Azure Monitor es un nombre de paraguas para una colección de herramientas diseñadas para proporcionar visibilidad sobre el estado del sistema. Le ayuda a comprender el rendimiento de los servicios nativos de la nube y a identificar proactivamente los problemas que afectan a ellos. En la figura 7-12 se muestra un alto nivel de vista de Azure Monitor.

![Vista de alto nivel de Azure Monitor. ](./media/azure-monitor.png)
 **Figura 7-12**. Vista de alto nivel de Azure Monitor.

## <a name="gathering-logs-and-metrics"></a>Recopilación de registros y métricas

El primer paso en cualquier solución de supervisión es recopilar tantos datos como sea posible. Cuanto más datos se recopilen, más profunda es la información. Tradicionalmente, los sistemas de instrumentación han sido difíciles. El Protocolo simple de administración de redes (SNMP) era el protocolo estándar Gold para recopilar información de nivel de máquina, pero requirió una gran cantidad de conocimientos y configuración. Afortunadamente, gran parte de este trabajo duro se ha eliminado, ya que Azure Monitor recopila automáticamente las métricas más comunes.

No es posible instrumentar eventos y métricas de nivel de aplicación de forma automática porque son específicos de la aplicación que se está implementando. Con el fin de recopilar estas métricas, hay [SDK y API disponibles](/azure/azure-monitor/app/api-custom-events-metrics) para notificar directamente dicha información, como cuando un cliente se suscribe o completa un pedido. Las excepciones también se pueden capturar y volver a informar en Azure Monitor a través de Application Insights. Los SDK admiten la mayoría de los lenguajes que se encuentran en las aplicaciones nativas de la nube, como Go, Python, JavaScript y los lenguajes .NET.

El objetivo final de recopilar información sobre el estado de la aplicación es asegurarse de que los usuarios finales tengan una buena experiencia. ¿Cuál es la mejor manera de saber si los usuarios experimentan problemas que realizar [pruebas Web externas](/azure/azure-monitor/app/monitor-web-app-availability)? Estas pruebas pueden ser tan sencillas como hacer ping en el sitio web desde ubicaciones de todo el mundo o como implicar que los agentes inicien sesión en el sitio y simulen las acciones del usuario.

## <a name="reporting-data"></a>Datos de informes

Una vez que se recopilan los datos, se pueden manipular, resumir y trazar en los gráficos, lo que permite a los usuarios ver al instante Cuándo hay problemas. Estos gráficos se pueden recopilar en paneles o en libros, un informe de varias páginas diseñado para indicar una historia sobre algún aspecto del sistema.

No se completará ninguna aplicación moderna sin algunas inteligencia artificial o aprendizaje automático. Para este fin, los datos [se pueden pasar](https://www.youtube.com/watch?v=Cuza-I1g9tw) a las diversas herramientas de aprendizaje automático de Azure para que pueda extraer tendencias e información que, de otro modo, se ocultaría.

Application Insights proporciona un lenguaje de consulta eficaz (similar a SQL) denominado *Kusto* que puede consultar registros, resumirlos e incluso gráficos de trazados. Por ejemplo, la consulta siguiente buscará todos los registros del mes de noviembre de 2007, los agrupará por estado y trazará los 10 principales como un gráfico circular.

```kusto
StormEvents
| where StartTime >= datetime(2007-11-01) and StartTime < datetime(2007-12-01)
| summarize count() by State
| top 10 by count_
| render piechart
```

En la figura 7-13 se muestran los resultados de esta Application Insights consulta.

![Application Insights la ](./media/application_insights_example.png)
 **figura 7-13** de resultados de la consulta. Application Insights resultados de la consulta.

Hay una [animación para experimentar con consultas Kusto](https://dataexplorer.azure.com/clusters/help/databases/Samples) . Leer [consultas de ejemplo](/azure/kusto/query/samples) también puede ser instructivo.

## <a name="dashboards"></a>Paneles

Hay varias tecnologías de panel diferentes que se pueden usar para exponer la información de Azure Monitor. Quizás lo más sencillo es ejecutar consultas en Application Insights y [trazar los datos en un gráfico](/azure/azure-monitor/learn/tutorial-app-dashboards).

![Un ejemplo de gráficos de Application Insights insertados en el panel principal de Azure ](./media/azure_dashboard.png)
 **figura 7-14**. Un ejemplo de gráficos de Application Insights insertados en el panel principal de Azure.

Estos gráficos se pueden incrustar en el Azure Portal adecuado a través del uso de la característica del panel. Para los usuarios con más requisitos de peractuación, como la posibilidad de explorar en profundidad varios niveles de datos, Azure Monitor datos están disponibles para [Power BI](https://powerbi.microsoft.com/). Power BI es una herramienta de inteligencia empresarial líder del sector que puede agregar datos de muchos orígenes de datos diferentes.

![Un ejemplo de panel de Power BI](./media/powerbidashboard.png)

**Figura 7-15**. Un ejemplo Power BI panel.

## <a name="alerts"></a>Alertas

A veces, tener paneles de datos no es suficiente. Si nadie está activo para ver los paneles, puede seguir siendo de muchas horas antes de que se solucione un problema, o incluso cuando se detecte. Con este fin, Azure Monitor también proporciona una solución de [alerta](/azure/azure-monitor/platform/alerts-overview)de muesca. Las alertas se pueden desencadenar en una amplia variedad de condiciones, entre las que se incluyen:

- Valores de métrica
- Consultas de búsqueda de registros
- Eventos del registro de actividad
- Estado de la plataforma Azure subyacente
- Pruebas de disponibilidad del sitio web

Cuando se desencadena, las alertas pueden realizar una amplia variedad de tareas. En el lado sencillo, las alertas solo pueden enviar una notificación por correo electrónico a una lista de distribución de correo o un mensaje de texto a un individuo. Las alertas más complicadas podrían desencadenar un flujo de trabajo en una herramienta como PagerDuty, que es consciente de quién está llamando a para una aplicación determinada. Las alertas pueden desencadenar acciones en [Microsoft Flow](https://flow.microsoft.com/) desbloquear las posibilidades sin límites para los flujos de trabajo.

A medida que se identifican las causas comunes de las alertas, las alertas se pueden mejorar con detalles sobre las causas comunes de las alertas y los pasos que deben seguirse para resolverlos. Las implementaciones de aplicaciones nativas en la nube de gran madurez pueden optar por iniciar tareas de recuperación automática, que realizan acciones como la eliminación de nodos con errores de un conjunto de escalado o la activación de una actividad de escalado automático. Finalmente, es posible que ya no sea necesario reactivar al personal de la llamada en 2AM para resolver un problema en el sitio activo, ya que el sistema podrá ajustarse a sí mismo para compensar o al menos Limp, hasta que alguien llegue al trabajo la mañana siguiente.

Azure Monitor aprovecha automáticamente el aprendizaje automático para comprender los parámetros operativos normales de las aplicaciones implementadas. Este enfoque permite detectar servicios que funcionan fuera de sus parámetros normales. Por ejemplo, el tráfico de día de la semana típico en el sitio podría ser 10.000 solicitudes por minuto. Y después, en una semana determinada, el número de solicitudes alcanza una cantidad muy inusual de 20.000 solicitudes por minuto. La [detección inteligente](/azure/azure-monitor/app/proactive-diagnostics) observará esta desviación de la norma y desencadenará una alerta. Al mismo tiempo, el análisis de tendencias es lo suficientemente inteligente como para evitar la activación de falsos positivos cuando se espera la carga del tráfico.

## <a name="references"></a>Referencias

- [Azure Monitor](/azure/azure-monitor/overview)

>[!div class="step-by-step"]
>[Anterior](monitoring-azure-kubernetes.md)
>[Siguiente](identity.md)
