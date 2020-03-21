---
title: Transferir
ms.date: 03/30/2017
ms.assetid: dfcfa36c-d3bb-44b4-aa15-1c922c6f73e6
ms.openlocfilehash: e0ebfff97cd33e7a588a1ab92399a97a0fbec039
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185704"
---
# <a name="transfer"></a>Transferir
En este tema se describe la transferencia en el modelo de seguimiento de actividad de Windows Communication Foundation (WCF).  
  
## <a name="transfer-definition"></a>Definición de transferencia  
 Las transferencias entre actividades representan relaciones causales entre eventos en las actividades relacionadas dentro de los puntos de conexión. Dos actividades se relacionan con transferencias cuando el control fluye entre estas actividades, como por ejemplo, una llamada al método que cruza límites de actividad. En WCF, cuando los bytes son entrantes en el servicio, el escuchar en la actividad se transfiere a la actividad de bytes de recepción donde se crea el objeto de mensaje. Para obtener una lista de escenarios de seguimiento de extremo a extremo y su respectivo diseño de actividad y seguimiento, vea [Escenarios](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing-scenarios.md)de seguimiento de extremo a extremo .  
  
 Para emitir seguimientos de transferencia, use el valor `ActivityTracing` en el origen de seguimiento, tal y como se muestra en el código de configuración siguiente.  
  
```xml  
<source name="System.ServiceModel" switchValue="Verbose,ActivityTracing">  
```  
  
## <a name="using-transfer-to-correlate-activities-within-endpoints"></a>Uso de la transferencia para poner en correlación actividades dentro de los puntos de conexión  
 Las actividades y transferencias permiten al usuario ubicar probabilísticamente la causa principal de un error. Por ejemplo, si transferimos de uno a otro respectivamente entre las actividades M y N en componentes M y N, y se bloquea N justamente antes de realizarse la transferencia a M, podemos sacar la conclusión de que es probable que se deba a que N emita datos a M.  
  
 Se emite un seguimiento de transferencia de la actividad M a la actividad N cuando hay flujo de control entre M y N. Por ejemplo, N realiza algún trabajo para M debido a una llamada al método que cruza los límites de las actividades. N puede que ya exista o que se haya creado. M genera N cuando esta última es una nueva actividad que realiza algún trabajo para M.  
  
 Una transferencia de M a N puede que no sea seguida por una transferencia de vuelta de N a M, ya que M puede generar algún trabajo en N y no sabe cuándo N termina ese trabajo. De hecho, M puede finalizar antes de que N complete su tarea. Esto sucede en la actividad "Open ServiceHost" (M) que genera las actividades de escucha (N) y, a continuación, finaliza. Una transferencia de vuelta de N a M significa que N completó el trabajo relacionado con M.  
  
 N puede seguir realizando otro procesamiento no relacionado con M, como por ejemplo una actividad de autenticador existente (N) que sigue recibiendo solicitudes de inicio de sesión (M) de diferentes actividades de inicio de sesión.  
  
 No existe necesariamente una relación de anidamiento entre las actividades M y N. Esto puede pasar debido a dos razones. Primero, cuando la actividad M no supervisa el procesamiento real realizado en N aunque M inició N. Second, cuando N ya existe.  
  
## <a name="example-of-transfers"></a>Ejemplo de transferencias  
 A continuación se muestran dos ejemplos de transferencia.  
  
- Al crear un host de servicio, el constructor toma el control del código de llamada o el código de llamada transfiere al constructor. Cuando el constructor ha terminado de ejecutar, devuelve el control al código de llamada o el constructor transfiere de nuevo al código de llamada. Éste es el caso de una relación anidada.  
  
- Cuando un agente de escucha empieza a procesar datos de transporte, crea un nuevo subproceso y da a la actividad Recibir Bytes el contexto adecuado para procesar, es decir, pasar control y datos. Cuando ese subproceso ha finalizado el procesamiento de la solicitud, la actividad Recibir Bytes no devuelve nada al agente de escucha. En este caso, tenemos una transferencia de entrada pero ninguna de salida en la nueva actividad de subproceso. Las dos actividades se relacionan pero no están anidadas.  
  
## <a name="activity-transfer-sequence"></a>Secuencia de transferencia de actividad  
 Una secuencia de transferencia de actividad bien formada incluye los pasos siguientes.  
  
1. Comenzar una nueva actividad, que consiste en seleccionar un nuevo gAId.  
  
2. Emitir un seguimiento de transferencia a ese nuevo gAId desde el id. de actividad actual  
  
3. Establecer el nuevo id. en TLS  
  
4. Emitir un seguimiento de inicio para indicar el principio de la nueva actividad.  
  
5. Volver a la actividad original consiste en lo siguiente:  
  
6. Emitir un seguimiento de transferencia al gAId original  
  
7. Emitir un seguimiento de detención para indicar el fin de la nueva actividad  
  
8. Establecer TLS en el gAId anterior.  
  
 En el ejemplo de código siguiente se muestra cómo utilizar este recurso. Este ejemplo supone que se realiza una llamada de bloqueo al transferir a la nueva actividad, e incluye seguimientos de suspensión/reanudación.  
  
```csharp
// 0. Create a trace source  
TraceSource ts = new TraceSource("myTS");  

// 1. remember existing ("ambient") activity for clean up  
Guid oldGuid = Trace.CorrelationManager.ActivityId;  
// this will be our new activity  
Guid newGuid = Guid.NewGuid();

// 2. call transfer, indicating that we are switching to the new AID  
ts.TraceTransfer(667, "Transferring.", newGuid);  

// 3. Suspend the current activity.  
ts.TraceEvent(TraceEventType.Suspend, 667, "Suspend: Activity " + i-1);  

// 4. set the new AID in TLS  
Trace.CorrelationManager.ActivityId = newGuid;  

// 5. Emit the start trace  
ts.TraceEvent(TraceEventType.Start, 667, "Boundary: Activity " + i);  

// trace something  
ts.TraceEvent(TraceEventType.Information, 667, "Hello from activity " + i);  

// Perform Work  
// some work.  
// Return  
ts.TraceEvent(TraceEventType.Information, 667, "Work complete on activity " + i);

// 6. Emit the transfer returning to the original activity  
ts.TraceTransfer(667, "Transferring Back.", oldGuid);  

// 7. Emit the End trace  
ts.TraceEvent(TraceEventType.Stop, 667, "Boundary: Activity " + i);  

// 8. Change the tls variable to the original AID  
Trace.CorrelationManager.ActivityId = oldGuid;

// 9. Resume the old activity  
ts.TraceEvent(TraceEventType.Resume, 667, "Resume: Activity " + i-1);  
```  
  
## <a name="see-also"></a>Consulte también

- [Configuración de la traza](../../../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md)
- [Uso del visor de seguimiento de servicios para ver seguimientos asociados y para la solución de problemas](../../../../../docs/framework/wcf/diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md)
- [Escenarios de seguimiento de traza de un extremo a otro](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing-scenarios.md)
- [Herramienta del visor de seguimiento de servicio (SvcTraceViewer.exe)](../../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md)
