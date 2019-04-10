---
title: Filtrar para inspeccionar y modificar mensajes en el servicio
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 9c5b1cc7-84f3-45f8-9226-d59c278e8c42
ms.openlocfilehash: 87f9cf5040ffb757799c51d598d0755847c5bfd9
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59340651"
---
# <a name="how-to-inspect-and-modify-messages-on-the-service"></a><span data-ttu-id="3dcd2-102">Filtrar para inspeccionar y modificar mensajes en el servicio</span><span class="sxs-lookup"><span data-stu-id="3dcd2-102">How to: Inspect and Modify Messages on the Service</span></span>
<span data-ttu-id="3dcd2-103">Puede inspeccionar o modificar los mensajes entrantes o salientes a través de un cliente de Windows Communication Foundation (WCF) mediante la implementación de un <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=nameWithType> e insertarlos en el runtime del servicio.</span><span class="sxs-lookup"><span data-stu-id="3dcd2-103">You can inspect or modify the incoming or outgoing messages across a Windows Communication Foundation (WCF) client by implementing a <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=nameWithType> and inserting it into the service runtime.</span></span> <span data-ttu-id="3dcd2-104">Para obtener más información, consulte [extender distribuidores](../../../../docs/framework/wcf/extending/extending-dispatchers.md).</span><span class="sxs-lookup"><span data-stu-id="3dcd2-104">For more information, see [Extending Dispatchers](../../../../docs/framework/wcf/extending/extending-dispatchers.md).</span></span> <span data-ttu-id="3dcd2-105">La característica equivalente del servicio es <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="3dcd2-105">The equivalent feature on the service is the <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=nameWithType>.</span></span>  
  
### <a name="to-inspect-or-modify-messages"></a><span data-ttu-id="3dcd2-106">Inspeccionar o modificar los mensajes</span><span class="sxs-lookup"><span data-stu-id="3dcd2-106">To inspect or modify messages</span></span>  
  
1. <span data-ttu-id="3dcd2-107">Implementar la interfaz <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="3dcd2-107">Implement the <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=nameWithType> interface.</span></span>  
  
2. <span data-ttu-id="3dcd2-108">Implemente una interfaz <xref:System.ServiceModel.Description.IServiceBehavior?displayProperty=nameWithType>, <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType>, o <xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType> dependiendo del ámbito en el que desee insertar fácilmente su inspector de mensajes de servicio.</span><span class="sxs-lookup"><span data-stu-id="3dcd2-108">Implement a <xref:System.ServiceModel.Description.IServiceBehavior?displayProperty=nameWithType>, <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType>, or <xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType> interface depending upon the scope at which you want to easily insert your service message inspector.</span></span>  
  
3. <span data-ttu-id="3dcd2-109">Inserte su comportamiento antes de llamar al método <xref:System.ServiceModel.ICommunicationObject.Open%2A?displayProperty=nameWithType> en <xref:System.ServiceModel.ServiceHost?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="3dcd2-109">Insert your behavior prior to calling the <xref:System.ServiceModel.ICommunicationObject.Open%2A?displayProperty=nameWithType> method on the <xref:System.ServiceModel.ServiceHost?displayProperty=nameWithType>.</span></span> <span data-ttu-id="3dcd2-110">Para obtener más información, consulte [configurar y extender el tiempo de ejecución con comportamientos](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md).</span><span class="sxs-lookup"><span data-stu-id="3dcd2-110">For details, see [Configuring and Extending the Runtime with Behaviors](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3dcd2-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3dcd2-111">Example</span></span>  
 <span data-ttu-id="3dcd2-112">Los siguientes ejemplos de código muestran, en orden:</span><span class="sxs-lookup"><span data-stu-id="3dcd2-112">The following code examples show, in order:</span></span>  
  
-   <span data-ttu-id="3dcd2-113">Una implementación de inspector de servicio.</span><span class="sxs-lookup"><span data-stu-id="3dcd2-113">A service inspector implementation.</span></span>  
  
-   <span data-ttu-id="3dcd2-114">Un comportamiento del servicio que inserta el inspector.</span><span class="sxs-lookup"><span data-stu-id="3dcd2-114">A service behavior that inserts the inspector.</span></span>  
  
-   <span data-ttu-id="3dcd2-115">Un archivo de configuración que carga y ejecuta el comportamiento en una aplicación de servicio.</span><span class="sxs-lookup"><span data-stu-id="3dcd2-115">A configuration file that loads and runs the behavior in a service application.</span></span>  
  
 [!code-csharp[Interceptors#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/interceptors.cs#7)]
 [!code-vb[Interceptors#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/interceptors/vb/interceptors.vb#7)]  
  
 [!code-csharp[Interceptors#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/insertingbehaviors.cs#8)]
 [!code-vb[Interceptors#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/interceptors/vb/insertingbehaviors.vb#8)]  
  
 [!code-xml[Interceptors#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/hostapplication.exe.config#9)]  
  
## <a name="see-also"></a><span data-ttu-id="3dcd2-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="3dcd2-116">See also</span></span>

- <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=nameWithType>
- <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=nameWithType>
- [<span data-ttu-id="3dcd2-117">Configuración y extensión del tiempo de ejecución con comportamientos</span><span class="sxs-lookup"><span data-stu-id="3dcd2-117">Configuring and Extending the Runtime with Behaviors</span></span>](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)
