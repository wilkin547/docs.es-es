---
description: 'Más información acerca de: transferencia'
title: Transferencia
ms.date: 03/30/2017
ms.assetid: dfcfa36c-d3bb-44b4-aa15-1c922c6f73e6
ms.openlocfilehash: ce88a71d87c7dd09f321ee58f603f7c4672a6df9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99758065"
---
# <a name="transfer"></a><span data-ttu-id="37b93-103">Transferencia</span><span class="sxs-lookup"><span data-stu-id="37b93-103">Transfer</span></span>

<span data-ttu-id="37b93-104">En este tema se describe la transferencia en el modelo de seguimiento de actividades de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="37b93-104">This topic describes transfer in the Windows Communication Foundation (WCF) activity tracing model.</span></span>  
  
## <a name="transfer-definition"></a><span data-ttu-id="37b93-105">Definición de transferencia</span><span class="sxs-lookup"><span data-stu-id="37b93-105">Transfer Definition</span></span>  

 <span data-ttu-id="37b93-106">Las transferencias entre actividades representan relaciones causales entre eventos en las actividades relacionadas dentro de los puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="37b93-106">Transfers between activities represent causal relationships between events in the related activities within endpoints.</span></span> <span data-ttu-id="37b93-107">Dos actividades se relacionan con transferencias cuando el control fluye entre estas actividades, como por ejemplo, una llamada al método que cruza límites de actividad.</span><span class="sxs-lookup"><span data-stu-id="37b93-107">Two activities are related with transfers when control flows between these activities, for example, a method call crossing activity boundaries.</span></span> <span data-ttu-id="37b93-108">En WCF, cuando los bytes son entrantes en el servicio, la actividad escuchar en se transfiere a la actividad recibir bytes donde se crea el objeto de mensaje.</span><span class="sxs-lookup"><span data-stu-id="37b93-108">In WCF, when bytes are incoming on the service, the Listen At activity is transferred to the Receive Bytes activity where the message object is created.</span></span> <span data-ttu-id="37b93-109">Para obtener una lista de escenarios de seguimiento de un extremo a otro, así como su actividad y diseño de seguimiento completos, consulte [escenarios de seguimiento de un extremo a otro](end-to-end-tracing-scenarios.md).</span><span class="sxs-lookup"><span data-stu-id="37b93-109">For a list of end-to-end tracing scenarios, and their respective activity and tracing design, see [End-To-End Tracing Scenarios](end-to-end-tracing-scenarios.md).</span></span>  
  
 <span data-ttu-id="37b93-110">Para emitir seguimientos de transferencia, use el valor `ActivityTracing` en el origen de seguimiento, tal y como se muestra en el código de configuración siguiente.</span><span class="sxs-lookup"><span data-stu-id="37b93-110">To emit transfer traces, use the `ActivityTracing` setting on the trace source as demonstrated by the following configuration code.</span></span>  
  
```xml  
<source name="System.ServiceModel" switchValue="Verbose,ActivityTracing">  
```  
  
