---
title: Procedimiento Creación de instancias de servicio de control
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e0b12b34-8004-443a-a46d-83a5c00f2601
ms.openlocfilehash: 3e1e0669b083e30db01c571c44830adfaff31d79
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54515318"
---
# <a name="how-to-control-service-instancing"></a><span data-ttu-id="7d13d-102">Procedimiento Creación de instancias de servicio de control</span><span class="sxs-lookup"><span data-stu-id="7d13d-102">How to: Control Service Instancing</span></span>
<span data-ttu-id="7d13d-103">Establecer el modo de instancia de un servicio le permite especificar cuándo se crea (y su objeto de servicio  asociado definido por el usuario) <xref:System.ServiceModel.InstanceContext?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="7d13d-103">Setting the instance mode of a service enables you to specify when a <xref:System.ServiceModel.InstanceContext?displayProperty=nameWithType> (and its associated user-defined service object) is created.</span></span> <span data-ttu-id="7d13d-104">Vea la enumeración de <xref:System.ServiceModel.InstanceContextMode> para los posibles modos.</span><span class="sxs-lookup"><span data-stu-id="7d13d-104">See the <xref:System.ServiceModel.InstanceContextMode> enumeration for the possible modes.</span></span> <span data-ttu-id="7d13d-105">Para obtener más información acerca de los comportamientos, consulte [configurar y extender el tiempo de ejecución con comportamientos](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md).</span><span class="sxs-lookup"><span data-stu-id="7d13d-105">For more information about behaviors, see [Configuring and Extending the Runtime with Behaviors](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md).</span></span> <span data-ttu-id="7d13d-106">Para obtener ejemplos, vea [comportamientos](../../../../docs/framework/wcf/samples/behaviors.md).</span><span class="sxs-lookup"><span data-stu-id="7d13d-106">For working examples, see [Behaviors](../../../../docs/framework/wcf/samples/behaviors.md).</span></span>  
  
### <a name="to-control-the-service-instance-lifetime-using-code"></a><span data-ttu-id="7d13d-107">Para controlar la duración de instancia de servicio mediante el código</span><span class="sxs-lookup"><span data-stu-id="7d13d-107">To control the service instance lifetime using code</span></span>  
  
1.  <span data-ttu-id="7d13d-108">Aplique <xref:System.ServiceModel.ServiceBehaviorAttribute> a la clase de servicio.</span><span class="sxs-lookup"><span data-stu-id="7d13d-108">Apply the <xref:System.ServiceModel.ServiceBehaviorAttribute> to the service class.</span></span>  
  
2.  <span data-ttu-id="7d13d-109">Establezca la propiedad <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> a uno de los siguientes valores: <xref:System.ServiceModel.InstanceContextMode.PerCall>, <xref:System.ServiceModel.InstanceContextMode.PerSession>, o <xref:System.ServiceModel.InstanceContextMode.Single>.</span><span class="sxs-lookup"><span data-stu-id="7d13d-109">Set the <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> property to one of the following values: <xref:System.ServiceModel.InstanceContextMode.PerCall>, <xref:System.ServiceModel.InstanceContextMode.PerSession>, or <xref:System.ServiceModel.InstanceContextMode.Single>.</span></span>  
  
     [!code-csharp[C_ControlServiceInstancing#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_controlserviceinstancing/cs/source.cs#1)]
     [!code-vb[C_ControlServiceInstancing#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_controlserviceinstancing/vb/source.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="7d13d-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7d13d-110">Example</span></span>  
 <span data-ttu-id="7d13d-111">El siguiente ejemplo de código establece la propiedad <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> del atributo <xref:System.ServiceModel.ServiceBehaviorAttribute> en <xref:System.ServiceModel.InstanceContextMode.PerCall>.</span><span class="sxs-lookup"><span data-stu-id="7d13d-111">The following code example sets the <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> property of the <xref:System.ServiceModel.ServiceBehaviorAttribute> attribute to <xref:System.ServiceModel.InstanceContextMode.PerCall>.</span></span>  
  
 [!code-csharp[c_ControlServiceInstancing#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_controlserviceinstancing/cs/source.cs#2)]
 [!code-vb[c_ControlServiceInstancing#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_controlserviceinstancing/vb/source.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="7d13d-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="7d13d-112">See also</span></span>
- <xref:System.ServiceModel.ServiceBehaviorAttribute>
- <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A>
- <xref:System.ServiceModel.InstanceContextMode>
- [<span data-ttu-id="7d13d-113">Servicio: Ejemplos de comportamientos</span><span class="sxs-lookup"><span data-stu-id="7d13d-113">Service: Behaviors Samples</span></span>](https://msdn.microsoft.com/library/4e3c6513-a7ff-4b35-8dcf-b5506c6f39a7)
