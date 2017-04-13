---
title: "Utilizar un enlace personalizado con el canal del cliente de detecci&#243;n | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 36f95e75-04f7-44f3-a995-a0d623624d7f
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# Utilizar un enlace personalizado con el canal del cliente de detecci&#243;n
Al utilizar un enlace personalizado con <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>, debe definir una clase <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider> que cree las instancias <xref:System.ServiceModel.Discovery.DiscoveryEndpoint>.  
  
## Crear un DiscoveryEndpointProvider  
 La clase <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider> es la responsable de la creación de [T:System:ServiceModel.Discovery.DiscoveryEndpoints](assetId:///T:System:ServiceModel.Discovery.DiscoveryEndpoints?qualifyHint=False&amp;autoUpgrade=True) a petición.Para definir un proveedor de extremo de detección, derive una clase de <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider> e invalide el método <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider.GetDiscoveryEndpoint%2A> y, a continuación, devuelva un nuevo extremo de detección.En el siguiente ejemplo, se muestra cómo crear un proveedor de extremo de detección.  
  
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
  
 Cuando haya definido el proveedor de extremo de detección, podrá crear un enlace personalizado y agregar <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>, que hace referencia al proveedor de extremo de detección, tal y como se muestra en el siguiente ejemplo.  
  
```  
DiscoveryClientBindingElement discoveryBindingElement = new DiscoveryClientBindingElement();  
  
// Provide the search criteria and the endpoint over which the probe is sent.  
discoveryBindingElement.FindCriteria = new FindCriteria(typeof(ICalculatorService));  
discoveryBindingElement.DiscoveryEndpointProvider = new UdpDiscoveryEndpointProvider();  
  
CustomBinding customBinding = new CustomBinding(new NetTcpBinding());  
// Insert DiscoveryClientBindingElement at the top of the BindingElement stack.  
// An exception is thrown if this binding element is not at the top.  
customBinding.Elements.Insert(0, discoveryBindingElement);  
```  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)] el uso del canal de cliente de detección, vea [Usar el canal del cliente de detección](../../../../docs/framework/wcf/feature-details/using-the-discovery-client-channel.md).Para obtener un ejemplo de código completo, vea [Ejemplo de elemento de enlace de detección](../../../../docs/framework/wcf/samples/discovery-binding-element-sample.md).  
  
## Vea también  
 [Información general de Detección de WCF](../../../../docs/framework/wcf/feature-details/wcf-discovery-overview.md)   
 [Usar el canal del cliente de detección](../../../../docs/framework/wcf/feature-details/using-the-discovery-client-channel.md)   
 [Ejemplo de elemento de enlace de detección](../../../../docs/framework/wcf/samples/discovery-binding-element-sample.md)