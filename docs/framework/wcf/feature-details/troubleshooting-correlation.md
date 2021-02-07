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
# <a name="troubleshooting-correlation"></a>Solución de problemas de correlación

La correlación se utiliza para relacionar los mensajes del servicio de flujo de trabajo entre sí y con la instancia de flujo de trabajo correcta, pero si no está configurada correctamente, los mensajes no se recibirán y las aplicaciones no funcionarán de forma adecuada. Este tema proporciona información general de varios métodos para solucionar problemas de la correlación y también enumera algunos problemas comunes que se pueden producir cuando se usa.

## <a name="handle-the-unknownmessagereceived-event"></a>Administrar el evento UnknownMessageReceived

 El evento <xref:System.ServiceModel.ServiceHostBase.UnknownMessageReceived> se produce cuando un servicio recibe un mensaje desconocido, incluidos los mensajes que no se pueden poner en correlación con una instancia existente. Para los servicios autohospedados, este evento se puede administrar en la aplicación host.

```csharp
host.UnknownMessageReceived += delegate(object sender, UnknownMessageReceivedEventArgs e)
{
    Console.WriteLine("Unknown Message Received:");
    Console.WriteLine(e.Message);
};
```

 Para los servicios hospedados en web, este evento se puede administrar derivando una clase de <xref:System.ServiceModel.Activities.Activation.WorkflowServiceHostFactory> e invalidando el método <xref:System.ServiceModel.Activities.Activation.WorkflowServiceHostFactory.CreateWorkflowServiceHost%2A>.

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

 Esta clase <xref:System.ServiceModel.Activities.Activation.WorkflowServiceHostFactory> personalizada se puede especificar entonces en el archivo `svc` para el servicio.

`<% @ServiceHost Language="C#" Service="OrderServiceWorkflow" Factory="CustomFactory" %>`

 Cuando se invoca este controlador, el mensaje se puede recuperar utilizando la propiedad <xref:System.ServiceModel.UnknownMessageReceivedEventArgs.Message%2A> de la clase <xref:System.ServiceModel.UnknownMessageReceivedEventArgs> y se parecerá al siguiente mensaje.

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

 Al inspeccionar los mensajes enviados al controlador del evento <xref:System.ServiceModel.ServiceHostBase.UnknownMessageReceived>, se pueden proporcionar pistas acerca de por qué el mensaje no estaba en correlación con una instancia del servicio de flujo de trabajo.

## <a name="use-tracking-to-monitor-the-progress-of-the-workflow"></a>Seguimiento del uso para supervisar el progreso del flujo de trabajo

 El seguimiento ofrece una manera de supervisar el progreso de un flujo de trabajo. De forma predeterminada, se emiten registros de seguimiento para los eventos de ciclo de vida de flujo de trabajo, los eventos de ciclo de vida de actividad, la propagación de errores y la reanudación de marcadores. Además, las actividades personalizadas pueden emitir registros de seguimiento personalizados. Al solucionar los problemas de la correlación, los registros más útiles son los de seguimiento de las actividades, de la reanudación de marcadores y de la propagación de errores. Los registros de seguimiento de actividades se pueden utilizar para determinar el progreso actual del flujo de trabajo y pueden ayudar a identificar qué actividad de mensajería está esperando actualmente mensajes. Los registros de reanudación de marcadores son útiles porque indican que el flujo de trabajo recibió un mensaje, y los registros de propagación de errores proporcionan un registro de los errores en el flujo de trabajo. Para habilitar el seguimiento, especifique el objeto<xref:System.Activities.Tracking.TrackingParticipant> deseado en la propiedad <xref:System.ServiceModel.Activities.WorkflowServiceHost.WorkflowExtensions%2A> de la clase <xref:System.ServiceModel.Activities.WorkflowServiceHost>. En el ejemplo siguiente, el `ConsoleTrackingParticipant` (del ejemplo de [seguimiento personalizado](../../windows-workflow-foundation/samples/custom-tracking.md) ) se configura mediante el perfil de seguimiento predeterminado.

