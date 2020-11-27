---
title: Actividad
ms.date: 03/30/2017
ms.assetid: 70471705-f55f-4da1-919f-4b580f172665
ms.openlocfilehash: 96d89a69071a90a81ead7d594eb495c5d0cdfc63
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96254459"
---
# <a name="activity"></a>Actividad

En este tema se describen los seguimientos de actividad en el modelo de seguimiento de Windows Communication Foundation (WCF). Las actividades procesan unidades que ayudan al usuario a reducir el ámbito de un error. Los errores que se producen en la misma actividad están directamente relacionados. Por ejemplo, se produce un error en una operación porque se ha producido un error en el descifrado del mensaje. Los seguimientos para el error de descifrado del mensaje y la operación aparecen en la misma actividad, mostrando una correlación directa entre el error del descifrado y el error de la solicitud.  
  
## <a name="configuring-activity-tracing"></a>Configuración del seguimiento de actividades  

 WCF proporciona actividades predefinidas para el procesamiento de aplicaciones (consulte la [lista de actividades](activity-list.md)). También puede definir las actividades mediante programación para agrupar los seguimientos del usuario. Para obtener más información, consulte [emitir seguimientos de User-Code](emitting-user-code-traces.md).  
  
 Para emitir seguimientos de actividad en tiempo de ejecución, use la `ActivityTracing` configuración del `System.ServiceModel` origen de seguimiento u otros orígenes de seguimiento WCF o Custom, como se muestra en el código de configuración siguiente.  
  
```xml  
<source name="System.ServiceModel" switchValue="Verbose,ActivityTracing">  
```  
  
 Para obtener más información sobre el elemento de configuración y los atributos que se usan, vea el tema [configuración del seguimiento](configuring-tracing.md) .  
  
## <a name="viewing-activities"></a>Visualización de actividades  

 Puede ver las actividades y su utilidad en la [herramienta Service Trace Viewer (SvcTraceViewer.exe)](../../service-trace-viewer-tool-svctraceviewer-exe.md). Cuando ActivityTracing está habilitado, esta herramienta toma los seguimientos y los ordena en función de la actividad. También puede ver las transferencias de seguimientos. Una transferencia de seguimiento indica cómo se relacionan a entre sí actividades diferentes. Puede ver que una actividad determinada hizo que se iniciara otra. Por ejemplo, una solicitud del mensaje inició un protocolo de enlace de seguridad para obtener un Token de conversación segura.  
  
### <a name="correlating-activities-in-service-trace-viewer"></a>Correlación de actividades en Service Trace Viewer  

 La herramienta Service Trace Viewer proporciona dos vistas de actividades:  
  
- Vista de **lista** , donde el ID. de actividad se usa para correlacionar directamente los seguimientos entre los procesos. Los seguimientos de diferentes procesos, por ejemplo, cliente y servicio, pero con el mismo id. de actividad se agrupan en la misma actividad. Por consiguiente, un error que se produce en el servicio que, a continuación, produce un error en el cliente, se mostrarán ambos en la misma vista de actividades en la herramienta.  
  
- Vista de **gráfico** , donde las actividades se agrupan por procesos. En esta vista, un cliente y un servicio con el mismo identificador de actividad tienen sus seguimientos en actividades diferentes. Para correlacionar actividades con el mismo id. de actividad en procesos diferentes, la herramienta muestra flujos de mensajes en las actividades relacionadas.  
  
 Para obtener más información y ver una vista gráfica de la herramienta Service Trace Viewer, vea la [herramienta Service Trace Viewer (SvcTraceViewer.exe)](../../service-trace-viewer-tool-svctraceviewer-exe.md) y el [uso del visor de seguimiento de servicio para ver los seguimientos correlacionados y la solución de problemas](using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md).  
  
## <a name="defining-the-scope-of-an-activity"></a>Definición del ámbito de una actividad  

 Una actividad se define durante el diseño y denota una unidad lógica de trabajo. Los seguimientos emitidos con el mismo identificador de actividad están directamente relacionados, forman parte de la misma actividad. Debido a que una actividad puede cruzar los límites de extremos (una solicitud), se definen dos ámbitos para una actividad.  
  
- Ámbito `Global`, por aplicación. En este ámbito, la actividad se identifica por su identificador de actividad único globalmente de 128 bits, el gAId. El gAId es lo que se propaga por los puntos de conexión.  
  
- Ámbito `Local`, por extremo. En este ámbito, la actividad se identifica mediante su gAId, junto con el nombre del origen de seguimiento que emite los seguimientos de actividad y el identificador de proceso. Este tríptico constituye el ID. de actividad local, que se establece. El lAId se utiliza para definir los límites (locales) de una actividad.  
  
## <a name="trace-schema"></a>Esquema de seguimiento  

 Los seguimientos se pueden emitir utilizando cualquier esquema y entre plataformas de Microsoft. "E2E" (para "extremo a extremo") es un esquema de uso frecuente. Este esquema incluye un identificador de 128 bits (gAId), el nombre del origen de seguimiento y el identificador de proceso. En código administrado, <xref:System.Diagnostics.XmlWriterTraceListener> emite seguimientos en el esquema E2E.  
  
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
  
