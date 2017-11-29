---
title: "Cómo: inspeccionar o modificar parámetros"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: ab6c0ac7-aac4-45ba-93d6-a0e9afd1756f
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 71e96dc3cf448b2e67b8a039f28a12df8360c76a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-inspect-or-modify-parameters"></a><span data-ttu-id="34ca6-102">Cómo: inspeccionar o modificar parámetros</span><span class="sxs-lookup"><span data-stu-id="34ca6-102">How to: Inspect or Modify Parameters</span></span>
<span data-ttu-id="34ca6-103">Puede inspeccionar o modificar los mensajes entrantes o salientes de una sola operación en un objeto de cliente [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] o un servicio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] implementando la interfaz <xref:System.ServiceModel.Dispatcher.IParameterInspector?displayProperty=nameWithType> e insertándola en el cliente o servicio en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="34ca6-103">You can inspect or modify the incoming or outgoing messages for a single operation on a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] client object or a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service by implementing the <xref:System.ServiceModel.Dispatcher.IParameterInspector?displayProperty=nameWithType> interface and inserting it into the client or service runtime.</span></span> <span data-ttu-id="34ca6-104">Normalmente se utiliza un comportamiento de operación para agregar inspectores de parámetro en una sola operación; se pueden utilizar otros comportamientos para proporcionar acceso fácil al tiempo de ejecución en un ámbito mayor.</span><span class="sxs-lookup"><span data-stu-id="34ca6-104">Typically an operation behavior is used to add parameter inspectors for a single operation; other behaviors can be used to provide easy access to the runtime at a greater scope.</span></span> <span data-ttu-id="34ca6-105">Para obtener más información, consulte [clientes extender](../../../../docs/framework/wcf/extending/extending-clients.md) y [extender distribuidores](../../../../docs/framework/wcf/extending/extending-dispatchers.md).</span><span class="sxs-lookup"><span data-stu-id="34ca6-105">For more information, see [Extending Clients](../../../../docs/framework/wcf/extending/extending-clients.md) and [Extending Dispatchers](../../../../docs/framework/wcf/extending/extending-dispatchers.md).</span></span>  
  
### <a name="inspecting-or-modifying-parameters"></a><span data-ttu-id="34ca6-106">Inspeccionando o modificando parámetros</span><span class="sxs-lookup"><span data-stu-id="34ca6-106">Inspecting or Modifying Parameters</span></span>  
  
1.  <span data-ttu-id="34ca6-107">Implementar la interfaz <xref:System.ServiceModel.Dispatcher.IParameterInspector?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="34ca6-107">Implement the <xref:System.ServiceModel.Dispatcher.IParameterInspector?displayProperty=nameWithType> interface.</span></span>  
  
2.  <span data-ttu-id="34ca6-108">Implemente <xref:System.ServiceModel.Description.IOperationBehavior?displayProperty=nameWithType>, <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType>, <xref:System.ServiceModel.Description.IServiceBehavior?displayProperty=nameWithType> o <xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType> (dependiendo del ámbito requerido) para agregar su inspector de parámetro a <xref:System.ServiceModel.Dispatcher.ClientOperation.ParameterInspectors%2A?displayProperty=nameWithType> o las propiedades <xref:System.ServiceModel.Dispatcher.DispatchOperation.ParameterInspectors%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="34ca6-108">Implement a <xref:System.ServiceModel.Description.IOperationBehavior?displayProperty=nameWithType>, <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType>, <xref:System.ServiceModel.Description.IServiceBehavior?displayProperty=nameWithType> or <xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType> (depending upon the required scope) to add your parameter inspector to either the <xref:System.ServiceModel.Dispatcher.ClientOperation.ParameterInspectors%2A?displayProperty=nameWithType> or <xref:System.ServiceModel.Dispatcher.DispatchOperation.ParameterInspectors%2A?displayProperty=nameWithType> properties.</span></span>  
  
3.  <span data-ttu-id="34ca6-109">Inserte su comportamiento antes de llamar <xref:System.ServiceModel.ClientBase%601.Open%2A?displayProperty=nameWithType> o el método <xref:System.ServiceModel.ICommunicationObject.Open%2A?displayProperty=nameWithType> en <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="34ca6-109">Insert your behavior prior to calling <xref:System.ServiceModel.ClientBase%601.Open%2A?displayProperty=nameWithType> or the <xref:System.ServiceModel.ICommunicationObject.Open%2A?displayProperty=nameWithType> method on the <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType>.</span></span> <span data-ttu-id="34ca6-110">Para obtener más información, consulte [configuración y al ampliar el tiempo de ejecución con comportamientos](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md).</span><span class="sxs-lookup"><span data-stu-id="34ca6-110">For details, see [Configuring and Extending the Runtime with Behaviors](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="34ca6-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="34ca6-111">Example</span></span>  
 <span data-ttu-id="34ca6-112">Los siguientes ejemplos de código muestran, en orden:</span><span class="sxs-lookup"><span data-stu-id="34ca6-112">The following code examples show, in order:</span></span>  
  
-   <span data-ttu-id="34ca6-113">Una implementación de inspector de parámetro.</span><span class="sxs-lookup"><span data-stu-id="34ca6-113">A parameter inspector implementation.</span></span>  
  
-   <span data-ttu-id="34ca6-114">La implementación de comportamiento que inserta el inspector de parámetro utilizando <xref:System.ServiceModel.Description.IOperationBehavior?displayProperty=nameWithType>, <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType> y <xref:System.ServiceModel.Description.IServiceBehavior?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="34ca6-114">The behavior implementation that inserts the parameter inspector using a <xref:System.ServiceModel.Description.IOperationBehavior?displayProperty=nameWithType>, <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType>, and an <xref:System.ServiceModel.Description.IServiceBehavior?displayProperty=nameWithType>.</span></span>  
  
-   <span data-ttu-id="34ca6-115">Un archivo de configuración que carga y ejecuta el comportamiento del punto de conexión en una aplicación cliente para insertar el inspector de parámetro en el cliente.</span><span class="sxs-lookup"><span data-stu-id="34ca6-115">A configuration file that loads and runs the endpoint behavior in a client application to insert the parameter inspector on the client.</span></span>  
  
 [!code-csharp[Interceptors#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/interceptors.cs#4)]
 [!code-vb[Interceptors#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/interceptors/vb/interceptors.vb#4)]  
  
 [!code-csharp[Interceptors#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/insertingbehaviors.cs#5)]
 [!code-vb[Interceptors#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/interceptors/vb/insertingbehaviors.vb#5)]  
  
 [!code-xml[Interceptors#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/client.exe.config#3)]  
  
## <a name="see-also"></a><span data-ttu-id="34ca6-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="34ca6-116">See Also</span></span>  
 [<span data-ttu-id="34ca6-117">Configurar y extender el tiempo de ejecución con comportamientos</span><span class="sxs-lookup"><span data-stu-id="34ca6-117">Configuring and Extending the Runtime with Behaviors</span></span>](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)
