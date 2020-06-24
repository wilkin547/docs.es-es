---
title: Servicios dúplex
description: Aprenda a crear un contrato de servicio dúplex en WCF, que permite que ambos extremos envíen mensajes entre sí a través de un canal creado por el cliente.
ms.date: 05/09/2018
dev_langs:
- csharp
- vb
ms.assetid: 396b875a-d203-4ebe-a3a1-6a330d962e95
ms.openlocfilehash: a43bb63a0ccf1a34b79dce755c19f7ed4cb6c16c
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "85247356"
---
# <a name="duplex-services"></a>Servicios dúplex

Un contrato de servicios dúplex es un patrón de intercambio de mensajes en el que ambos puntos de conexión pueden enviar mensajes al otro de manera independiente. Un servicio dúplex, por tanto, puede enviar mensajes de vuelta al punto de conexión del cliente, proporcionando un comportamiento parecido a los eventos. La comunicación dúplex se produce cuando un cliente se conecta a un servicio y proporciona al servicio un canal en el que el servicio puede devolver los mensajes al cliente. Tenga en cuenta que el comportamiento como evento de los servicios dúplex solo funciona dentro de una sesión.

Para crear un contrato dúplex ha de crear un par de interfaces. La primera es la interfaz del contrato de servicio, que describe las operaciones que un cliente puede invocar. Dicho contrato de servicio debe especificar un *contrato de devolución de llamada* en la <xref:System.ServiceModel.ServiceContractAttribute.CallbackContract%2A?displayProperty=nameWithType> propiedad. El contrato de devolución de llamadas es la interfaz que define las operaciones a las que el servicio puede llamar en el punto de conexión del cliente. Un contrato dúplex no requiere una sesión, aunque los enlaces dúplex proporcionados por el sistema las utilizan.

A continuación, se muestra un ejemplo de un contrato dúplex.

[!code-csharp[c_DuplexServices#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_duplexservices/cs/service.cs#0)]
[!code-vb[c_DuplexServices#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_duplexservices/vb/service.vb#0)]

La clase `CalculatorService` implementa la interfaz principal `ICalculatorDuplex`. El servicio utiliza el modo de instancia <xref:System.ServiceModel.InstanceContextMode.PerSession> para mantener el resultado para cada sesión. Una propiedad privada denominada `Callback` tiene acceso al canal de devolución de llamadas hasta el cliente. El servicio utiliza la devolución de llamadas para devolver los mensajes al cliente a través de la interfaz de devolución de llamadas, como se muestra en el siguiente código de muestra.

[!code-csharp[c_DuplexServices#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_duplexservices/cs/service.cs#1)]
[!code-vb[c_DuplexServices#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_duplexservices/vb/service.vb#1)]

El cliente debe proporcionar una clase que implemente la interfaz de devolución de llamadas del contrato dúplex para recibir los mensajes del servicio. En el siguiente ejemplo de código se muestra una clase `CallbackHandler` que implementa la interfaz `ICalculatorDuplexCallback`.

[!code-csharp[c_DuplexServices#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_duplexservices/cs/client.cs#2)]
[!code-vb[c_DuplexServices#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_duplexservices/vb/client.vb#2)]

El cliente de WCF que se genera para un contrato dúplex requiere que <xref:System.ServiceModel.InstanceContext> se proporcione una clase en la construcción. Esta clase <xref:System.ServiceModel.InstanceContext> se utiliza como sitio para un objeto que implementa la interfaz de devolución de llamadas y administra mensajes que se devuelven desde el servicio. Se construye una clase <xref:System.ServiceModel.InstanceContext> con una instancia de la clase `CallbackHandler`. Este objeto administra mensajes enviados desde el servicio al cliente en la interfaz de devolución de llamadas.

[!code-csharp[c_DuplexServices#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_duplexservices/cs/client.cs#3)]
[!code-vb[c_DuplexServices#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_duplexservices/vb/client.vb#3)]

La configuración del servicio debe realizarse para proporcionar un enlace que admita comunicación de la sesión y dúplex. El elemento `wsDualHttpBinding` admite la comunicación de la sesión y permite la comunicación dúplex proporcionando conexiones HTTP duales, una para cada dirección.

En el cliente, debe configurar una dirección que el servidor pueda utilizar para conectarse al cliente, como se muestra en la configuración del ejemplo siguiente.

> [!NOTE]
> Además, los clientes que no sean dúplex y que no se autentiquen mediante una conversación segura, normalmente, producen una <xref:System.ServiceModel.Security.MessageSecurityException>. Sin embargo, si un cliente dúplex que utiliza una conversación segura no se autentica, el cliente recibe una <xref:System.TimeoutException>.

Si crea un cliente/servicio mediante el elemento `WSHttpBinding` y no incluye el punto de conexión de devolución de llamada de cliente, recibirá el siguiente error.

```console
HTTP could not register URL
htp://+:80/Temporary_Listen_Addresses/<guid> because TCP port 80 is being used by another application.
```

En el código de ejemplo siguiente se muestra cómo especificar la dirección del punto de conexión de cliente mediante programación.

```csharp
WSDualHttpBinding binding = new WSDualHttpBinding();
EndpointAddress endptadr = new EndpointAddress("http://localhost:12000/DuplexTestUsingCode/Server");
binding.ClientBaseAddress = new Uri("http://localhost:8000/DuplexTestUsingCode/Client/");
```

```vb
Dim binding As New WSDualHttpBinding()
Dim endptadr As New EndpointAddress("http://localhost:12000/DuplexTestUsingCode/Server")
binding.ClientBaseAddress = New Uri("http://localhost:8000/DuplexTestUsingCode/Client/")
```

El siguiente ejemplo de código muestra cómo especificar la dirección de extremo de cliente mediante configuración.

```xml
<client>
    <endpoint name ="ServerEndpoint"
          address="http://localhost:12000/DuplexTestUsingConfig/Server"
          bindingConfiguration="WSDualHttpBinding_IDuplexTest"
            binding="wsDualHttpBinding"
           contract="IDuplexTest" />
</client>
<bindings>
    <wsDualHttpBinding>
        <binding name="WSDualHttpBinding_IDuplexTest"
          clientBaseAddress="http://localhost:8000/myClient/" >
            <security mode="None"/>
         </binding>
    </wsDualHttpBinding>
</bindings>
```

> [!WARNING]
> El modelo dúplex no detecta automáticamente cuando un servicio o cliente cierra su canal. Por tanto, si un cliente finaliza inesperadamente, de forma predeterminada no se notificará al servicio, o si un servicio finaliza inesperadamente, no se notificará al cliente. Si utiliza un servicio que está desconectado, <xref:System.ServiceModel.CommunicationException> se produce la excepción. Los clientes y los servicios pueden implementar su propio protocolo para notificarse si así lo deciden. Para obtener más información sobre el control de errores, vea [control de errores de WCF](../wcf-error-handling.md).

## <a name="see-also"></a>Vea también

- [Dúplex](../samples/duplex.md)
- [Especificación del comportamiento de tiempo de ejecución del cliente](../specifying-client-run-time-behavior.md)
- [Procedimiento para crear un generador de canales y usarlo para crear y administrar canales](how-to-create-a-channel-factory-and-use-it-to-create-and-manage-channels.md)