- Iniciar: indica el principio de una actividad. Un seguimiento de "Inicio" proporciona un registro de inicio de un nuevo hito de procesamiento. Contiene un nuevo id. de actividad para un origen de seguimiento determinado en un proceso determinado, excepto cuando el id. de actividad se propaga por los extremos, en cuyo caso vemos un "Iniciar" por extremo. Ejemplos de comienzo de una nueva actividad incluyen la creación de un nuevo subproceso para el procesamiento o la entrada en un nuevo método público.  
  
- Detener: indica el fin de una actividad. Un seguimiento de "detención" proporciona un registro de la finalización de un hito de procesamiento existente. Contiene un id. de actividad existente para un origen de seguimiento de traza determinado en un proceso concreto, excepto cuando el id. de actividad se propaga por los extremos, en cuyo caso vemos un "Stop" por cada extremo.  Entre los ejemplos de detención de una actividad se incluye la finalización de un subproceso de procesamiento o la salida de un método cuyo comienzo se ha indicado con un seguimiento de "Inicio".  
  
- Suspender: indica la suspensión del procesamiento de una actividad. Un seguimiento "suspender" contiene un ID. de actividad existente cuyo procesamiento se espera que se reanude en otro momento. Ningún seguimiento se emite con este id. entre los eventos Suspender y Reanudar del origen de seguimientos actual. Entre los ejemplos se incluye la detención de una actividad al llamar una función de biblioteca externa o al esperar un recurso como un puerto de finalización de E/S.  
  
- Reanudar: indica la reanudación del procesamiento de una actividad. Un seguimiento "reanudar" contiene un ID. de actividad existente cuyo último seguimiento emitido desde el origen de seguimiento actual era un seguimiento "suspender". Entre los ejemplos se incluye el volver desde una llamada a una función de biblioteca externa o cuando se ha señalado la reanudación del procesamiento por un recurso como un puerto de finalización de E/S.  
  
- Transferencia: dado que algunas actividades están causadas por otros usuarios o se relacionan con otras, las actividades se pueden relacionar con otras actividades a través de los seguimientos de "transferencia". Una transferencia registra la relación dirigida de una actividad a otra  
  
 Los seguimientos Iniciar y Detener no son críticos para la correlación. Sin embargo, pueden ayudar a aumentar el rendimiento, creación de perfiles y la validación de ámbito de las actividades.  
  
 Mediante el uso de estos tipos, las herramientas pueden optimizar la navegación a través de los registros de seguimiento para encontrar los eventos inmediatamente relacionados de la misma actividad, o eventos en actividades relacionadas si la herramienta sigue los seguimientos de la transferencia. Por ejemplo, las herramientas dejarán de analizar los registros para una actividad determinada cuando vean un seguimiento Iniciar/Detener.  
  
 Estos tipos de seguimiento también se pueden utilizar para la creación de perfiles. Los recursos utilizados entre los marcadores de inicio y detención representan el tiempo inclusivo de la actividad incluyendo las actividades lógicas contenidas. Restar los intervalos de tiempo entre los seguimientos Suspender y Reanudar proporciona la duración real de la actividad.  
  
 El seguimiento Detener también es particularmente útil para validar el ámbito de las actividades implementadas. Si algunos seguimientos del procesamiento aparecen después del seguimiento Detener en lugar de dentro de una actividad determinada, esto puede sugerir un defecto en el código.  
  
## <a name="guidelines-for-using-activity-tracing"></a>Instrucciones para el uso de seguimiento de actividades  

 A continuación se muestra una guía sobre el uso de seguimientos ActivityTracing (Iniciar, Detener, Suspender, Reanudar y Transferir).  
  
- El seguimiento es un gráfico cíclico dirigido, no un árbol. Puede devolver el control a una actividad que generó una actividad.  
  
- Una actividad denota un límite de procesamiento que puede ser significativo para el administrador del sistema o para proporcionar compatibilidad.  
  
- Cada método WCF, tanto en el cliente como en el servidor, se limita iniciando una nueva actividad y, a continuación, (después de que se haya realizado el trabajo) finalizando la nueva actividad y volviendo a la actividad de ambiente.  
  
- Las actividades de larga duración (en curso) como realizar escuchas de conexiones o esperar mensajes se representan haciendo corresponder los marcadores de inicio/detención.  
  
- Las actividades activadas mediante el recibo o procesamiento de un mensaje se representan mediante límites de seguimiento.  
  
- Las actividades representan actividades, no necesariamente objetos. Una actividad debe interpretarse como "Esto estaba ocurriendo cuando. . . (se produjo una emisión de seguimientos significativa)”.  
  
## <a name="see-also"></a>Vea también

- [Configurar seguimiento](configuring-tracing.md)
- [Uso del visor de seguimiento de servicios para ver seguimientos asociados y para la solución de problemas](using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md)
- [Escenarios de seguimiento de traza de un extremo a otro](end-to-end-tracing-scenarios.md)
- [Herramienta del visor de seguimiento de servicio (SvcTraceViewer.exe)](../../service-trace-viewer-tool-svctraceviewer-exe.md)
- [Emisión de trazas del código de usuario](emitting-user-code-traces.md)
