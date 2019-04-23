---
title: Actividad
ms.date: 03/30/2017
ms.assetid: 70471705-f55f-4da1-919f-4b580f172665
ms.openlocfilehash: b93960d4006499c935c27ee18e066d091632d3d9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59170214"
---
# <a name="activity"></a>Actividad
En este tema describe los seguimientos de actividad en el modelo de seguimiento de Windows Communication Foundation (WCF). Las actividades procesan unidades que ayudan al usuario a reducir el ámbito de un error. Los errores que se producen en la misma actividad están directamente relacionados. Por ejemplo, se produce un error en una operación porque se ha producido un error en el descifrado del mensaje. Los seguimientos para el error de descifrado del mensaje y la operación aparecen en la misma actividad, mostrando una correlación directa entre el error del descifrado y el error de la solicitud.  
  
## <a name="configuring-activity-tracing"></a>Configuración del seguimiento de actividades  
 WCF proporciona actividades predefinidas para las aplicaciones de procesamiento (vea [lista de actividades](../../../../../docs/framework/wcf/diagnostics/tracing/activity-list.md)). También puede definir las actividades mediante programación para agrupar los seguimientos del usuario. Para obtener más información, consulte [emisión de trazas del código de usuario](../../../../../docs/framework/wcf/diagnostics/tracing/emitting-user-code-traces.md).  
  
 Para emitir seguimientos de actividad en tiempo de ejecución, utilice el `ActivityTracing` para el `System.ServiceModel` de seguimiento de código fuente, u otros WCF o los orígenes de seguimiento personalizado, como se muestra en el siguiente código de configuración.  
  
```xml  
<source name="System.ServiceModel" switchValue="Verbose,ActivityTracing">  
```  
  
 Para obtener más información sobre el elemento de configuración y los atributos que se va a usar, vea el [configurar el seguimiento](../../../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md) tema.  
  
## <a name="viewing-activities"></a>Visualización de actividades  
 Puede ver las actividades y su utilidad en el [herramienta Service Trace Viewer (SvcTraceViewer.exe)](../../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md). Cuando ActivityTracing está habilitado, esta herramienta toma los seguimientos y los ordena en función de la actividad. También puede ver las transferencias de seguimientos. Una transferencia de seguimiento indica cómo se relacionan a entre sí actividades diferentes. Puede ver que una actividad determinada hizo que se iniciara otra. Por ejemplo, una solicitud del mensaje inició un protocolo de enlace de seguridad para obtener un Token de conversación segura.  
  
### <a name="correlating-activities-in-service-trace-viewer"></a>Correlación de actividades en Service Trace Viewer  
 La herramienta Service Trace Viewer proporciona dos vistas de actividades:  
  
-   **Lista** vista, donde el identificador de actividad se usa para correlacionar directamente seguimientos en los procesos. Los seguimientos de diferentes procesos, por ejemplo, cliente y servicio, pero con el mismo id. de actividad se agrupan en la misma actividad. Por consiguiente, un error que se produce en el servicio que, a continuación, produce un error en el cliente, se mostrarán ambos en la misma vista de actividades en la herramienta.  
  
-   **Gráfico** vista, donde las actividades están agrupadas por procesos. En esta vista, un cliente y un servicio con el mismo identificador de actividad tienen sus seguimientos en actividades diferentes. Para correlacionar actividades con el mismo id. de actividad en procesos diferentes, la herramienta muestra flujos de mensajes en las actividades relacionadas.  
  
 Para obtener más información y para ver una vista gráfica de la herramienta Service Trace Viewer, vea [herramienta Service Trace Viewer (SvcTraceViewer.exe)](../../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) y [utilizando Service Trace Viewer para ver seguimientos correlacionados y Solución de problemas](../../../../../docs/framework/wcf/diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md).  
  
