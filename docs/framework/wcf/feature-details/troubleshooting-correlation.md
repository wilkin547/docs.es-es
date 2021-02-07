---
description: Más información acerca de la solución de problemas de correlación
title: Solución de problemas de correlación
ms.date: 03/30/2017
ms.assetid: 98003875-233d-4512-a688-4b2a1b0b5371
ms.openlocfilehash: de02017f7a86478147cd12a89c37bb7b5bc89a7d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99733026"
---
# <a name="troubleshooting-correlation"></a><span data-ttu-id="95c5e-103">Solución de problemas de correlación</span><span class="sxs-lookup"><span data-stu-id="95c5e-103">Troubleshooting Correlation</span></span>

<span data-ttu-id="95c5e-104">La correlación se utiliza para relacionar los mensajes del servicio de flujo de trabajo entre sí y con la instancia de flujo de trabajo correcta, pero si no está configurada correctamente, los mensajes no se recibirán y las aplicaciones no funcionarán de forma adecuada.</span><span class="sxs-lookup"><span data-stu-id="95c5e-104">Correlation is used to relate workflow service messages to each other and to the correct workflow instance, but if it is not configured correctly, messages will not be received and applications will not work correctly.</span></span> <span data-ttu-id="95c5e-105">Este tema proporciona información general de varios métodos para solucionar problemas de la correlación y también enumera algunos problemas comunes que se pueden producir cuando se usa.</span><span class="sxs-lookup"><span data-stu-id="95c5e-105">This topic provides an overview of several methods for troubleshooting correlation issues, and also lists some common issues that can occur when you use correlation.</span></span>

## <a name="handle-the-unknownmessagereceived-event"></a><span data-ttu-id="95c5e-106">Administrar el evento UnknownMessageReceived</span><span class="sxs-lookup"><span data-stu-id="95c5e-106">Handle the UnknownMessageReceived Event</span></span>

 <span data-ttu-id="95c5e-107">El evento <xref:System.ServiceModel.ServiceHostBase.UnknownMessageReceived> se produce cuando un servicio recibe un mensaje desconocido, incluidos los mensajes que no se pueden poner en correlación con una instancia existente.</span><span class="sxs-lookup"><span data-stu-id="95c5e-107">The <xref:System.ServiceModel.ServiceHostBase.UnknownMessageReceived> event occurs when an unknown message is received by a service, including messages that cannot be correlated to an existing instance.</span></span> <span data-ttu-id="95c5e-108">Para los servicios autohospedados, este evento se puede administrar en la aplicación host.</span><span class="sxs-lookup"><span data-stu-id="95c5e-108">For self-hosted services, this event can be handled in the host application.</span></span>

```csharp
host.UnknownMessageReceived += delegate(object sender, UnknownMessageReceivedEventArgs e)
{
    Console.WriteLine("Unknown Message Received:");
    Console.WriteLine(e.Message);
};
```

 <span data-ttu-id="95c5e-109">Para los servicios hospedados en web, este evento se puede administrar derivando una clase de <xref:System.ServiceModel.Activities.Activation.WorkflowServiceHostFactory> e invalidando el método <xref:System.ServiceModel.Activities.Activation.WorkflowServiceHostFactory.CreateWorkflowServiceHost%2A>.</span><span class="sxs-lookup"><span data-stu-id="95c5e-109">For Web-hosted services, this event can be handled by deriving a class from <xref:System.ServiceModel.Activities.Activation.WorkflowServiceHostFactory> and overriding <xref:System.ServiceModel.Activities.Activation.WorkflowServiceHostFactory.CreateWorkflowServiceHost%2A>.</span></span>

```csharp
class CustomFactory : WorkflowServiceHostFactory
{
    protected override WorkflowServiceHost CreateWorkflowServiceHost(Activity activity, Uri[] baseAddresses)
    {
        // Create the WorkflowServiceHost.
        WorkflowServiceHost host = new WorkflowServiceHost(activity, baseAddresses);

        // Handle the UnknownMessageReceived event.
        host.UnknownMessageReceived += delegate(object sender, UnknownMessageReceivedEventArgs e)
        {
            Console.WriteLine("Unknown Message Received:");
            Console.WriteLine(e.Message);
        };

        return host;
    }
}
```

 <span data-ttu-id="95c5e-110">Esta clase <xref:System.ServiceModel.Activities.Activation.WorkflowServiceHostFactory> personalizada se puede especificar entonces en el archivo `svc` para el servicio.</span><span class="sxs-lookup"><span data-stu-id="95c5e-110">This custom <xref:System.ServiceModel.Activities.Activation.WorkflowServiceHostFactory> can then be specified in the `svc` file for the service.</span></span>

`<% @ServiceHost Language="C#" Service="OrderServiceWorkflow" Factory="CustomFactory" %>`

 <span data-ttu-id="95c5e-111">Cuando se invoca este controlador, el mensaje se puede recuperar utilizando la propiedad <xref:System.ServiceModel.UnknownMessageReceivedEventArgs.Message%2A> de la clase <xref:System.ServiceModel.UnknownMessageReceivedEventArgs> y se parecerá al siguiente mensaje.</span><span class="sxs-lookup"><span data-stu-id="95c5e-111">When this handler is invoked, the message can be retrieved by using the <xref:System.ServiceModel.UnknownMessageReceivedEventArgs.Message%2A> property of the <xref:System.ServiceModel.UnknownMessageReceivedEventArgs>, and will resemble the following message.</span></span>

