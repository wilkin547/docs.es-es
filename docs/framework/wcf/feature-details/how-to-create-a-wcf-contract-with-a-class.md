---
title: 'Cómo: Crear un contrato de Windows Communication Foundation con una clase'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 1ad69393-3915-4e7f-9b91-b6fc59c6f5ba
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 8e1a66dd00592e24fd505cb1956b04d2856bf96a
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2018
---
# <a name="how-to-create-a-windows-communication-foundation-contract-with-a-class"></a><span data-ttu-id="a3dea-102">Cómo: Crear un contrato de Windows Communication Foundation con una clase</span><span class="sxs-lookup"><span data-stu-id="a3dea-102">How to: Create a Windows Communication Foundation Contract with a Class</span></span>
<span data-ttu-id="a3dea-103">La manera preferida de crear un contrato [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] es utilizar una interfaz.</span><span class="sxs-lookup"><span data-stu-id="a3dea-103">The preferred way of creating a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] contract is by using an interface.</span></span> <span data-ttu-id="a3dea-104">Para obtener más información, consulte [Cómo: definir un contrato de servicio](../../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md).</span><span class="sxs-lookup"><span data-stu-id="a3dea-104">For more information, see [How to: Define a Service Contract](../../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md).</span></span> <span data-ttu-id="a3dea-105">Una alternativa, descrita aquí, es crear una clase y después aplicar directamente el atributo <xref:System.ServiceModel.ServiceContractAttribute> a la clase directamente y el atributo <xref:System.ServiceModel.OperationContractAttribute> a cada uno de los métodos de la clase que forman parte del contrato.</span><span class="sxs-lookup"><span data-stu-id="a3dea-105">An alternative, outlined here, is to create a class and then apply the <xref:System.ServiceModel.ServiceContractAttribute> attribute to the class directly and the <xref:System.ServiceModel.OperationContractAttribute> attribute to each of the methods in the class that are part of the contract.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="a3dea-106">`[ServiceContract]` y `[ServiceContractAttribute]` hacen lo mismo.</span><span class="sxs-lookup"><span data-stu-id="a3dea-106">`[ServiceContract]` and `[ServiceContractAttribute]` do the same thing.</span></span> <span data-ttu-id="a3dea-107">Lo mismo se aplica a `[OperationContract]` y `[OperationContractAttribute]`.</span><span class="sxs-lookup"><span data-stu-id="a3dea-107">The same thing it true for `[OperationContract]` and `[OperationContractAttribute]`.</span></span> <span data-ttu-id="a3dea-108">En cada caso el anterior es una forma abreviada del último.</span><span class="sxs-lookup"><span data-stu-id="a3dea-108">In each case the former is shorthand for the latter.</span></span>  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="a3dea-109"> contratos de servicio, consulte [diseñar contratos de servicio](../../../../docs/framework/wcf/designing-service-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="a3dea-109"> service contracts, see [Designing Service Contracts](../../../../docs/framework/wcf/designing-service-contracts.md).</span></span>  
  
### <a name="creating-a-windows-communication-foundation-contract-with-a-class"></a><span data-ttu-id="a3dea-110">Creación de un contrato de Windows Communication Foundation con una clase</span><span class="sxs-lookup"><span data-stu-id="a3dea-110">Creating a Windows Communication Foundation contract with a class</span></span>  
  
1.  <span data-ttu-id="a3dea-111">Cree una nueva clase mediante Visual Basic, C# o cualquier otro lenguaje de common language runtime.</span><span class="sxs-lookup"><span data-stu-id="a3dea-111">Create a new class using Visual Basic, C#, or any other common language runtime language.</span></span>  
  
2.  <span data-ttu-id="a3dea-112">Aplique la clase <xref:System.ServiceModel.ServiceContractAttribute> a la clase.</span><span class="sxs-lookup"><span data-stu-id="a3dea-112">Apply the <xref:System.ServiceModel.ServiceContractAttribute> class to the class.</span></span>  
  
3.  <span data-ttu-id="a3dea-113">Cree los métodos en la clase.</span><span class="sxs-lookup"><span data-stu-id="a3dea-113">Create methods in the class.</span></span>  
  
4.  <span data-ttu-id="a3dea-114">Aplique la clase <xref:System.ServiceModel.OperationContractAttribute> a cada método que debe exponerse como parte del contrato público de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a3dea-114">Apply the <xref:System.ServiceModel.OperationContractAttribute> class to each method that must be exposed as part of the public [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] contract.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a3dea-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a3dea-115">Example</span></span>  
 <span data-ttu-id="a3dea-116">El ejemplo de código siguiente muestra una clase que define un contrato de servicio.</span><span class="sxs-lookup"><span data-stu-id="a3dea-116">The following code example shows a class that defines a service contract.</span></span>  
  
 [!code-csharp[c_HowTo_CreateContractWithClass#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createcontractwithclass/cs/source.cs#1)]
 [!code-vb[c_HowTo_CreateContractWithClass#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_createcontractwithclass/vb/source.vb#1)]  
  
 <span data-ttu-id="a3dea-117">Los métodos que tienen aplicada la clase <xref:System.ServiceModel.OperationContractAttribute> usan de forma predeterminada un patrón de mensaje solicitud-respuesta.</span><span class="sxs-lookup"><span data-stu-id="a3dea-117">The methods that have the <xref:System.ServiceModel.OperationContractAttribute> class applied use a request-reply message pattern by default.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="a3dea-118"> Este patrón de mensajes, vea [Cómo: crear un contrato de solicitud-respuesta](../../../../docs/framework/wcf/feature-details/how-to-create-a-request-reply-contract.md).</span><span class="sxs-lookup"><span data-stu-id="a3dea-118"> this message pattern, see [How to: Create a Request-Reply Contract](../../../../docs/framework/wcf/feature-details/how-to-create-a-request-reply-contract.md).</span></span> <span data-ttu-id="a3dea-119">Puede crear y utilizar también otros patrones de mensaje estableciendo las propiedades del atributo.</span><span class="sxs-lookup"><span data-stu-id="a3dea-119">You can also create and use other message patterns by setting properties of the attribute.</span></span> <span data-ttu-id="a3dea-120">Para obtener más ejemplos, vea [Cómo: crear un contrato unidireccional](../../../../docs/framework/wcf/feature-details/how-to-create-a-one-way-contract.md) y [Cómo: crear un contrato dúplex](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).</span><span class="sxs-lookup"><span data-stu-id="a3dea-120">For more examples, see [How to: Create a One-Way Contract](../../../../docs/framework/wcf/feature-details/how-to-create-a-one-way-contract.md) and [How to: Create a Duplex Contract](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3dea-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="a3dea-121">See Also</span></span>  
 <xref:System.ServiceModel.ServiceContractAttribute>  
 <xref:System.ServiceModel.OperationContractAttribute>