## <a name="defining-the-scope-of-an-activity"></a>Definición del ámbito de una actividad  
 Una actividad se define durante el diseño y denota una unidad lógica de trabajo. Los seguimientos emitidos con el mismo identificador de actividad están directamente relacionados, forman parte de la misma actividad. Debido a que una actividad puede cruzar los límites de extremos (una solicitud), se definen dos ámbitos para una actividad.  
  
-   Ámbito `Global`, por aplicación. En este ámbito, la actividad se identifica por su identificador de actividad único globalmente de 128 bits, el gAId. El gAId es lo que se propaga por los puntos de conexión.  
  
-   Ámbito `Local`, por extremo. En este ámbito, GAId identifica la actividad, junto con el nombre del origen de seguimiento que emite los seguimientos de actividad y el identificador de proceso. Este triplete constituye el id. de actividad local, lAId. El lAId se utiliza para definir los límites (locales) de una actividad.  
  
## <a name="trace-schema"></a>Esquema de seguimiento  
 Los seguimientos se pueden emitir utilizando cualquier esquema y entre plataformas de Microsoft. "e2e" (para "to End") es un esquema comúnmente utilizado. Este esquema incluye un identificador de 128 bits (gAId), el nombre del origen de seguimiento y el identificador de proceso. En código administrado, <xref:System.Diagnostics.XmlWriterTraceListener> emite seguimientos en el esquema E2E.  
  
 Los programadores pueden establecer el AID que se emite con un seguimiento estableciendo la propiedad <xref:System.Diagnostics.CorrelationManager.ActivityId%2A> con un Guid en Almacenamiento local para el subproceso (TLS). En el siguiente ejemplo se muestra cómo hacerlo.  
  
```csharp
// set the current Activity ID to a new GUID.  
CorrelationManager.ActivityId = Guid.NewGuid();  
```
  
 Establecer gAId en TLS será evidente cuando los seguimientos se emitan utilizando un origen de seguimiento, como se muestra en el ejemplo siguiente.  
  
```csharp
TraceSource traceSource = new TraceSource("myTraceSource");  
traceSource.TraceEvent(TraceEventType.Warning, eventId, "Information");  
```  
  
 El seguimiento emitido contendrá actualmente el gAId en TLS, el nombre del origen de seguimiento pasado como parámetro al constructor del origen de seguimiento y el identificador de proceso actual.  
  
## <a name="activity-lifetime"></a>Duración de una actividad  
 En términos estrictos, la evidencia de una actividad se inicia la primera vez que se utiliza el identificador de actividad en un seguimiento emitido y finaliza la última vez que se utiliza en un seguimiento emitido. <xref:System.Diagnostics> proporciona un conjunto predefinido de tipos de seguimiento, incluyendo Iniciar y Detener, para marcar explícitamente los límites de duración de la actividad.  
  
-   Inicio: Indica el principio de una actividad. Un seguimiento "Iniciar" proporciona un registro de comienzo de un nuevo hito de procesamiento. Contiene un nuevo id. de actividad para un origen de seguimiento determinado en un proceso determinado, excepto cuando el id. de actividad se propaga por los extremos, en cuyo caso vemos un "Iniciar" por extremo. Ejemplos de comienzo de una nueva actividad incluyen la creación de un nuevo subproceso para el procesamiento o la entrada en un nuevo método público.  
  
-   Detener: Indica el final de una actividad. Un seguimiento "Detener" proporciona un registro de finalización de un hito de procesamiento existente. Contiene un id. de actividad existente para un origen de seguimiento de traza determinado en un proceso concreto, excepto cuando el id. de actividad se propaga por los extremos, en cuyo caso vemos un "Stop" por cada extremo.  Terminar un subproceso de procesamiento o salir de un método cuyo comienzo se denotó con un seguimiento "Iniciar" son ejemplos de detención de una actividad.  
  
