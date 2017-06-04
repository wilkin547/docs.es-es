---
title: "Servicios d&#250;plex | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 396b875a-d203-4ebe-a3a1-6a330d962e95
caps.latest.revision: 17
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 17
---
# Servicios d&#250;plex
Un contrato de servicios dúplex es un patrón de intercambio de mensajes en el que ambos extremos pueden enviar mensajes al otro de manera independiente. Un servicio dúplex, por tanto, puede enviar mensajes de vuelta al extremo del cliente, proporcionando un comportamiento parecido a los eventos. La comunicación dúplex se produce cuando un cliente se conecta a un servicio y proporciona al servicio un canal en el que el servicio puede devolver los mensajes al cliente. Tenga en cuenta que el comportamiento como evento de los servicios dúplex solo funciona dentro de una sesión.  
  
 Para crear un contrato dúplex ha de crear un par de interfaces. La primera es la interfaz del contrato de servicio, que describe las operaciones que un cliente puede invocar. Ese contrato de servicio debe especificar un *contrato de devolución de llamada* en el <xref:System.ServiceModel.ServiceContractAttribute.CallbackContract%2A?displayProperty=fullName> propiedad. El contrato de devolución de llamadas es la interfaz que define las operaciones a las que el servicio puede llamar en el punto de conexión del cliente. Un contrato dúplex no requiere una sesión, aunque los enlaces dúplex proporcionados por el sistema las utilizan.  
  
 A continuación, se muestra un ejemplo de un contrato dúplex.  
  
 [!code-csharp[c_DuplexServices#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_duplexservices/cs/service.cs#0)]
 [!code-vb[c_DuplexServices#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_duplexservices/vb/service.vb#0)]  
  
 La clase `CalculatorService` implementa la interfaz principal `ICalculatorDuplex`. El servicio utiliza la <xref:System.ServiceModel.InstanceContextMode> modo de instancia para mantener el resultado para cada sesión. Una propiedad privada denominada `Callback` tiene acceso al canal de devolución de llamadas hasta el cliente. El servicio utiliza la devolución de llamadas para devolver los mensajes al cliente a través de la interfaz de devolución de llamadas, como se muestra en el siguiente código de muestra.  
  
 [!code-csharp[c_DuplexServices#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_duplexservices/cs/service.cs#1)]
 [!code-vb[c_DuplexServices#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_duplexservices/vb/service.vb#1)]  
  
 El cliente debe proporcionar una clase que implemente la interfaz de devolución de llamadas del contrato dúplex para recibir los mensajes del servicio. En el siguiente ejemplo de código se muestra una clase `CallbackHandler` que implementa la interfaz `ICalculatorDuplexCallback`.  
  
 [!code-csharp[c_DuplexServices#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_duplexservices/cs/client.cs#2)]
 [!code-vb[c_DuplexServices#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_duplexservices/vb/client.vb#2)]  
  
 El [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] cliente que se genera para un contrato dúplex requiere una <xref:System.ServiceModel.InstanceContext> clase proporcionarse en la construcción. Esto <xref:System.ServiceModel.InstanceContext> clase se utiliza como el sitio para un objeto que implementa la interfaz de devolución de llamada y administra mensajes que se envían desde el servicio. Un <xref:System.ServiceModel.InstanceContext> se crea una clase con una instancia de la `CallbackHandler` clase. Este objeto administra mensajes enviados desde el servicio al cliente en la interfaz de devolución de llamadas.  
  
 [!code-csharp[c_DuplexServices#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_duplexservices/cs/client.cs#3)]
 [!code-vb[c_DuplexServices#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_duplexservices/vb/client.vb#3)]  
  
 La configuración del servicio debe realizarse para proporcionar un enlace que admita comunicación de la sesión y dúplex. El elemento `wsDualHttpBinding` admite la comunicación de la sesión y permite la comunicación dúplex proporcionando conexiones HTTP duales, una para cada dirección.  
  
 En el cliente, debe configurar una dirección que el servidor pueda utilizar para conectarse al cliente, como se muestra en la configuración del ejemplo siguiente.  
  
  
  
> [!NOTE]
>  Los clientes que no sean dúplex que no se autentican mediante una conversación segura, normalmente producen un <xref:System.ServiceModel.Security.MessageSecurityException>. Sin embargo, si no se puede autenticar un cliente dúplex que utiliza una conversación segura, el cliente recibe un <xref:System.TimeoutException> en su lugar.  
  
 Si crea un cliente/servicio mediante el elemento `WSHttpBinding` y no incluye el extremo de devolución de llamada de cliente, recibirá el siguiente error.  
  
```  
HTTP could not register URL  
htp://+:80/Temporary_Listen_Addresses/<guid> because TCP port 80 is being used by another application.  
```  
  
 El siguiente ejemplo de código muestra cómo especificar la dirección de extremo de cliente mediante código.  
  
```  
WSDualHttpBinding binding = new WSDualHttpBinding();  
EndpointAddress endptadr = new EndpointAddress("http://localhost:12000/DuplexTestUsingCode/Server");  
binding.ClientBaseAddress = new Uri("http://localhost:8000/DuplexTestUsingCode/Client/");  
```  
  
 El siguiente ejemplo de código muestra cómo especificar la dirección de extremo de cliente mediante configuración.  
  
```  
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
>  El modelo dúplex no detecta automáticamente cuando un servicio o cliente cierra su canal. Por tanto, si un cliente finaliza inesperadamente, de forma predeterminada no se notificará al servicio. Los clientes y los servicios pueden implementar su propio protocolo para notificarse si así lo deciden.  
  
## <a name="see-also"></a>Vea también  
 [Dúplex](../../../../docs/framework/wcf/samples/duplex.md)   
 [Especificar el comportamiento de tiempo de ejecución de cliente](../../../../docs/framework/wcf/specifying-client-run-time-behavior.md)   
 [Cómo: crear un generador de canales y utilizarlo para crear y administrar canales](../../../../docs/framework/wcf/feature-details/how-to-create-a-channel-factory-and-use-it-to-create-and-manage-channels.md)