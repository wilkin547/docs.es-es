---
title: Azure Monitor
description: Se está ejecutando el uso de Azure Monitor para obtener visibilidad en el sistema.
ms.date: 02/05/2020
ms.openlocfilehash: 4e5ddba6c1c13dc65662a7748d4ae3a58a6a6f68
ms.sourcegitcommit: f87ad41b8e62622da126aa928f7640108c4eff98
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/07/2020
ms.locfileid: "80805628"
---
# <a name="azure-monitor"></a>Azure Monitor

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Ningún otro proveedor de nube tiene tan maduro de una solución de supervisión de aplicaciones en la nube como la que se encuentra en Azure. Azure Monitor es un nombre general para una colección de herramientas diseñadas para proporcionar visibilidad del estado del sistema, información sobre cualquier problema y optimización de la aplicación.

![Azure Monitor, una colección de herramientas para proporcionar información sobre cómo funciona una aplicación nativa de la nube. ](./media/azure-monitor.png)
 **Figura 7-12**. Azure Monitor, una colección de herramientas para proporcionar información sobre cómo funciona una aplicación nativa de la nube.

## <a name="gathering-logs-and-metrics"></a>Recopilación de registros y métricas

El primer paso en cualquier solución de supervisión es recopilar tantos datos como sea posible. Cuantos más datos se puedan recopilar, más profundas serán las perspectivas que se pueden obtener. Tradicionalmente, los sistemas de instrumentación han sido difíciles. Simple Network Management Protocol (SNMP) era el protocolo estándar de oro para recopilar información a nivel de máquina, pero requería una gran cantidad de conocimientos y configuración. Afortunadamente, gran parte de este trabajo duro se ha eliminado a medida que Azure Monitor recopila automáticamente las métricas más comunes.