-   Suspender: Indica la suspensión del procesamiento de una actividad. Un seguimiento "Suspender" contiene un identificador de actividad existente cuyo procesamiento se espera que se reanude más adelante. Ningún seguimiento se emite con este id. entre los eventos Suspender y Reanudar del origen de seguimientos actual. Entre los ejemplos se incluye la detención de una actividad al llamar una función de biblioteca externa o al esperar un recurso como un puerto de finalización de E/S.  
  
-   Reanudar: Indica la reanudación del procesamiento de una actividad. Un seguimiento "Reanudar" contiene un identificador de actividad existente cuyo último seguimiento emitido desde el origen de seguimiento actual fue un seguimiento "Suspender". Entre los ejemplos se incluye el volver desde una llamada a una función de biblioteca externa o cuando se ha señalado la reanudación del procesamiento por un recurso como un puerto de finalización de E/S.  
  
-   Transferencia: Puesto que algunas actividades son causadas por otras, o se relacionan con otros usuarios, las actividades pueden deberse a otras actividades mediante seguimientos "Transferir". Una transferencia registra la relación dirigida de una actividad a otra  
  
 Los seguimientos Iniciar y Detener no son críticos para la correlación. Sin embargo, pueden ayudar a aumentar el rendimiento, creación de perfiles y la validación de ámbito de las actividades.  
  
 Mediante el uso de estos tipos, las herramientas pueden optimizar la navegación a través de los registros de seguimiento para encontrar los eventos inmediatamente relacionados de la misma actividad, o eventos en actividades relacionadas si la herramienta sigue los seguimientos de la transferencia. Por ejemplo, las herramientas dejarán de analizar los registros para una actividad determinada cuando vean un seguimiento Iniciar/Detener.  
  
 Estos tipos de seguimiento también se pueden utilizar para la creación de perfiles. Los recursos utilizados entre los marcadores de inicio y detención representan el tiempo inclusivo de la actividad incluyendo las actividades lógicas contenidas. Restar los intervalos de tiempo entre los seguimientos Suspender y Reanudar proporciona la duración real de la actividad.  
  
 El seguimiento Detener también es particularmente útil para validar el ámbito de las actividades implementadas. Si algunos seguimientos del procesamiento aparecen después del seguimiento Detener en lugar de dentro de una actividad determinada, esto puede sugerir un defecto en el código.  
  
## <a name="guidelines-for-using-activity-tracing"></a>Instrucciones para el uso de seguimiento de actividades  
 A continuación se muestra una guía sobre el uso de seguimientos ActivityTracing (Iniciar, Detener, Suspender, Reanudar y Transferir).  
  
-   El seguimiento es un gráfico cíclico dirigido, no un árbol. Puede devolver el control a una actividad que generó una actividad.  
  
-   Una actividad denota un límite de procesamiento que puede ser significativo para el administrador del sistema o para proporcionar compatibilidad.  
  
-   Cada método WCF, tanto en el cliente y el servidor está limitado por a partir de una nueva actividad y luego (después de realizar el trabajo) final de la nueva actividad y volver a la actividad ambiente.  
  
-   Las actividades de larga duración (en curso) como realizar escuchas de conexiones o esperar mensajes se representan haciendo corresponder los marcadores de inicio/detención.  
  
-   Las actividades activadas mediante el recibo o procesamiento de un mensaje se representan mediante límites de seguimiento.  
  
-   Las actividades representan actividades, no necesariamente objetos. Una actividad debe interpretarse como "Esto sucedía cuando. . . (se produjo una emisión de seguimientos significativa)”.  
  
## <a name="see-also"></a>Vea también

- [Configuración de la traza](../../../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md)
- [Uso del visor de seguimiento de servicios para ver seguimientos asociados y para la solución de problemas](../../../../../docs/framework/wcf/diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md)
- [Escenarios de traza de un extremo a otro](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing-scenarios.md)
- [Herramienta del visor de seguimiento de servicio (SvcTraceViewer.exe)](../../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md)
- [Emisión de trazas del código de usuario](../../../../../docs/framework/wcf/diagnostics/tracing/emitting-user-code-traces.md)
