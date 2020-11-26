---
title: Procedimiento para inspeccionar y modificar mensajes en el servicio
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 9c5b1cc7-84f3-45f8-9226-d59c278e8c42
ms.openlocfilehash: 8d1ce6ef00462adb38e3d59c3d9bd35694c4dbe9
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96249064"
---
# <a name="how-to-inspect-and-modify-messages-on-the-service"></a><span data-ttu-id="b9c46-102">Procedimiento para inspeccionar y modificar mensajes en el servicio</span><span class="sxs-lookup"><span data-stu-id="b9c46-102">How to: Inspect and Modify Messages on the Service</span></span>

<span data-ttu-id="b9c46-103">Puede inspeccionar o modificar los mensajes entrantes o salientes a través de un cliente Windows Communication Foundation (WCF) implementando <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=nameWithType> e insertando en el tiempo de ejecución del servicio.</span><span class="sxs-lookup"><span data-stu-id="b9c46-103">You can inspect or modify the incoming or outgoing messages across a Windows Communication Foundation (WCF) client by implementing a <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=nameWithType> and inserting it into the service runtime.</span></span> <span data-ttu-id="b9c46-104">Para obtener más información, consulte [extensión de distribuidores](extending-dispatchers.md).</span><span class="sxs-lookup"><span data-stu-id="b9c46-104">For more information, see [Extending Dispatchers](extending-dispatchers.md).</span></span> <span data-ttu-id="b9c46-105">La característica equivalente del servicio es <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b9c46-105">The equivalent feature on the service is the <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=nameWithType>.</span></span>  
  
### <a name="to-inspect-or-modify-messages"></a><span data-ttu-id="b9c46-106">Inspeccionar o modificar los mensajes</span><span class="sxs-lookup"><span data-stu-id="b9c46-106">To inspect or modify messages</span></span>  
  
1. <span data-ttu-id="b9c46-107">Implemente la interfaz <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b9c46-107">Implement the <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=nameWithType> interface.</span></span>  
  
2. <span data-ttu-id="b9c46-108">Implemente una interfaz <xref:System.ServiceModel.Description.IServiceBehavior?displayProperty=nameWithType>, <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType>, o <xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType> dependiendo del ámbito en el que desee insertar fácilmente su inspector de mensajes de servicio.</span><span class="sxs-lookup"><span data-stu-id="b9c46-108">Implement a <xref:System.ServiceModel.Description.IServiceBehavior?displayProperty=nameWithType>, <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType>, or <xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType> interface depending upon the scope at which you want to easily insert your service message inspector.</span></span>  
  
3. <span data-ttu-id="b9c46-109">Inserte su comportamiento antes de llamar al método <xref:System.ServiceModel.ICommunicationObject.Open%2A?displayProperty=nameWithType> en <xref:System.ServiceModel.ServiceHost?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b9c46-109">Insert your behavior prior to calling the <xref:System.ServiceModel.ICommunicationObject.Open%2A?displayProperty=nameWithType> method on the <xref:System.ServiceModel.ServiceHost?displayProperty=nameWithType>.</span></span> <span data-ttu-id="b9c46-110">Para obtener más información, consulte [configuración y extensión del tiempo de ejecución con comportamientos](configuring-and-extending-the-runtime-with-behaviors.md).</span><span class="sxs-lookup"><span data-stu-id="b9c46-110">For details, see [Configuring and Extending the Runtime with Behaviors](configuring-and-extending-the-runtime-with-behaviors.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b9c46-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b9c46-111">Example</span></span>  

 <span data-ttu-id="b9c46-112">Los siguientes ejemplos de código muestran, en orden:</span><span class="sxs-lookup"><span data-stu-id="b9c46-112">The following code examples show, in order:</span></span>  
  
- <span data-ttu-id="b9c46-113">Una implementación de inspector de servicio.</span><span class="sxs-lookup"><span data-stu-id="b9c46-113">A service inspector implementation.</span></span>  
  
- <span data-ttu-id="b9c46-114">Un comportamiento del servicio que inserta el inspector.</span><span class="sxs-lookup"><span data-stu-id="b9c46-114">A service behavior that inserts the inspector.</span></span>  
  
- <span data-ttu-id="b9c46-115">Un archivo de configuración que carga y ejecuta el comportamiento en una aplicación de servicio.</span><span class="sxs-lookup"><span data-stu-id="b9c46-115">A configuration file that loads and runs the behavior in a service application.</span></span>  
  
 [!code-csharp[Interceptors#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/interceptors.cs#7)]
 [!code-vb[Interceptors#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/interceptors/vb/interceptors.vb#7)]  
  
 [!code-csharp[Interceptors#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/insertingbehaviors.cs#8)]
 [!code-vb[Interceptors#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/interceptors/vb/insertingbehaviors.vb#8)]  
  
 [!code-xml[Interceptors#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/hostapplication.exe.config#9)]  
  
## <a name="see-also"></a><span data-ttu-id="b9c46-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="b9c46-116">See also</span></span>

- <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=nameWithType>
- <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=nameWithType>
- [<span data-ttu-id="b9c46-117">Configuración y extensión del tiempo de ejecución con comportamientos</span><span class="sxs-lookup"><span data-stu-id="b9c46-117">Configuring and Extending the Runtime with Behaviors</span></span>](configuring-and-extending-the-runtime-with-behaviors.md)