```csharp
host.WorkflowExtensions.Add(new ConsoleTrackingParticipant());
```

 Un participante del seguimiento como ConsoleTrackingParticipant es útil para los servicios de flujo de trabajo autohospedados que tengan una ventana de la consola. Para un servicio hospedado en Web, se debe usar un participante de seguimiento que registre la información de seguimiento en un almacén duradero, como el integrado <xref:System.Activities.Tracking.EtwTrackingParticipant> , o un participante de seguimiento personalizado que registre la información en un archivo.

 Para obtener más información sobre el seguimiento y la configuración del seguimiento de un servicio de flujo de trabajo hospedado en Web, vea seguimiento y seguimiento de [flujos de trabajo](../../windows-workflow-foundation/workflow-tracking-and-tracing.md), [configuración del seguimiento de un flujo de trabajo](../../windows-workflow-foundation/configuring-tracking-for-a-workflow.md)y ejemplos de [seguimiento &#91;WF&#93;](../../windows-workflow-foundation/samples/tracking.md) ejemplos.

## <a name="use-wcf-tracing"></a>Usar el seguimiento de WCF

 El seguimiento de WCF permite el seguimiento del flujo de mensajes de un servicio de flujo de trabajo. Esta información de seguimiento resulta útil cuando se solucionan los problemas de la correlación, en especial en el caso de la correlación basada en el contenido. Para habilitar el seguimiento, especifique los agentes de escucha de seguimiento que desee en la sección `system.diagnostics` del archivo `web.config` si el servicio del flujo de trabajo es hospedado en web, o el archivo `app.config`, si el servicio de flujo de trabajo es autohospedado. Para incluir el contenido de los mensajes en el archivo de seguimiento, especifique `true` en `logEntireMessage` en el elemento `messageLogging` de la sección `diagnostics` de `system.serviceModel`. En el siguiente ejemplo, la información de seguimiento, incluido el contenido de los mensajes, se configura para escribirse en un archivo que se denomina `service.svclog`.

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

 Para ver la información de seguimiento contenida en `service.svclog` , se usa la [herramienta Service Trace Viewer (SvcTraceViewer.exe)](../service-trace-viewer-tool-svctraceviewer-exe.md) . Esto es especialmente útil cuando se solucionan los problemas de la correlación basada en contenido porque puede ver el contenido de los mensajes y ver lo que se pasa exactamente, y si coincide el <xref:System.ServiceModel.CorrelationQuery> con la correlación basada en contenido. Para obtener más información sobre el seguimiento de WCF, vea [herramienta Visor de seguimiento de servicio (SvcTraceViewer.exe)](../service-trace-viewer-tool-svctraceviewer-exe.md), [configurar el seguimiento](../diagnostics/tracing/configuring-tracing.md)y [usar el seguimiento para solucionar problemas de la aplicación](../diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md).

## <a name="common-context-exchange-correlation-issues"></a>Problemas comunes de la correlación de intercambio del contexto

 Ciertos tipos de correlación requieren que se use un tipo específico de enlace para que la correlación funcione correctamente. En los ejemplos se incluye la correlación de tipo solicitud-respuesta, que requiere un enlace bidireccional como <xref:System.ServiceModel.BasicHttpBinding>, y la correlación de intercambio de contexto, que requiere un enlace basado en contexto como <xref:System.ServiceModel.BasicHttpContextBinding>. La mayoría de los enlaces admiten las operaciones bidireccionales, de modo que no es un problema común de la correlación de solicitud-respuesta, pero solo hay algunos enlaces basados en contexto incluidos <xref:System.ServiceModel.BasicHttpContextBinding>, <xref:System.ServiceModel.WSHttpContextBinding> y <xref:System.ServiceModel.NetTcpContextBinding>. Si no se utiliza alguno de estos enlaces, la llamada inicial a un servicio de flujo de trabajo tendrá éxito, pero se producirá un error en las llamadas posteriores con la siguiente <xref:System.ServiceModel.FaultException>.

```output
There is no context attached to the incoming message for the service
and the current operation is not marked with "CanCreateInstance = true".
In order to communicate with this service check whether the incoming binding
supports the context protocol and has a valid context initialized.
```

 <xref:System.ServiceModel.Activities.SendReply> puede devolver la información de contexto que se utiliza para la correlación del contexto a la actividad de <xref:System.ServiceModel.Activities.Receive> que inicializa la correlación del contexto cuando se usa una operación bidireccional, o bien el elemento que realiza la llamada puede especificar la información si la operación es unidireccional. Si el elemento que realiza la llamada no envía el contexto o el servicio de flujo de trabajo no lo devuelve, se devolverá el mismo <xref:System.ServiceModel.FaultException> descrito previamente cuando se invoque la operación siguiente.

## <a name="common-request-reply-correlation-issues"></a>Problemas comunes de la correlación de solicitud-respuesta

 La correlación de solicitud-respuesta se utiliza con un <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> par para implementar una operación bidireccional en un servicio de flujo de trabajo y con un <xref:System.ServiceModel.Activities.Send> / <xref:System.ServiceModel.Activities.ReceiveReply> par que invoca una operación bidireccional en otro servicio Web. Al invocar una operación bidireccional en un servicio WCF, el servicio puede ser un servicio de WCF basado en código imperativo tradicional o puede ser un servicio de flujo de trabajo. Para utilizar la correlación de solicitud-respuesta, se debe utilizar un enlace bidireccional, como <xref:System.ServiceModel.BasicHttpBinding>, y las operaciones deben ser bidireccionales.

 Si el servicio de flujo de trabajo tiene operaciones bidireccionales en paralelo, o en pares o superpuestos <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> <xref:System.ServiceModel.Activities.Send> / <xref:System.ServiceModel.Activities.ReceiveReply> , la administración de identificadores de correlación implícita proporcionada por <xref:System.ServiceModel.Activities.WorkflowServiceHost> puede no ser suficiente, especialmente en escenarios de alto esfuerzo, y es posible que los mensajes no se enruten correctamente. Para evitar que este problema se produzca, recomendamos especificar <xref:System.ServiceModel.Activities.CorrelationHandle> siempre explícitamente al utilizar la correlación de solicitud-respuesta. Al usar las plantillas **SendAndReceiveReply** y **ReceiveAndSendReply** de la sección mensajería del **cuadro de herramientas** en el diseñador de flujo de trabajo, <xref:System.ServiceModel.Activities.CorrelationHandle> se configura explícitamente de forma predeterminada. Al crear un flujo de trabajo con código, el <xref:System.ServiceModel.Activities.CorrelationHandle> se especifica en la propiedad <xref:System.ServiceModel.Activities.Receive.CorrelationInitializers%2A> de la primera actividad del par. En el siguiente ejemplo, se configura una actividad de <xref:System.ServiceModel.Activities.Receive> con una propiedad <xref:System.ServiceModel.Activities.CorrelationInitializer.CorrelationHandle%2A> explícita especificada en <xref:System.ServiceModel.Activities.RequestReplyCorrelationInitializer>.

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

 No se permite la persistencia entre un <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> par o un <xref:System.ServiceModel.Activities.Send> / <xref:System.ServiceModel.Activities.ReceiveReply> par. Se crea una zona sin persistencia que dura hasta que ambas actividades se han completado. Si en esta zona sin persistencia hay una actividad, por ejemplo una actividad de demora, y provoca que el flujo de trabajo se vuelva inactivo, este no persistirá ni siquiera aunque el host se configure para hacer persistir los flujos de trabajo cuando se vuelvan inactivos. Si una actividad, por ejemplo una actividad de persistencia, intenta persistir de modo explícito en la zona sin persistencia, se inicia una excepción grave, el flujo de trabajo se anula y se devuelve un objeto <xref:System.ServiceModel.FaultException> al autor de la llamada. El mensaje de la excepción grave es "System.InvalidOperationException: las actividades persistentes no pueden estar incluidas en bloques sin persistencia.". Esta excepción no se devuelve al autor de la llamada pero puede observarse si se habilita el seguimiento. El mensaje para el objeto <xref:System.ServiceModel.FaultException> devuelto al autor de la llamada es "No se puede realizar la operación porque WorkflowInstance '5836145b-7da2-49d0-a052-a49162adeab6' se ha completado".

 Para obtener más información acerca de la correlación de solicitud-respuesta, consulte [solicitud y respuesta](request-reply-correlation.md).

## <a name="common-content-correlation-issues"></a>Problemas comunes de la correlación de contenido

 La correlación basada en contenido se utiliza cuando un servicio de flujo de trabajo recibe varios mensajes y un dato de los mensajes intercambiados identifica la instancia deseada. La correlación basada en contenidos usa estos datos en el mensaje, como un número de cliente o un identificador de orden, para enrutar los mensajes a la instancia de flujo de trabajo correcta. Esta sección describe varios problemas comunes que se pueden producir al utilizar la correlación basada en contenido.

### <a name="ensure-the-identifying-data-is-unique"></a>Asegurarse de que los datos de identificación son únicos

 A los datos que se utilizan para identificar la instancia se les aplica un algoritmo hash en una clave de correlación. Preste atención para garantizar que los datos que se usan para la correlación son únicos; de otro modo, podrían producirse colisiones en la clave a la que se ha aplicado un algoritmo hash y hacer que los mensajes se envíen a un destino incorrecto. Por ejemplo, una correlación basada solamente en un nombre de cliente puede producir una colisión porque puede haber múltiples clientes que tengan el mismo nombre. Los dos puntos (:) no se deberían utilizar como parte de los datos empleados para la correlación del mensaje, porque ya se utilizan para delimitar el valor y la clave de la consulta del mensaje para formar la cadena a la que, posteriormente, se aplica un algoritmo hash. Si se utiliza la persistencia, asegúrese de que los datos identificativos actuales no se han utilizado por una instancia conservada anteriormente. Deshabilitar la persistencia temporalmente puede ayudar a identificar este problema. El seguimiento de WCF se puede utilizar para ver la clave de correlación calculada y es de utilidad para depurar este tipo de problema.

### <a name="race-conditions"></a>Condiciones de carrera

 Hay un pequeño intervalo de tiempo entre el momento en que el servicio recibe un mensaje y el momento en que la correlación se inicializa realmente, durante el cual se omitirán los mensajes siguientes. Si un servicio de flujo de trabajo inicializa la correlación basada en contenido utilizando los datos pasados del cliente a través de una operación unidireccional y el elemento que llama envía los mensajes de seguimiento inmediatos, estos mensajes se omitirán durante este intervalo. Esto se puede evitar utilizando una operación bidireccional para inicializar la correlación o utilizando <xref:System.ServiceModel.Activities.TransactedReceiveScope>.

### <a name="correlation-query-issues"></a>Cuestiones relacionadas con las consultas de correlación

 Las consultas de correlación se utilizan para especificar los datos de un mensaje que se utilizan para poner en correlación el mensaje. Estos datos se especifican utilizando una consulta XPath. Si no se envían los mensajes a un servicio aunque todo parezca correcto, una estrategia correcta para solucionar problemas es especificar un valor literal que coincida con el valor de los datos de mensaje en lugar de una consulta XPath. Para especificar un valor literal, utilice la función `string`. En el siguiente ejemplo, <xref:System.ServiceModel.MessageQuerySet> se configura para utilizar el valor literal de `11445` para `OrderId` y la consulta XPath se saca del comentario.

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

 Si se configura incorrectamente una consulta XPath de modo que no se recuperen los datos de correlación, se devuelve un error con el mensaje siguiente: "Una consulta de correlación produjo un conjunto de resultados vacío. Asegúrese de que las consultas de correlación del extremo están configuradas correctamente.". Un modo rápido de solucionar esto es reemplazar la consulta XPath con un valor literal según se describe en la sección anterior. Este problema puede producirse si se usa el generador de consultas XPath en los cuadros de diálogo **Agregar inicializadores de correlación** o **definición de CorrelatesOn** y el servicio de flujo de trabajo utiliza contratos de mensaje. En el ejemplo siguiente, se define una clase de contrato de mensaje.

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

 Una actividad <xref:System.ServiceModel.Activities.Receive> usa este contrato de mensaje en un flujo de trabajo. El `CartId` del encabezado del mensaje se usa para correlacionar el mensaje con la instancia correcta. Si la consulta XPath que recupera el `CartId` se crea con los cuadros de diálogo de correlación del diseñador de flujo de trabajo, se genera la siguiente consulta XPath incorrecta.

```
sm:body()/xg0:AddItemMessage/xg0:CartId
```

 Esta consulta XPath sería correcta si la actividad <xref:System.ServiceModel.Activities.Receive> usó parámetros para los datos, pero dado que usa un contrato de mensaje, es incorrecta. La consulta XPath siguiente es la correcta para recuperar el `CartId` del encabezado.

```
sm:header()/tempuri:CartId
```

Esto se puede confirmar examinando el cuerpo del mensaje.

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

El ejemplo siguiente muestra una actividad <xref:System.ServiceModel.Activities.Receive> configurada para una operación `AddItem` que usa el contrato de mensaje anterior para recuperar datos. La consulta XPath está configurada correctamente.

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