Las métricas y los eventos de nivel de aplicación no son posibles de instrumentar automáticamente porque son específicos de la aplicación que se está implementando. Para recopilar estas métricas, hay [SDK y API disponibles](https://docs.microsoft.com/azure/azure-monitor/app/api-custom-events-metrics) para informar directamente dicha información, como cuando un cliente registra o completa un pedido. Las excepciones también se pueden capturar y notificar en Azure Monitor a través de Application Insights. Los SDK admiten la mayoría de todos los idiomas que se encuentran en las aplicaciones nativas de la nube, incluidos Go, Python, JavaScript y los lenguajes .NET.

El objetivo final de recopilar información sobre el estado de la aplicación es garantizar que los usuarios finales tengan una buena experiencia. ¿Qué mejor manera de saber si los usuarios están experimentando problemas que haciendo [pruebas externas a la web?](https://docs.microsoft.com/azure/azure-monitor/app/monitor-web-app-availability) Estas pruebas pueden ser tan simples como hacer ping a su sitio web desde ubicaciones de todo el mundo o tan involucrados como hacer que los agentes inicien sesión en el sitio y simulen las acciones del usuario.

## <a name="reporting-data"></a>Datos de informes

Una vez recopilados los datos, se pueden manipular, resumir y trazar en gráficos, lo que permite a los usuarios ver al instante cuando hay problemas. Estos gráficos se pueden recopilar en paneles o en Workbooks, un informe de varias páginas diseñado para contar una historia sobre algún aspecto del sistema.

Ninguna aplicación moderna estaría completa sin inteligencia artificial o aprendizaje automático. Con este fin, los datos [se pueden pasar](https://www.youtube.com/watch?v=Cuza-I1g9tw) a las distintas herramientas de aprendizaje automático de Azure para permitirle extraer tendencias e información que de otro modo estarían ocultas.

Application Insights proporciona un lenguaje de consulta eficaz denominado Kusto que se puede usar para buscar registros, resumirlos e incluso trazar gráficos. Por ejemplo, esta consulta localizará todos los registros del mes de noviembre de 2007, los agrupará por estado y trazará los 10 principales como un gráfico circular.

```kusto
StormEvents
| where StartTime >= datetime(2007-11-01) and StartTime < datetime(2007-12-01)
| summarize count() by State
| top 10 by count_
| render piechart
```

![El resultado de la](./media/azure-monitor.png)
**figura 7-13**de la consulta de Application Insights. El resultado de la consulta de Application Insights.

Hay un patio de recreo para experimentar con consultas [Kusto,](https://dataexplorer.azure.com/clusters/help/databases/Samples) que es un lugar fantástico para pasar una o dos horas. La lectura de [consultas](https://docs.microsoft.com/azure/kusto/query/samples) de ejemplo también puede ser instructiva.

## <a name="dashboards"></a>Paneles

Hay varias tecnologías de panel diferentes que se pueden usar para exponer la información de Azure Monitor. Tal vez lo más sencillo es simplemente ejecutar consultas en Application Insights y [trazar los datos en un gráfico.](https://docs.microsoft.com/azure/azure-monitor/learn/tutorial-app-dashboards)

![Un ejemplo de gráficos de Application](./media/azure-monitor.png)
Insights incrustados en la**figura 7-14**del panel de Azure principal. Un ejemplo de gráficos de Application Insights incrustados en el panel principal de Azure.

A continuación, estos gráficos se pueden incrustar en Azure Portal correctamente mediante el uso de la característica de panel. Para los usuarios con requisitos más exigentes, como la reincorporación a varios niveles de datos, los datos de Azure Monitor están disponibles para [Power BI.](https://powerbi.microsoft.com/) Power BI es una herramienta de inteligencia empresarial líder en la industria que puede agregar datos de muchos orígenes de datos diferentes.

![Un ejemplo de](./media/azure-monitor.png)
panel de Power BI**Figura 7-15**. Un panel de Power BI de ejemplo.

## <a name="alerts"></a>Alertas

A veces, tener paneles de datos es insuficiente. Si nadie está despierto para ver los paneles, entonces todavía pueden pasar muchas horas antes de que se solucione un problema, o incluso se detecte. Con este fin, Azure Monitor también proporciona una solución de [alertas](https://docs.microsoft.com/azure/azure-monitor/platform/alerts-overview)de primer nivel. Las alertas pueden ser activadas por una amplia gama de condiciones, incluyendo:

- Valores de métrica
- Consultas de búsqueda de registros
- Eventos del registro de actividad
- Estado de la plataforma Azure subyacente
- Pruebas de disponibilidad del sitio web

Cuando se activan, las alertas pueden realizar una amplia variedad de tareas. En el lado simple, las alertas pueden simplemente enviar una notificación por correo electrónico a una lista de correo o un mensaje de texto a una persona. Las alertas más implicadas pueden desencadenar un flujo de trabajo en una herramienta como PagerDuty, que es consciente de quién está de guardia para una aplicación determinada. Las alertas pueden desencadenar acciones en [Microsoft Flow](https://flow.microsoft.com/) desbloqueando casi posibilidades ilimitadas para flujos de trabajo.

A medida que se identifican las causas comunes de las alertas, las alertas se pueden mejorar con detalles sobre las causas comunes de las alertas y los pasos a seguir para resolverlas. Las implementaciones de aplicaciones nativas de la nube altamente maduras pueden optar por iniciar tareas de recuperación automática, que realizan acciones como quitar nodos con errores de un conjunto de escalado o desencadenar una actividad de escalado automático. Eventualmente puede que ya no sea necesario despertar al personal de guardia a las 2 de la mañana para resolver un problema del sitio en vivo, ya que el sistema será capaz de ajustarse para compensar o al menos cojear hasta que alguien llegue al trabajo a la mañana siguiente.

Azure Monitor aprovecha automáticamente el aprendizaje automático para comprender los parámetros operativos normales de las aplicaciones implementadas. Esto le permite detectar servicios que operan fuera de sus parámetros normales. Por ejemplo, el tráfico típico entre semana en el sitio puede ser de 10.000 solicitudes por minuto. Y luego, en una semana determinada, de repente el número de solicitudes llega a una muy inusual 20.000 solicitudes por minuto. [Detección inteligente](https://docs.microsoft.com/azure/azure-monitor/app/proactive-diagnostics) notará esta desviación de la norma y activará una alerta. Al mismo tiempo, el análisis de tendencias es lo suficientemente inteligente como para evitar que se activen falsos positivos cuando se espera la carga de tráfico.

## <a name="references"></a>Referencias

- [Azure Monitor](https://docs.microsoft.com/azure/azure-monitor/overview)

>[!div class="step-by-step"]
>[Anterior](monitoring-azure-kubernetes.md)
>[Siguiente](identity.md)
