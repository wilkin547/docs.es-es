---
title: "Ejemplo de elemento de enlace de detección"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: af513015-85bf-417b-8729-1bdff77ff6d6
caps.latest.revision: "12"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 821f629a7f39869975af19c793fe26188a40d7d6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="discovery-binding-element-sample"></a>Ejemplo de elemento de enlace de detección
En este ejemplo se muestra cómo utilizar el elemento de enlace de cliente de detección para detectar un servicio. Esta característica permite a los desarrolladores de software agregar un canal de cliente de detección a su pila del canal de clientes existente, con lo que el modelo de programación resulta muy intuitivo. Cuando se abre el canal asociado, la dirección del servicio se resuelve utilizando la detección. Este ejemplo consta de los siguientes proyectos:  
  
-   **CalculatorService**: un reconocible [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] servicio.  
  
-   **CalculatorClient**: un [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] aplicación cliente que utiliza el canal de cliente de detección para buscar y llamar a CalculatorService.  
  
-   **DynamicCalculatorClient**: un [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] aplicación cliente que utiliza un extremo dinámico para buscar y llamar a CalculatorService.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\DiscoveryBindingElement`  
  
## <a name="calculatorservice"></a>CalculatorService  
 Este proyecto contiene un servicio de calculadora sencillo que implementa el contrato de la interfaz `ICalculatorService`.  
  
 El siguiente archivo App.config se utiliza para agregar un comportamiento `<serviceDiscovery>` en los comportamientos del servicio, así como el extremo de detección.  
  
```xml  
<system.serviceModel>  
    <services>  
      <service behaviorConfiguration="CalculatorBehavior" name="Microsoft.Samples.Discovery.CalculatorService">  
        <endpoint name="udpDiscoveryEpt" kind="udpDiscoveryEndpoint" />  
      </service>  
    </services>  
    <behaviors>  
      <!--Enable discovery through configuration.-->  
      <serviceBehaviors>  
        <behavior name="CalculatorBehavior">  
          <serviceDiscovery>  
          </serviceDiscovery>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  </system.serviceModel>  
```  
  
 Esto hace que el servicio y sus extremos se puedan detectar. CalculatorService es un servicio autohospedado que agrega un extremo mediante el enlace NetTcpBinding. También agrega un `EndpointDiscoveryBehavior` al extremo y especifica un ámbito como se muestra en el siguiente código.  
  
```  
// Add a NET.TCP endpoint and add a scope to that endpoint.  
ServiceEndpoint netTcpEndpoint = serviceHost.AddServiceEndpoint(typeof(ICalculatorService), new NetTcpBinding(), netTcpAddress);  
EndpointDiscoveryBehavior netTctEndpointBehavior = new EndpointDiscoveryBehavior();  
netTctEndpointBehavior.Scopes.Add(new Uri("ldap:///ou=engineering,o=exampleorg,c=us"));  
netTcpEndpoint.Behaviors.Add(netTctEndpointBehavior);  
serviceHost.Open();  
```  
  
## <a name="calculatorclient"></a>CalculatorClient  
 Este proyecto contiene una implementación del cliente que envía los mensajes a CalculatorService. Este programa utiliza el método `CreateCustomBindingWithDiscoveryElement()` para crear un enlace personalizado que utiliza el canal de cliente de detección.  
  
```  
static CustomBinding CreateCustomBindingWithDiscoveryElement()  
 {  
      DiscoveryClientBindingElement discoveryBindingElement = new DiscoveryClientBindingElement();  
  
            // Provide the search criteria and the endpoint over which the probe is sent  
            discoveryBindingElement.FindCriteria = new FindCriteria(typeof(ICalculatorService));  
            discoveryBindingElement.DiscoveryEndpointProvider = new UdpDiscoveryEndpointProvider();  
  
            CustomBinding customBinding = new CustomBinding(new NetTcpBinding());  
            // Insert DiscoveryClientBindingElement at the top of the BindingElement stack.  
            // An exception is thrown if this binding element is not at the top  
            customBinding.Elements.Insert(0, discoveryBindingElement);  
  
            return customBinding; }  
```  
  
 Una vez creado el objeto <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>, el desarrollador de software especifica los criterios que se usan al buscar un servicio. En este caso, el criterio de búsqueda de detección es el tipo de la interfaz `ICalculatorService`. Además, el desarrollador de software especifica un <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider> que devuelve un <xref:System.ServiceModel.Discovery.DiscoveryEndpoint> que especifica dónde buscar los servicios. El <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider> devuelve una nueva instancia de <xref:System.ServiceModel.Discovery.DiscoveryEndpoint>. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Mediante un enlace personalizado con el canal de cliente de detección](../../../../docs/framework/wcf/feature-details/using-a-custom-binding-with-the-discovery-client-channel.md).  
  
```  
// Extend DiscoveryEndpointProvider class to change the default DiscoveryEndpoint  
    // to the DiscoveryClientBindingElement. The Discovery ClientChannel   
    // uses this endpoint to send Probe message.  
    public class UdpDiscoveryEndpointProvider : DiscoveryEndpointProvider  
    {  
        public override DiscoveryEndpoint GetDiscoveryEndpoint()  
        {  
            return new UdpDiscoveryEndpoint(DiscoveryVersion.WSDiscoveryApril2005);  
        }  
    }  
```  
  
 En este caso, el cliente utiliza el mecanismo de multidifusión de UDP definido por el protocolo de detección para buscar los servicios en la subred local. El resto del método crea un enlace personalizado e inserta el elemento de enlace de detección en la parte superior de la pila.  
  
> [!NOTE]
>  <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement> se debe colocar en la parte superior de la pila de enlaces. El objeto <xref:System.ServiceModel.Channels.BindingElement> sobre <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement> debe asegurarse de que el generador de canales o el canal que crea no use las propiedades `EndpointAddress` o `Via`, porque la dirección real solo se encuentra en el canal del cliente de detección.  
  
 Después, se puede crear una instancia de `CalculatorClient` pasando este enlace personalizado así como una dirección del extremo.  
  
```  
CalculatorServiceClient client = new CalculatorServiceClient(CreateCustomBindingWithDiscoveryElement(), DiscoveryClientBindingElement.DiscoveryEndpointAddress);  
```  
  
 Al usar el canal de cliente de detección, se pasa la dirección constante de extremo especificada anteriormente. Ahora en tiempo de ejecución, el canal de cliente de detección encuentra el servicio especificado por los criterios de búsqueda y se conecta a él. Para que el servicio y el cliente establezcan una conexión, deben tener también la misma pila de enlaces subyacente.  
  
#### <a name="to-use-this-sample"></a>Para utilizar este ejemplo  
  
1.  Abra la solución en [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].  
  
2.  Compile la solución.  
  
3.  Ejecute la aplicación de servicio y cada una de las aplicaciones cliente.  
  
4.  Observe que el cliente pudo encontrar el servicio sin conocer su dirección.  
  
## <a name="see-also"></a>Vea también