```xml
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header>
    <To s:mustUnderstand="1" xmlns="http://schemas.microsoft.com/ws/2005/05/addressing/none">http://localhost:8080/OrderService</To>
    <Action s:mustUnderstand="1" xmlns="http://schemas.microsoft.com/ws/2005/05/addressing/none">http://tempuri.org/IService/AddItem</Action>
  </s:Header>
  <s:Body>
    <AddItem xmlns="http://tempuri.org/">
      <Item>Books</Item>
    </AddItem>
  </s:Body>
</s:Envelope>
```

 <span data-ttu-id="95c5e-112">Al inspeccionar los mensajes enviados al controlador del evento <xref:System.ServiceModel.ServiceHostBase.UnknownMessageReceived>, se pueden proporcionar pistas acerca de por qué el mensaje no estaba en correlación con una instancia del servicio de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="95c5e-112">Inspecting messages dispatched to the <xref:System.ServiceModel.ServiceHostBase.UnknownMessageReceived> handler may provide clues about why the message did not correlate to an instance of the workflow service.</span></span>

## <a name="use-tracking-to-monitor-the-progress-of-the-workflow"></a><span data-ttu-id="95c5e-113">Seguimiento del uso para supervisar el progreso del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="95c5e-113">Use Tracking to Monitor the Progress of the Workflow</span></span>

 <span data-ttu-id="95c5e-114">El seguimiento ofrece una manera de supervisar el progreso de un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="95c5e-114">Tracking provides a way to monitor the progress of a workflow.</span></span> <span data-ttu-id="95c5e-115">De forma predeterminada, se emiten registros de seguimiento para los eventos de ciclo de vida de flujo de trabajo, los eventos de ciclo de vida de actividad, la propagación de errores y la reanudación de marcadores.</span><span class="sxs-lookup"><span data-stu-id="95c5e-115">By default, tracking records are emitted for workflow life-cycle events, activity life-cycle events, fault propagation, and bookmark resumption.</span></span> <span data-ttu-id="95c5e-116">Además, las actividades personalizadas pueden emitir registros de seguimiento personalizados.</span><span class="sxs-lookup"><span data-stu-id="95c5e-116">Additionally, custom tracking records can be emitted by custom activities.</span></span> <span data-ttu-id="95c5e-117">Al solucionar los problemas de la correlación, los registros más útiles son los de seguimiento de las actividades, de la reanudación de marcadores y de la propagación de errores.</span><span class="sxs-lookup"><span data-stu-id="95c5e-117">When troubleshooting correlation, the activity tracking records, the bookmark resumption records, and the fault propagation records are the most useful.</span></span> <span data-ttu-id="95c5e-118">Los registros de seguimiento de actividades se pueden utilizar para determinar el progreso actual del flujo de trabajo y pueden ayudar a identificar qué actividad de mensajería está esperando actualmente mensajes.</span><span class="sxs-lookup"><span data-stu-id="95c5e-118">The activity tracking records can be used to determine the current progress of the workflow and can help identify which messaging activity is currently waiting for messages.</span></span> <span data-ttu-id="95c5e-119">Los registros de reanudación de marcadores son útiles porque indican que el flujo de trabajo recibió un mensaje, y los registros de propagación de errores proporcionan un registro de los errores en el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="95c5e-119">Bookmark resumption records are useful because they indicate that a message was received by the workflow, and fault propagation records provide a record of any faults in the workflow.</span></span> <span data-ttu-id="95c5e-120">Para habilitar el seguimiento, especifique el objeto<xref:System.Activities.Tracking.TrackingParticipant> deseado en la propiedad <xref:System.ServiceModel.Activities.WorkflowServiceHost.WorkflowExtensions%2A> de la clase <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="95c5e-120">To enable tracking, specify the desired <xref:System.Activities.Tracking.TrackingParticipant> in the <xref:System.ServiceModel.Activities.WorkflowServiceHost.WorkflowExtensions%2A> of the <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span></span> <span data-ttu-id="95c5e-121">En el ejemplo siguiente, el `ConsoleTrackingParticipant` (del ejemplo de [seguimiento personalizado](../../windows-workflow-foundation/samples/custom-tracking.md) ) se configura mediante el perfil de seguimiento predeterminado.</span><span class="sxs-lookup"><span data-stu-id="95c5e-121">In the following example, the `ConsoleTrackingParticipant` (from the [Custom Tracking](../../windows-workflow-foundation/samples/custom-tracking.md) sample) is configured by using the default tracking profile.</span></span>

