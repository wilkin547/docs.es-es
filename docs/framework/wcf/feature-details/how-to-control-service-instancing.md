---
description: 'Más información acerca de cómo: controlar la creación de instancias de servicio'
title: Procedimiento para controlar la creación de instancias de servicio
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e0b12b34-8004-443a-a46d-83a5c00f2601
ms.openlocfilehash: 014d7fb4b054a1b52c1fea671cd099267fba468c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99779925"
---
# <a name="how-to-control-service-instancing"></a><span data-ttu-id="f0de7-103">Procedimiento para controlar la creación de instancias de servicio</span><span class="sxs-lookup"><span data-stu-id="f0de7-103">How to: Control Service Instancing</span></span>

<span data-ttu-id="f0de7-104">Establecer el modo de instancia de un servicio le permite especificar cuándo se crea (y su objeto de servicio  asociado definido por el usuario) <xref:System.ServiceModel.InstanceContext?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f0de7-104">Setting the instance mode of a service enables you to specify when a <xref:System.ServiceModel.InstanceContext?displayProperty=nameWithType> (and its associated user-defined service object) is created.</span></span> <span data-ttu-id="f0de7-105">Vea la enumeración de <xref:System.ServiceModel.InstanceContextMode> para los posibles modos.</span><span class="sxs-lookup"><span data-stu-id="f0de7-105">See the <xref:System.ServiceModel.InstanceContextMode> enumeration for the possible modes.</span></span> <span data-ttu-id="f0de7-106">Para obtener más información sobre los comportamientos, vea [configuración y extensión del tiempo de ejecución con comportamientos](../extending/configuring-and-extending-the-runtime-with-behaviors.md).</span><span class="sxs-lookup"><span data-stu-id="f0de7-106">For more information about behaviors, see [Configuring and Extending the Runtime with Behaviors](../extending/configuring-and-extending-the-runtime-with-behaviors.md).</span></span> <span data-ttu-id="f0de7-107">Para obtener ejemplos prácticos, vea [Behaviors](../samples/behaviors.md).</span><span class="sxs-lookup"><span data-stu-id="f0de7-107">For working examples, see [Behaviors](../samples/behaviors.md).</span></span>  
  
### <a name="to-control-the-service-instance-lifetime-using-code"></a><span data-ttu-id="f0de7-108">Para controlar la duración de instancia de servicio mediante el código</span><span class="sxs-lookup"><span data-stu-id="f0de7-108">To control the service instance lifetime using code</span></span>  
  
1. <span data-ttu-id="f0de7-109">Aplique <xref:System.ServiceModel.ServiceBehaviorAttribute> a la clase de servicio.</span><span class="sxs-lookup"><span data-stu-id="f0de7-109">Apply the <xref:System.ServiceModel.ServiceBehaviorAttribute> to the service class.</span></span>  
  
2. <span data-ttu-id="f0de7-110">Establezca la propiedad <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> a uno de los siguientes valores: <xref:System.ServiceModel.InstanceContextMode.PerCall>, <xref:System.ServiceModel.InstanceContextMode.PerSession>, o <xref:System.ServiceModel.InstanceContextMode.Single>.</span><span class="sxs-lookup"><span data-stu-id="f0de7-110">Set the <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> property to one of the following values: <xref:System.ServiceModel.InstanceContextMode.PerCall>, <xref:System.ServiceModel.InstanceContextMode.PerSession>, or <xref:System.ServiceModel.InstanceContextMode.Single>.</span></span>  
  
     [!code-csharp[C_ControlServiceInstancing#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_controlserviceinstancing/cs/source.cs#1)]
     [!code-vb[C_ControlServiceInstancing#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_controlserviceinstancing/vb/source.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="f0de7-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f0de7-111">Example</span></span>  

 <span data-ttu-id="f0de7-112">El siguiente ejemplo de código establece la propiedad <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> del atributo <xref:System.ServiceModel.ServiceBehaviorAttribute> en <xref:System.ServiceModel.InstanceContextMode.PerCall>.</span><span class="sxs-lookup"><span data-stu-id="f0de7-112">The following code example sets the <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> property of the <xref:System.ServiceModel.ServiceBehaviorAttribute> attribute to <xref:System.ServiceModel.InstanceContextMode.PerCall>.</span></span>  
  
 [!code-csharp[c_ControlServiceInstancing#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_controlserviceinstancing/cs/source.cs#2)]
 [!code-vb[c_ControlServiceInstancing#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_controlserviceinstancing/vb/source.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="f0de7-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="f0de7-113">See also</span></span>

- <xref:System.ServiceModel.ServiceBehaviorAttribute>
- <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A>
- <xref:System.ServiceModel.InstanceContextMode>
- [<span data-ttu-id="f0de7-114">Servicio: ejemplos de comportamientos</span><span class="sxs-lookup"><span data-stu-id="f0de7-114">Service: Behaviors Samples</span></span>](../samples/behaviors.md)