## <a name="using-transfer-to-correlate-activities-within-endpoints"></a><span data-ttu-id="37b93-111">Uso de la transferencia para poner en correlación actividades dentro de los puntos de conexión</span><span class="sxs-lookup"><span data-stu-id="37b93-111">Using Transfer to Correlate Activities Within Endpoints</span></span>  

 <span data-ttu-id="37b93-112">Las actividades y transferencias permiten al usuario ubicar probabilísticamente la causa principal de un error.</span><span class="sxs-lookup"><span data-stu-id="37b93-112">Activities and transfers permit the user to probabilistically locate the root cause of an error.</span></span> <span data-ttu-id="37b93-113">Por ejemplo, si transferimos de uno a otro respectivamente entre las actividades M y N en componentes M y N, y se bloquea N justamente antes de realizarse la transferencia a M, podemos sacar la conclusión de que es probable que se deba a que N emita datos a M.</span><span class="sxs-lookup"><span data-stu-id="37b93-113">For example, if we transfer back and forth between activities M and N respectively in components M and N, and a crash happens in N right after the transfer back to M, we can draw the conclusion that it is likely due to N’s passing data back to M.</span></span>  
  
 <span data-ttu-id="37b93-114">Se emite un seguimiento de transferencia de la actividad M a la actividad N cuando hay flujo de control entre M y N. Por ejemplo, N realiza algún trabajo para M debido a una llamada al método que cruza los límites de las actividades.</span><span class="sxs-lookup"><span data-stu-id="37b93-114">A transfer trace is emitted from activity M to activity N when there is a flow of control between M and N. For example, N performs some work for M because of a method call crossing the activities’ boundaries.</span></span> <span data-ttu-id="37b93-115">N puede que ya exista o que se haya creado.</span><span class="sxs-lookup"><span data-stu-id="37b93-115">N may already exist or has been created.</span></span> <span data-ttu-id="37b93-116">M genera N cuando esta última es una nueva actividad que realiza algún trabajo para M.</span><span class="sxs-lookup"><span data-stu-id="37b93-116">N is spawned by M when N is a new activity that performs some work for M.</span></span>  
  
 <span data-ttu-id="37b93-117">Una transferencia de M a N puede que no sea seguida por una transferencia de vuelta de N a M, ya que M puede generar algún trabajo en N y no sabe cuándo N termina ese trabajo.</span><span class="sxs-lookup"><span data-stu-id="37b93-117">A transfer from M to N may not be followed by a transfer back from N to M. This is because M can spawn some work in N and do not track when N completes that work.</span></span> <span data-ttu-id="37b93-118">De hecho, M puede finalizar antes de que N complete su tarea.</span><span class="sxs-lookup"><span data-stu-id="37b93-118">In fact, M can terminate before N completes its task.</span></span> <span data-ttu-id="37b93-119">Esto sucede en la actividad "abrir ServiceHost" (M) que genera las actividades del agente de escucha (N) y, a continuación, finaliza.</span><span class="sxs-lookup"><span data-stu-id="37b93-119">This happens in the "Open ServiceHost" activity (M) that spawns Listener activities (N) and then terminates.</span></span> <span data-ttu-id="37b93-120">Una transferencia de vuelta de N a M significa que N completó el trabajo relacionado con M.</span><span class="sxs-lookup"><span data-stu-id="37b93-120">A transfer back from N to M means that N completed the work related to M.</span></span>  
  
 <span data-ttu-id="37b93-121">N puede seguir realizando otro procesamiento no relacionado con M, como por ejemplo una actividad de autenticador existente (N) que sigue recibiendo solicitudes de inicio de sesión (M) de diferentes actividades de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="37b93-121">N can continue performing other processing unrelated to M, for example, an existing authenticator activity (N) that keeps receiving login requests (M) from different login activities.</span></span>  
  
 <span data-ttu-id="37b93-122">No existe necesariamente una relación de anidamiento entre las actividades M y N. Esto puede pasar debido a dos razones.</span><span class="sxs-lookup"><span data-stu-id="37b93-122">A nesting relationship does not necessarily exist between activities M and N. This can happen due to two reasons.</span></span> <span data-ttu-id="37b93-123">Primero, cuando la actividad M no supervisa el procesamiento real realizado en N aunque M inició N. Second, cuando N ya existe.</span><span class="sxs-lookup"><span data-stu-id="37b93-123">First, when activity M does not monitor the actual processing performed in N although M initiated N. Second, when N already exists.</span></span>  
  
## <a name="example-of-transfers"></a><span data-ttu-id="37b93-124">Ejemplo de transferencias</span><span class="sxs-lookup"><span data-stu-id="37b93-124">Example of Transfers</span></span>  

 <span data-ttu-id="37b93-125">A continuación se muestran dos ejemplos de transferencia.</span><span class="sxs-lookup"><span data-stu-id="37b93-125">The following lists two transfer examples.</span></span>  
  
- <span data-ttu-id="37b93-126">Al crear un host de servicio, el constructor toma el control del código de llamada o el código de llamada transfiere al constructor.</span><span class="sxs-lookup"><span data-stu-id="37b93-126">When you create a service host, the constructor gains control from the calling code, or the calling code transfers to the constructor.</span></span> <span data-ttu-id="37b93-127">Cuando el constructor ha terminado de ejecutar, devuelve el control al código de llamada o el constructor transfiere de nuevo al código de llamada.</span><span class="sxs-lookup"><span data-stu-id="37b93-127">When the constructor has finished executing, it returns control to the calling code, or the constructor transfers back to the calling code.</span></span> <span data-ttu-id="37b93-128">Éste es el caso de una relación anidada.</span><span class="sxs-lookup"><span data-stu-id="37b93-128">This is the case of a nested relationship.</span></span>  
  
- <span data-ttu-id="37b93-129">Cuando un agente de escucha empieza a procesar datos de transporte, crea un nuevo subproceso y da a la actividad Recibir Bytes el contexto adecuado para procesar, es decir, pasar control y datos.</span><span class="sxs-lookup"><span data-stu-id="37b93-129">When a listener starts processing transport data, it creates a new thread and hands to the Receive Bytes activity the appropriate context for processing, passing control and data.</span></span> <span data-ttu-id="37b93-130">Cuando ese subproceso ha finalizado el procesamiento de la solicitud, la actividad Recibir Bytes no devuelve nada al agente de escucha.</span><span class="sxs-lookup"><span data-stu-id="37b93-130">When that thread has finished processing the request, the Receive Bytes activity passes nothing back to the listener.</span></span> <span data-ttu-id="37b93-131">En este caso, tenemos una transferencia de entrada pero ninguna de salida en la nueva actividad de subproceso.</span><span class="sxs-lookup"><span data-stu-id="37b93-131">In this case, we have a transfer in but no transfer out of the new thread activity.</span></span> <span data-ttu-id="37b93-132">Las dos actividades se relacionan pero no están anidadas.</span><span class="sxs-lookup"><span data-stu-id="37b93-132">The two activities are related but not nested.</span></span>  
  