```csharp
host.WorkflowExtensions.Add(new ConsoleTrackingParticipant());
```

 <span data-ttu-id="95c5e-122">Un participante del seguimiento como ConsoleTrackingParticipant es útil para los servicios de flujo de trabajo autohospedados que tengan una ventana de la consola.</span><span class="sxs-lookup"><span data-stu-id="95c5e-122">A tracking participant such as the ConsoleTrackingParticipant is useful for self-hosted workflow services that have a console window.</span></span> <span data-ttu-id="95c5e-123">Para un servicio hospedado en Web, se debe usar un participante de seguimiento que registre la información de seguimiento en un almacén duradero, como el integrado <xref:System.Activities.Tracking.EtwTrackingParticipant> , o un participante de seguimiento personalizado que registre la información en un archivo.</span><span class="sxs-lookup"><span data-stu-id="95c5e-123">For a Web-hosted service, a tracking participant that logs the tracking information to a durable store should be used, such as the built-in <xref:System.Activities.Tracking.EtwTrackingParticipant>, or a custom tracking participant that logs the information to a file.</span></span>

 <span data-ttu-id="95c5e-124">Para obtener más información sobre el seguimiento y la configuración del seguimiento de un servicio de flujo de trabajo hospedado en Web, vea seguimiento y seguimiento de [flujos de trabajo](../../windows-workflow-foundation/workflow-tracking-and-tracing.md), [configuración del seguimiento de un flujo de trabajo](../../windows-workflow-foundation/configuring-tracking-for-a-workflow.md)y ejemplos de [seguimiento &#91;WF&#93;](../../windows-workflow-foundation/samples/tracking.md) ejemplos.</span><span class="sxs-lookup"><span data-stu-id="95c5e-124">For more information about tracking and configuring tracking for a Web-hosted workflow service, see [Workflow Tracking and Tracing](../../windows-workflow-foundation/workflow-tracking-and-tracing.md), [Configuring Tracking for a Workflow](../../windows-workflow-foundation/configuring-tracking-for-a-workflow.md), and the [Tracking &#91;WF Samples&#93;](../../windows-workflow-foundation/samples/tracking.md) samples.</span></span>

## <a name="use-wcf-tracing"></a><span data-ttu-id="95c5e-125">Usar el seguimiento de WCF</span><span class="sxs-lookup"><span data-stu-id="95c5e-125">Use WCF Tracing</span></span>

 <span data-ttu-id="95c5e-126">El seguimiento de WCF permite el seguimiento del flujo de mensajes de un servicio de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="95c5e-126">WCF tracing provides tracing of the flow of messages to and from a workflow service.</span></span> <span data-ttu-id="95c5e-127">Esta información de seguimiento resulta útil cuando se solucionan los problemas de la correlación, en especial en el caso de la correlación basada en el contenido.</span><span class="sxs-lookup"><span data-stu-id="95c5e-127">This tracing information is useful when troubleshooting correlation issues, especially for content-based correlation.</span></span> <span data-ttu-id="95c5e-128">Para habilitar el seguimiento, especifique los agentes de escucha de seguimiento que desee en la sección `system.diagnostics` del archivo `web.config` si el servicio del flujo de trabajo es hospedado en web, o el archivo `app.config`, si el servicio de flujo de trabajo es autohospedado.</span><span class="sxs-lookup"><span data-stu-id="95c5e-128">To enable tracing, specify the desired trace listeners in the `system.diagnostics` section of the `web.config` file if the workflow service is Web-hosted, or the `app.config` file if the workflow service is self-hosted.</span></span> <span data-ttu-id="95c5e-129">Para incluir el contenido de los mensajes en el archivo de seguimiento, especifique `true` en `logEntireMessage` en el elemento `messageLogging` de la sección `diagnostics` de `system.serviceModel`.</span><span class="sxs-lookup"><span data-stu-id="95c5e-129">To include the contents of the messages in the trace file, specify `true` for `logEntireMessage` in the `messageLogging` element in the `diagnostics` section of `system.serviceModel`.</span></span> <span data-ttu-id="95c5e-130">En el siguiente ejemplo, la información de seguimiento, incluido el contenido de los mensajes, se configura para escribirse en un archivo que se denomina `service.svclog`.</span><span class="sxs-lookup"><span data-stu-id="95c5e-130">In the following example, tracing information, including the content of the messages, is configured to be written to a file that is named `service.svclog`.</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <system.diagnostics>
    <sources>
      <source name="System.ServiceModel" switchValue="Information" propagateActivity="true">
        <listeners>
          <add name="corr"/>
        </listeners>
      </source>
      <source name="System.ServiceModel.MessageLogging">
        <listeners>
          <add name="corr"/>
        </listeners>
      </source>
    </sources>

    <sharedListeners>
      <add name="corr" type="System.Diagnostics.XmlWriterTraceListener" initializeData="c:\logs\service.svclog">
      </add>
    </sharedListeners>
  </system.diagnostics>

  <system.serviceModel>
    <diagnostics>
      <messageLogging logEntireMessage="true" logMalformedMessages="false"
         logMessagesAtServiceLevel="false" logMessagesAtTransportLevel="true" maxSizeOfMessageToLog="2147483647">
      </messageLogging>
    </diagnostics>
  </system.serviceModel>
</configuration>
```

 <span data-ttu-id="95c5e-131">Para ver la información de seguimiento contenida en `service.svclog` , se usa la [herramienta Service Trace Viewer (SvcTraceViewer.exe)](../service-trace-viewer-tool-svctraceviewer-exe.md) .</span><span class="sxs-lookup"><span data-stu-id="95c5e-131">To view the trace information that is contained in `service.svclog`, the [Service Trace Viewer Tool (SvcTraceViewer.exe)](../service-trace-viewer-tool-svctraceviewer-exe.md) is used.</span></span> <span data-ttu-id="95c5e-132">Esto es especialmente útil cuando se solucionan los problemas de la correlación basada en contenido porque puede ver el contenido de los mensajes y ver lo que se pasa exactamente, y si coincide el <xref:System.ServiceModel.CorrelationQuery> con la correlación basada en contenido.</span><span class="sxs-lookup"><span data-stu-id="95c5e-132">This is especially useful when troubleshooting content-based correlation issues because you can view the message contents and see exactly what is being passed, and whether it matches the <xref:System.ServiceModel.CorrelationQuery> for the content-based correlation.</span></span> <span data-ttu-id="95c5e-133">Para obtener más información sobre el seguimiento de WCF, vea [herramienta Visor de seguimiento de servicio (SvcTraceViewer.exe)](../service-trace-viewer-tool-svctraceviewer-exe.md), [configurar el seguimiento](../diagnostics/tracing/configuring-tracing.md)y [usar el seguimiento para solucionar problemas de la aplicación](../diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md).</span><span class="sxs-lookup"><span data-stu-id="95c5e-133">For more information about WCF tracing, see [Service Trace Viewer Tool (SvcTraceViewer.exe)](../service-trace-viewer-tool-svctraceviewer-exe.md), [Configuring Tracing](../diagnostics/tracing/configuring-tracing.md), and [Using Tracing to Troubleshoot Your Application](../diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md).</span></span>

## <a name="common-context-exchange-correlation-issues"></a><span data-ttu-id="95c5e-134">Problemas comunes de la correlación de intercambio del contexto</span><span class="sxs-lookup"><span data-stu-id="95c5e-134">Common Context Exchange Correlation Issues</span></span>

 <span data-ttu-id="95c5e-135">Ciertos tipos de correlación requieren que se use un tipo específico de enlace para que la correlación funcione correctamente.</span><span class="sxs-lookup"><span data-stu-id="95c5e-135">Certain types of correlation require that a specific type of binding is used for the correlation to work correctly.</span></span> <span data-ttu-id="95c5e-136">En los ejemplos se incluye la correlación de tipo solicitud-respuesta, que requiere un enlace bidireccional como <xref:System.ServiceModel.BasicHttpBinding>, y la correlación de intercambio de contexto, que requiere un enlace basado en contexto como <xref:System.ServiceModel.BasicHttpContextBinding>.</span><span class="sxs-lookup"><span data-stu-id="95c5e-136">Examples include request-reply correlation, which requires a two-way binding such as <xref:System.ServiceModel.BasicHttpBinding>, and context exchange correlation, which requires a context-based binding such as <xref:System.ServiceModel.BasicHttpContextBinding>.</span></span> <span data-ttu-id="95c5e-137">La mayoría de los enlaces admiten las operaciones bidireccionales, de modo que no es un problema común de la correlación de solicitud-respuesta, pero solo hay algunos enlaces basados en contexto incluidos <xref:System.ServiceModel.BasicHttpContextBinding>, <xref:System.ServiceModel.WSHttpContextBinding> y <xref:System.ServiceModel.NetTcpContextBinding>.</span><span class="sxs-lookup"><span data-stu-id="95c5e-137">Most bindings support two-way operations so this is not a common issue for request-reply correlation, but there are only a handful of context-based bindings including <xref:System.ServiceModel.BasicHttpContextBinding>, <xref:System.ServiceModel.WSHttpContextBinding>, and <xref:System.ServiceModel.NetTcpContextBinding>.</span></span> <span data-ttu-id="95c5e-138">Si no se utiliza alguno de estos enlaces, la llamada inicial a un servicio de flujo de trabajo tendrá éxito, pero se producirá un error en las llamadas posteriores con la siguiente <xref:System.ServiceModel.FaultException>.</span><span class="sxs-lookup"><span data-stu-id="95c5e-138">If one of these bindings is not used, the initial call to a workflow service will succeed, but subsequent calls will fail with the following <xref:System.ServiceModel.FaultException>.</span></span>

```output
There is no context attached to the incoming message for the service
and the current operation is not marked with "CanCreateInstance = true".
In order to communicate with this service check whether the incoming binding
supports the context protocol and has a valid context initialized.
```

 <span data-ttu-id="95c5e-139"><xref:System.ServiceModel.Activities.SendReply> puede devolver la información de contexto que se utiliza para la correlación del contexto a la actividad de <xref:System.ServiceModel.Activities.Receive> que inicializa la correlación del contexto cuando se usa una operación bidireccional, o bien el elemento que realiza la llamada puede especificar la información si la operación es unidireccional.</span><span class="sxs-lookup"><span data-stu-id="95c5e-139">The context information that is used for context correlation can be returned by the <xref:System.ServiceModel.Activities.SendReply> to the <xref:System.ServiceModel.Activities.Receive> activity that initializes the context correlation when using a two-way operation, or it can be specified by the caller if the operation is one-way.</span></span> <span data-ttu-id="95c5e-140">Si el elemento que realiza la llamada no envía el contexto o el servicio de flujo de trabajo no lo devuelve, se devolverá el mismo <xref:System.ServiceModel.FaultException> descrito previamente cuando se invoque la operación siguiente.</span><span class="sxs-lookup"><span data-stu-id="95c5e-140">If the context is not sent by the caller or returned by the workflow service, then the same <xref:System.ServiceModel.FaultException> described previously will be returned when a subsequent operation is invoked.</span></span>

## <a name="common-request-reply-correlation-issues"></a><span data-ttu-id="95c5e-141">Problemas comunes de la correlación de solicitud-respuesta</span><span class="sxs-lookup"><span data-stu-id="95c5e-141">Common Request-Reply Correlation Issues</span></span>

 <span data-ttu-id="95c5e-142">La correlación de solicitud-respuesta se utiliza con un <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> par para implementar una operación bidireccional en un servicio de flujo de trabajo y con un <xref:System.ServiceModel.Activities.Send> / <xref:System.ServiceModel.Activities.ReceiveReply> par que invoca una operación bidireccional en otro servicio Web.</span><span class="sxs-lookup"><span data-stu-id="95c5e-142">Request-reply correlation is used with a <xref:System.ServiceModel.Activities.Receive>/<xref:System.ServiceModel.Activities.SendReply> pair to implement a two-way operation in a workflow service and with a <xref:System.ServiceModel.Activities.Send>/<xref:System.ServiceModel.Activities.ReceiveReply> pair that invokes a two-way operation in another Web service.</span></span> <span data-ttu-id="95c5e-143">Al invocar una operación bidireccional en un servicio WCF, el servicio puede ser un servicio de WCF basado en código imperativo tradicional o puede ser un servicio de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="95c5e-143">When invoking a two-way operation in a WCF service, the service can be either a traditional imperative code-based WCF service or it can be a workflow service.</span></span> <span data-ttu-id="95c5e-144">Para utilizar la correlación de solicitud-respuesta, se debe utilizar un enlace bidireccional, como <xref:System.ServiceModel.BasicHttpBinding>, y las operaciones deben ser bidireccionales.</span><span class="sxs-lookup"><span data-stu-id="95c5e-144">To use request-reply correlation a two-way binding must be used, such as <xref:System.ServiceModel.BasicHttpBinding>, and the operations must be two-way.</span></span>

 <span data-ttu-id="95c5e-145">Si el servicio de flujo de trabajo tiene operaciones bidireccionales en paralelo, o en pares o superpuestos <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> <xref:System.ServiceModel.Activities.Send> / <xref:System.ServiceModel.Activities.ReceiveReply> , la administración de identificadores de correlación implícita proporcionada por <xref:System.ServiceModel.Activities.WorkflowServiceHost> puede no ser suficiente, especialmente en escenarios de alto esfuerzo, y es posible que los mensajes no se enruten correctamente.</span><span class="sxs-lookup"><span data-stu-id="95c5e-145">If the workflow service has two-way operations in parallel, or overlapping <xref:System.ServiceModel.Activities.Receive>/<xref:System.ServiceModel.Activities.SendReply> or <xref:System.ServiceModel.Activities.Send>/<xref:System.ServiceModel.Activities.ReceiveReply> pairs, then the implicit correlation handle management provided by <xref:System.ServiceModel.Activities.WorkflowServiceHost> may not be sufficient, especially in high-stress scenarios, and messages may not be correctly routed.</span></span> <span data-ttu-id="95c5e-146">Para evitar que este problema se produzca, recomendamos especificar <xref:System.ServiceModel.Activities.CorrelationHandle> siempre explícitamente al utilizar la correlación de solicitud-respuesta.</span><span class="sxs-lookup"><span data-stu-id="95c5e-146">To prevent this issue from occurring, we recommend that you always explicitly specify a <xref:System.ServiceModel.Activities.CorrelationHandle> when using request-reply correlation.</span></span> <span data-ttu-id="95c5e-147">Al usar las plantillas **SendAndReceiveReply** y **ReceiveAndSendReply** de la sección mensajería del **cuadro de herramientas** en el diseñador de flujo de trabajo, <xref:System.ServiceModel.Activities.CorrelationHandle> se configura explícitamente de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="95c5e-147">When using the **SendAndReceiveReply** and **ReceiveAndSendReply** templates from the Messaging section of the **Toolbox** in the workflow designer, a <xref:System.ServiceModel.Activities.CorrelationHandle> is explicitly configured by default.</span></span> <span data-ttu-id="95c5e-148">Al crear un flujo de trabajo con código, el <xref:System.ServiceModel.Activities.CorrelationHandle> se especifica en la propiedad <xref:System.ServiceModel.Activities.Receive.CorrelationInitializers%2A> de la primera actividad del par.</span><span class="sxs-lookup"><span data-stu-id="95c5e-148">When building a workflow by using code, the <xref:System.ServiceModel.Activities.CorrelationHandle> is specified in the <xref:System.ServiceModel.Activities.Receive.CorrelationInitializers%2A> of the first activity in the pair.</span></span> <span data-ttu-id="95c5e-149">En el siguiente ejemplo, se configura una actividad de <xref:System.ServiceModel.Activities.Receive> con una propiedad <xref:System.ServiceModel.Activities.CorrelationInitializer.CorrelationHandle%2A> explícita especificada en <xref:System.ServiceModel.Activities.RequestReplyCorrelationInitializer>.</span><span class="sxs-lookup"><span data-stu-id="95c5e-149">In the following example, a <xref:System.ServiceModel.Activities.Receive> activity is configured with an explicit <xref:System.ServiceModel.Activities.CorrelationInitializer.CorrelationHandle%2A> specified in the <xref:System.ServiceModel.Activities.RequestReplyCorrelationInitializer>.</span></span>

```csharp
Variable<CorrelationHandle> RRHandle = new Variable<CorrelationHandle>();

Receive StartOrder = new Receive
{
    CanCreateInstance = true,
    ServiceContractName = OrderContractName,
    OperationName = "StartOrder",
    CorrelationInitializers =
    {
        new RequestReplyCorrelationInitializer
        {
            CorrelationHandle = RRHandle
        }
    }
};

SendReply ReplyToStartOrder = new SendReply
{
    Request = StartOrder,
    Content = ... // Contains the return value, if any.
};

// Construct a workflow using StartOrder and ReplyToStartOrder.
```

 <span data-ttu-id="95c5e-150">No se permite la persistencia entre un <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> par o un <xref:System.ServiceModel.Activities.Send> / <xref:System.ServiceModel.Activities.ReceiveReply> par.</span><span class="sxs-lookup"><span data-stu-id="95c5e-150">Persistence is not permitted between a <xref:System.ServiceModel.Activities.Receive>/<xref:System.ServiceModel.Activities.SendReply> pair or a <xref:System.ServiceModel.Activities.Send>/<xref:System.ServiceModel.Activities.ReceiveReply> pair.</span></span> <span data-ttu-id="95c5e-151">Se crea una zona sin persistencia que dura hasta que ambas actividades se han completado.</span><span class="sxs-lookup"><span data-stu-id="95c5e-151">A no-persist zone is created that lasts until both activities have completed.</span></span> <span data-ttu-id="95c5e-152">Si en esta zona sin persistencia hay una actividad, por ejemplo una actividad de demora, y provoca que el flujo de trabajo se vuelva inactivo, este no persistirá ni siquiera aunque el host se configure para hacer persistir los flujos de trabajo cuando se vuelvan inactivos.</span><span class="sxs-lookup"><span data-stu-id="95c5e-152">If an activity, such as a delay activity, is in this no-persist zone and causes the workflow to become idle, the workflow will not persist even if it the host is configured to persist workflows when they become idle.</span></span> <span data-ttu-id="95c5e-153">Si una actividad, por ejemplo una actividad de persistencia, intenta persistir de modo explícito en la zona sin persistencia, se inicia una excepción grave, el flujo de trabajo se anula y se devuelve un objeto <xref:System.ServiceModel.FaultException> al autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="95c5e-153">If an activity, such as a persist activity, attempts to explicitly persist in the no-persist zone, a fatal exception is thrown, the workflow aborts, and a <xref:System.ServiceModel.FaultException> is returned to the caller.</span></span> <span data-ttu-id="95c5e-154">El mensaje de la excepción grave es "System.InvalidOperationException: las actividades persistentes no pueden estar incluidas en bloques sin persistencia.".</span><span class="sxs-lookup"><span data-stu-id="95c5e-154">The fatal exception message is "System.InvalidOperationException: Persist activities cannot be contained within no persistence blocks.".</span></span> <span data-ttu-id="95c5e-155">Esta excepción no se devuelve al autor de la llamada pero puede observarse si se habilita el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="95c5e-155">This exception is not returned to the caller but can be observed if tracking is enabled.</span></span> <span data-ttu-id="95c5e-156">El mensaje para el objeto <xref:System.ServiceModel.FaultException> devuelto al autor de la llamada es "No se puede realizar la operación porque WorkflowInstance '5836145b-7da2-49d0-a052-a49162adeab6' se ha completado".</span><span class="sxs-lookup"><span data-stu-id="95c5e-156">The message for the <xref:System.ServiceModel.FaultException> returned to the caller is "The operation could not be performed because WorkflowInstance '5836145b-7da2-49d0-a052-a49162adeab6' has completed".</span></span>

 <span data-ttu-id="95c5e-157">Para obtener más información acerca de la correlación de solicitud-respuesta, consulte [solicitud y respuesta](request-reply-correlation.md).</span><span class="sxs-lookup"><span data-stu-id="95c5e-157">For more information about request-reply correlation, see [Request-Reply](request-reply-correlation.md).</span></span>

## <a name="common-content-correlation-issues"></a><span data-ttu-id="95c5e-158">Problemas comunes de la correlación de contenido</span><span class="sxs-lookup"><span data-stu-id="95c5e-158">Common Content Correlation Issues</span></span>

 <span data-ttu-id="95c5e-159">La correlación basada en contenido se utiliza cuando un servicio de flujo de trabajo recibe varios mensajes y un dato de los mensajes intercambiados identifica la instancia deseada.</span><span class="sxs-lookup"><span data-stu-id="95c5e-159">Content-based correlation is used when a workflow service receives multiple messages and a piece of data in the exchanged messages identifies the desired instance.</span></span> <span data-ttu-id="95c5e-160">La correlación basada en contenidos usa estos datos en el mensaje, como un número de cliente o un identificador de orden, para enrutar los mensajes a la instancia de flujo de trabajo correcta.</span><span class="sxs-lookup"><span data-stu-id="95c5e-160">Content-based correlation uses this data in the message, such as a customer number or order ID, to route messages to the correct workflow instance.</span></span> <span data-ttu-id="95c5e-161">Esta sección describe varios problemas comunes que se pueden producir al utilizar la correlación basada en contenido.</span><span class="sxs-lookup"><span data-stu-id="95c5e-161">This section describes several common issues that may occur when using content-based correlation.</span></span>

### <a name="ensure-the-identifying-data-is-unique"></a><span data-ttu-id="95c5e-162">Asegurarse de que los datos de identificación son únicos</span><span class="sxs-lookup"><span data-stu-id="95c5e-162">Ensure the Identifying Data Is Unique</span></span>

 <span data-ttu-id="95c5e-163">A los datos que se utilizan para identificar la instancia se les aplica un algoritmo hash en una clave de correlación.</span><span class="sxs-lookup"><span data-stu-id="95c5e-163">The data that is used to identify the instance is hashed into a correlation key.</span></span> <span data-ttu-id="95c5e-164">Preste atención para garantizar que los datos que se usan para la correlación son únicos; de otro modo, podrían producirse colisiones en la clave a la que se ha aplicado un algoritmo hash y hacer que los mensajes se envíen a un destino incorrecto.</span><span class="sxs-lookup"><span data-stu-id="95c5e-164">Care must be taken to guarantee that the data that is used for correlation is unique or else collisions in the hashed key might occur and cause messages to be misrouted.</span></span> <span data-ttu-id="95c5e-165">Por ejemplo, una correlación basada solamente en un nombre de cliente puede producir una colisión porque puede haber múltiples clientes que tengan el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="95c5e-165">For example, a correlation based only on a customer name may cause a collision because there may be multiple customers who have the same name.</span></span> <span data-ttu-id="95c5e-166">Los dos puntos (:) no se deberían utilizar como parte de los datos empleados para la correlación del mensaje, porque ya se utilizan para delimitar el valor y la clave de la consulta del mensaje para formar la cadena a la que, posteriormente, se aplica un algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="95c5e-166">The colon (:) should not be used as part of the data that is used to correlate the message because it is already used to delimit the message query’s key and value to form the string that is subsequently hashed.</span></span> <span data-ttu-id="95c5e-167">Si se utiliza la persistencia, asegúrese de que los datos identificativos actuales no se han utilizado por una instancia conservada anteriormente.</span><span class="sxs-lookup"><span data-stu-id="95c5e-167">If persistence is being used, make sure that the current identifying data has not been used by a previously persisted instance.</span></span> <span data-ttu-id="95c5e-168">Deshabilitar la persistencia temporalmente puede ayudar a identificar este problema.</span><span class="sxs-lookup"><span data-stu-id="95c5e-168">Temporarily disabling persistence can help identify this issue.</span></span> <span data-ttu-id="95c5e-169">El seguimiento de WCF se puede utilizar para ver la clave de correlación calculada y es de utilidad para depurar este tipo de problema.</span><span class="sxs-lookup"><span data-stu-id="95c5e-169">WCF tracing can be used to view the calculated correlation key and is useful for debugging this kind of issue.</span></span>

### <a name="race-conditions"></a><span data-ttu-id="95c5e-170">Condiciones de carrera</span><span class="sxs-lookup"><span data-stu-id="95c5e-170">Race Conditions</span></span>

 <span data-ttu-id="95c5e-171">Hay un pequeño intervalo de tiempo entre el momento en que el servicio recibe un mensaje y el momento en que la correlación se inicializa realmente, durante el cual se omitirán los mensajes siguientes.</span><span class="sxs-lookup"><span data-stu-id="95c5e-171">There is a small gap in time between the service receiving a message and the correlation actually being initialized, during which follow-up messages will be ignored.</span></span> <span data-ttu-id="95c5e-172">Si un servicio de flujo de trabajo inicializa la correlación basada en contenido utilizando los datos pasados del cliente a través de una operación unidireccional y el elemento que llama envía los mensajes de seguimiento inmediatos, estos mensajes se omitirán durante este intervalo.</span><span class="sxs-lookup"><span data-stu-id="95c5e-172">If a workflow service initializes the content-based correlation by using data passed from the client over a one-way operation, and the caller sends immediate follow-up messages, these messages will be ignored during this interval.</span></span> <span data-ttu-id="95c5e-173">Esto se puede evitar utilizando una operación bidireccional para inicializar la correlación o utilizando <xref:System.ServiceModel.Activities.TransactedReceiveScope>.</span><span class="sxs-lookup"><span data-stu-id="95c5e-173">This can be avoided by using a two-way operation to initialize the correlation, or by using a <xref:System.ServiceModel.Activities.TransactedReceiveScope>.</span></span>

### <a name="correlation-query-issues"></a><span data-ttu-id="95c5e-174">Cuestiones relacionadas con las consultas de correlación</span><span class="sxs-lookup"><span data-stu-id="95c5e-174">Correlation Query Issues</span></span>

 <span data-ttu-id="95c5e-175">Las consultas de correlación se utilizan para especificar los datos de un mensaje que se utilizan para poner en correlación el mensaje.</span><span class="sxs-lookup"><span data-stu-id="95c5e-175">Correlation queries are used to specify what data in a message is used to correlate the message.</span></span> <span data-ttu-id="95c5e-176">Estos datos se especifican utilizando una consulta XPath.</span><span class="sxs-lookup"><span data-stu-id="95c5e-176">This data is specified by using an XPath query.</span></span> <span data-ttu-id="95c5e-177">Si no se envían los mensajes a un servicio aunque todo parezca correcto, una estrategia correcta para solucionar problemas es especificar un valor literal que coincida con el valor de los datos de mensaje en lugar de una consulta XPath.</span><span class="sxs-lookup"><span data-stu-id="95c5e-177">If messages to a service are not being dispatched even though everything appears to be correct, one strategy for troubleshooting is to specify a literal value that matches the value of the message data instead of an XPath query.</span></span> <span data-ttu-id="95c5e-178">Para especificar un valor literal, utilice la función `string`.</span><span class="sxs-lookup"><span data-stu-id="95c5e-178">To specify a literal value, use the `string` function.</span></span> <span data-ttu-id="95c5e-179">En el siguiente ejemplo, <xref:System.ServiceModel.MessageQuerySet> se configura para utilizar el valor literal de `11445` para `OrderId` y la consulta XPath se saca del comentario.</span><span class="sxs-lookup"><span data-stu-id="95c5e-179">In the following example, a <xref:System.ServiceModel.MessageQuerySet> is configured to use a literal value of `11445` for the `OrderId` and the XPath query is commented out.</span></span>

```csharp
MessageQuerySet = new MessageQuerySet
{
    {
        "OrderId",
        //new XPathMessageQuery("sm:body()/tempuri:StartOrderResponse/tempuri:OrderId")
        new XPathMessageQuery("string('11445')")
    }
}
```

 <span data-ttu-id="95c5e-180">Si se configura incorrectamente una consulta XPath de modo que no se recuperen los datos de correlación, se devuelve un error con el mensaje siguiente: "Una consulta de correlación produjo un conjunto de resultados vacío.</span><span class="sxs-lookup"><span data-stu-id="95c5e-180">If an XPath query is configured incorrectly such that no correlation data is retrieved, a fault is returned with the following message: "A correlation query yielded an empty result set.</span></span> <span data-ttu-id="95c5e-181">Asegúrese de que las consultas de correlación del extremo están configuradas correctamente.".</span><span class="sxs-lookup"><span data-stu-id="95c5e-181">Please ensure correlation queries for the endpoint are correctly configured."</span></span> <span data-ttu-id="95c5e-182">Un modo rápido de solucionar esto es reemplazar la consulta XPath con un valor literal según se describe en la sección anterior.</span><span class="sxs-lookup"><span data-stu-id="95c5e-182">One quick way to troubleshoot this is to replace the XPath query with a literal value as described in the previous section.</span></span> <span data-ttu-id="95c5e-183">Este problema puede producirse si se usa el generador de consultas XPath en los cuadros de diálogo **Agregar inicializadores de correlación** o **definición de CorrelatesOn** y el servicio de flujo de trabajo utiliza contratos de mensaje.</span><span class="sxs-lookup"><span data-stu-id="95c5e-183">This issue can occur if you use the XPath query builder in the **Add Correlation Initializers** or **CorrelatesOn Definition** dialog boxes and your workflow service uses message contracts.</span></span> <span data-ttu-id="95c5e-184">En el ejemplo siguiente, se define una clase de contrato de mensaje.</span><span class="sxs-lookup"><span data-stu-id="95c5e-184">In the following example, a message contract class is defined.</span></span>

```csharp
[MessageContract]
public class AddItemMessage
{
    [MessageHeader]
    public string CartId;

    [MessageBodyMember]
    public string Item;
}
```

 <span data-ttu-id="95c5e-185">Una actividad <xref:System.ServiceModel.Activities.Receive> usa este contrato de mensaje en un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="95c5e-185">This message contract is used by a <xref:System.ServiceModel.Activities.Receive> activity in a workflow.</span></span> <span data-ttu-id="95c5e-186">El `CartId` del encabezado del mensaje se usa para correlacionar el mensaje con la instancia correcta.</span><span class="sxs-lookup"><span data-stu-id="95c5e-186">The `CartId` in the header of the message is used to correlate the message to the correct instance.</span></span> <span data-ttu-id="95c5e-187">Si la consulta XPath que recupera el `CartId` se crea con los cuadros de diálogo de correlación del diseñador de flujo de trabajo, se genera la siguiente consulta XPath incorrecta.</span><span class="sxs-lookup"><span data-stu-id="95c5e-187">If the XPath query that retrieves the `CartId` is created using the correlation dialogs in the workflow designer, the following incorrect XPath query is generated.</span></span>

```
sm:body()/xg0:AddItemMessage/xg0:CartId
```

 <span data-ttu-id="95c5e-188">Esta consulta XPath sería correcta si la actividad <xref:System.ServiceModel.Activities.Receive> usó parámetros para los datos, pero dado que usa un contrato de mensaje, es incorrecta.</span><span class="sxs-lookup"><span data-stu-id="95c5e-188">This XPath query would be correct if the <xref:System.ServiceModel.Activities.Receive> activity used parameters for the data, but since it is using a message contract it is incorrect.</span></span> <span data-ttu-id="95c5e-189">La consulta XPath siguiente es la correcta para recuperar el `CartId` del encabezado.</span><span class="sxs-lookup"><span data-stu-id="95c5e-189">The following XPath query is the correct XPath query to retrieve the `CartId` from the header.</span></span>

```
sm:header()/tempuri:CartId
```

<span data-ttu-id="95c5e-190">Esto se puede confirmar examinando el cuerpo del mensaje.</span><span class="sxs-lookup"><span data-stu-id="95c5e-190">This can be confirmed by examining the body of the message.</span></span>

```xml
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header>
    <Action s:mustUnderstand="1" xmlns="http://schemas.microsoft.com/ws/2005/05/addressing/none">http://tempuri.org/IService/AddItem</Action>
    <h:CartId xmlns:h="http://tempuri.org/">80c95b41-c98d-4660-a6c1-99412206e54c</h:CartId>
  </s:Header>
  <s:Body>
    <AddItemMessage xmlns="http://tempuri.org/">
      <Item>Books</Item>
    </AddItemMessage>
  </s:Body>
</s:Envelope>
```

<span data-ttu-id="95c5e-191">El ejemplo siguiente muestra una actividad <xref:System.ServiceModel.Activities.Receive> configurada para una operación `AddItem` que usa el contrato de mensaje anterior para recuperar datos.</span><span class="sxs-lookup"><span data-stu-id="95c5e-191">The following example shows a <xref:System.ServiceModel.Activities.Receive> activity configured for an `AddItem` operation that uses the previous message contract to receive data.</span></span> <span data-ttu-id="95c5e-192">La consulta XPath está configurada correctamente.</span><span class="sxs-lookup"><span data-stu-id="95c5e-192">The XPath query is correctly configured.</span></span>

```xaml
<Receive CorrelatesWith="[CCHandle] OperationName="AddItem" ServiceContractName="p:IService">
  <Receive.CorrelatesOn>
    <XPathMessageQuery x:Key="key1">
      <XPathMessageQuery.Namespaces>
        <ssx:XPathMessageContextMarkup>
          <x:String x:Key="xg0">http://schemas.datacontract.org/2004/07/MessageContractWFService</x:String>
        </ssx:XPathMessageContextMarkup>
      </XPathMessageQuery.Namespaces>sm:header()/tempuri:CartId</XPathMessageQuery>
  </Receive.CorrelatesOn>
  <ReceiveMessageContent DeclaredMessageType="m:AddItemMessage">
    <p1:OutArgument x:TypeArguments="m:AddItemMessage">[AddItemMessage]</p1:OutArgument>
  </ReceiveMessageContent>
</Receive>
```
