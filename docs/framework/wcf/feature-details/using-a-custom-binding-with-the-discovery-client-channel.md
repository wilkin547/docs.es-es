---
title: Utilizar un enlace personalizado con el canal del cliente de detección
ms.date: 03/30/2017
ms.assetid: 36f95e75-04f7-44f3-a995-a0d623624d7f
ms.openlocfilehash: 49983c3ab303d3839350af72b1aa4821c071fe99
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84595042"
---
# <a name="using-a-custom-binding-with-the-discovery-client-channel"></a><span data-ttu-id="fde8a-102">Utilizar un enlace personalizado con el canal del cliente de detección</span><span class="sxs-lookup"><span data-stu-id="fde8a-102">Using a Custom Binding with the Discovery Client Channel</span></span>
<span data-ttu-id="fde8a-103">Al utilizar un enlace personalizado con <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>, debe definir una clase <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider> que cree las instancias <xref:System.ServiceModel.Discovery.DiscoveryEndpoint>.</span><span class="sxs-lookup"><span data-stu-id="fde8a-103">When using a custom binding with the <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>, you must define a <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider> that creates <xref:System.ServiceModel.Discovery.DiscoveryEndpoint> instances.</span></span>  
  
## <a name="creating-a-discoveryendpointprovider"></a><span data-ttu-id="fde8a-104">Crear un DiscoveryEndpointProvider</span><span class="sxs-lookup"><span data-stu-id="fde8a-104">Creating a DiscoveryEndpointProvider</span></span>  
 <span data-ttu-id="fde8a-105">El <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider> es responsable de crear <xref:System.ServiceModel.Discovery.DiscoveryEndpoint> instancias a petición.</span><span class="sxs-lookup"><span data-stu-id="fde8a-105">The <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider> is responsible for creating <xref:System.ServiceModel.Discovery.DiscoveryEndpoint> instances on demand.</span></span> <span data-ttu-id="fde8a-106">Para definir un proveedor de extremo de detección, derive una clase de <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider> e invalide el método <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider.GetDiscoveryEndpoint%2A> y, a continuación, devuelva un nuevo extremo de detección.</span><span class="sxs-lookup"><span data-stu-id="fde8a-106">To define a discovery endpoint provider, derive a class from <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider> and override the <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider.GetDiscoveryEndpoint%2A> method and return a new discovery endpoint.</span></span> <span data-ttu-id="fde8a-107">En el siguiente ejemplo, se muestra cómo crear un proveedor de extremo de detección.</span><span class="sxs-lookup"><span data-stu-id="fde8a-107">The following example shows how to create a discovery endpoint provider.</span></span>  
  
```csharp
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
  
 <span data-ttu-id="fde8a-108">Cuando haya definido el proveedor de extremo de detección, podrá crear un enlace personalizado y agregar <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>, que hace referencia al proveedor de extremo de detección, tal y como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="fde8a-108">Once you have defined the discovery endpoint provider you can create a custom binding and add the <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>, which references the discovery endpoint provider as shown in the following example.</span></span>  
  
```csharp
DiscoveryClientBindingElement discoveryBindingElement = new DiscoveryClientBindingElement();  
  
// Provide the search criteria and the endpoint over which the probe is sent.  
discoveryBindingElement.FindCriteria = new FindCriteria(typeof(ICalculatorService));  
discoveryBindingElement.DiscoveryEndpointProvider = new UdpDiscoveryEndpointProvider();  
  
CustomBinding customBinding = new CustomBinding(new NetTcpBinding());  
// Insert DiscoveryClientBindingElement at the top of the BindingElement stack.  
// An exception is thrown if this binding element is not at the top.  
customBinding.Elements.Insert(0, discoveryBindingElement);  
```  
  
 <span data-ttu-id="fde8a-109">Para obtener más información sobre el uso del canal de cliente de detección, vea [usar el canal de cliente de detección](using-the-discovery-client-channel.md).</span><span class="sxs-lookup"><span data-stu-id="fde8a-109">For more information about using the discovery client channel, see [Using the Discovery Client Channel](using-the-discovery-client-channel.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="fde8a-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="fde8a-110">See also</span></span>

- [<span data-ttu-id="fde8a-111">Información general de Detección de WCF</span><span class="sxs-lookup"><span data-stu-id="fde8a-111">WCF Discovery Overview</span></span>](wcf-discovery-overview.md)
- [<span data-ttu-id="fde8a-112">Usar el canal del cliente de detección</span><span class="sxs-lookup"><span data-stu-id="fde8a-112">Using the Discovery Client Channel</span></span>](using-the-discovery-client-channel.md)