## <a name="activity-transfer-sequence"></a><span data-ttu-id="37b93-133">Secuencia de transferencia de actividad</span><span class="sxs-lookup"><span data-stu-id="37b93-133">Activity Transfer Sequence</span></span>  

 <span data-ttu-id="37b93-134">Una secuencia de transferencia de actividad bien formada incluye los pasos siguientes.</span><span class="sxs-lookup"><span data-stu-id="37b93-134">A well-formed activity transfer sequence includes the following steps.</span></span>  
  
1. <span data-ttu-id="37b93-135">Comenzar una nueva actividad, que consiste en seleccionar un nuevo gAId.</span><span class="sxs-lookup"><span data-stu-id="37b93-135">Begin a new activity, which consists of selecting a new gAId.</span></span>  
  
2. <span data-ttu-id="37b93-136">Emitir un seguimiento de transferencia a ese nuevo gAId desde el id. de actividad actual</span><span class="sxs-lookup"><span data-stu-id="37b93-136">Emit a transfer trace to that new gAId from the current activity ID</span></span>  
  
3. <span data-ttu-id="37b93-137">Establecer el nuevo id. en TLS</span><span class="sxs-lookup"><span data-stu-id="37b93-137">Set the new ID in TLS</span></span>  
  
4. <span data-ttu-id="37b93-138">Emitir un seguimiento de inicio para indicar el principio de la nueva actividad.</span><span class="sxs-lookup"><span data-stu-id="37b93-138">Emit a start trace to indicate the beginning of the new activity by.</span></span>  
  
5. <span data-ttu-id="37b93-139">Volver a la actividad original consiste en lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="37b93-139">Return to the original activity consists of the following:</span></span>  
  
6. <span data-ttu-id="37b93-140">Emitir un seguimiento de transferencia al gAId original</span><span class="sxs-lookup"><span data-stu-id="37b93-140">Emit a transfer trace to the original gAId</span></span>  
  
7. <span data-ttu-id="37b93-141">Emitir un seguimiento de detención para indicar el fin de la nueva actividad</span><span class="sxs-lookup"><span data-stu-id="37b93-141">Emit a Stop trace to indicate the end of the new activity</span></span>  
  
8. <span data-ttu-id="37b93-142">Establecer TLS en el gAId anterior.</span><span class="sxs-lookup"><span data-stu-id="37b93-142">Set TLS to the old gAId.</span></span>  
  
 <span data-ttu-id="37b93-143">En el ejemplo de código siguiente se muestra cómo utilizar este recurso.</span><span class="sxs-lookup"><span data-stu-id="37b93-143">The following code example demonstrates how to do this.</span></span> <span data-ttu-id="37b93-144">Este ejemplo supone que se realiza una llamada de bloqueo al transferir a la nueva actividad, e incluye seguimientos de suspensión/reanudación.</span><span class="sxs-lookup"><span data-stu-id="37b93-144">This sample assumes a blocking call is made when transferring to the new activity, and includes suspend/resume traces.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="37b93-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="37b93-145">See also</span></span>

- [<span data-ttu-id="37b93-146">Configurar seguimiento</span><span class="sxs-lookup"><span data-stu-id="37b93-146">Configuring Tracing</span></span>](configuring-tracing.md)
- [<span data-ttu-id="37b93-147">Uso del visor de seguimiento de servicios para ver seguimientos asociados y para la solución de problemas</span><span class="sxs-lookup"><span data-stu-id="37b93-147">Using Service Trace Viewer for Viewing Correlated Traces and Troubleshooting</span></span>](using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md)
- [<span data-ttu-id="37b93-148">Escenarios de seguimiento de traza de un extremo a otro</span><span class="sxs-lookup"><span data-stu-id="37b93-148">End-To-End Tracing Scenarios</span></span>](end-to-end-tracing-scenarios.md)
- [<span data-ttu-id="37b93-149">Herramienta del visor de seguimiento de servicio (SvcTraceViewer.exe)</span><span class="sxs-lookup"><span data-stu-id="37b93-149">Service Trace Viewer Tool (SvcTraceViewer.exe)</span></span>](../../service-trace-viewer-tool-svctraceviewer-exe.md)
