---
title: Utilizar un enlace personalizado con el canal del cliente de detección
ms.date: 03/30/2017
ms.assetid: 36f95e75-04f7-44f3-a995-a0d623624d7f
ms.openlocfilehash: 4ef85b4c52c1f27b333413e2b6178452142d313f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33498363"
---
# <a name="using-a-custom-binding-with-the-discovery-client-channel"></a>Utilizar un enlace personalizado con el canal del cliente de detección
Al utilizar un enlace personalizado con <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>, debe definir una clase <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider> que cree las instancias <xref:System.ServiceModel.Discovery.DiscoveryEndpoint>.  
  
## <a name="creating-a-discoveryendpointprovider"></a>Crear un DiscoveryEndpointProvider  
 El <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider> es responsable de crear <xref:System.ServiceModel.Discovery.DiscoveryEndpoint> instancias a petición. Para definir un proveedor de extremo de detección, derive una clase de <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider> e invalide el método <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider.GetDiscoveryEndpoint%2A> y, a continuación, devuelva un nuevo extremo de detección. En el siguiente ejemplo, se muestra cómo crear un proveedor de extremo de detección.  
  
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
  
 Para obtener más información acerca de cómo utilizar el canal de cliente de detección, consulte [utilizando el canal de cliente de detección](../../../../docs/framework/wcf/feature-details/using-the-discovery-client-channel.md). Para obtener un ejemplo de código completo, vea [ejemplo de elemento de enlace de detección](../../../../docs/framework/wcf/samples/discovery-binding-element-sample.md)  
  
## <a name="see-also"></a>Vea también  
 [Información general de Detección de WCF](../../../../docs/framework/wcf/feature-details/wcf-discovery-overview.md)  
 [Uso del canal del cliente de detección](../../../../docs/framework/wcf/feature-details/using-the-discovery-client-channel.md)  
 [Ejemplo de elemento de enlace de detección](../../../../docs/framework/wcf/samples/discovery-binding-element-sample.md)
