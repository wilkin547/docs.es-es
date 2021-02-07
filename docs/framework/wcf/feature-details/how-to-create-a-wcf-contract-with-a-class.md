---
description: 'Más información sobre: Cómo: crear un contrato de Windows Communication Foundation con una clase'
title: 'Cómo: Crear un contrato de Windows Communication Foundation con una clase'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1ad69393-3915-4e7f-9b91-b6fc59c6f5ba
ms.openlocfilehash: 63a5cc4e6a7966af69f2d5f3c7db0c7f4e313faf
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99756167"
---
# <a name="how-to-create-a-windows-communication-foundation-contract-with-a-class"></a><span data-ttu-id="0a4d2-103">Cómo: Crear un contrato de Windows Communication Foundation con una clase</span><span class="sxs-lookup"><span data-stu-id="0a4d2-103">How to: Create a Windows Communication Foundation Contract with a Class</span></span>

<span data-ttu-id="0a4d2-104">La manera preferida de crear un contrato de Windows Communication Foundation (WCF) es mediante una interfaz.</span><span class="sxs-lookup"><span data-stu-id="0a4d2-104">The preferred way of creating a Windows Communication Foundation (WCF) contract is by using an interface.</span></span> <span data-ttu-id="0a4d2-105">Para obtener más información, vea [Cómo: definir un contrato de servicio](../how-to-define-a-wcf-service-contract.md).</span><span class="sxs-lookup"><span data-stu-id="0a4d2-105">For more information, see [How to: Define a Service Contract](../how-to-define-a-wcf-service-contract.md).</span></span> <span data-ttu-id="0a4d2-106">Una alternativa, descrita aquí, es crear una clase y después aplicar directamente el atributo <xref:System.ServiceModel.ServiceContractAttribute> a la clase directamente y el atributo <xref:System.ServiceModel.OperationContractAttribute> a cada uno de los métodos de la clase que forman parte del contrato.</span><span class="sxs-lookup"><span data-stu-id="0a4d2-106">An alternative, outlined here, is to create a class and then apply the <xref:System.ServiceModel.ServiceContractAttribute> attribute to the class directly and the <xref:System.ServiceModel.OperationContractAttribute> attribute to each of the methods in the class that are part of the contract.</span></span>  
  
> [!WARNING]
> <span data-ttu-id="0a4d2-107">`[ServiceContract]` y `[ServiceContractAttribute]` hacen lo mismo.</span><span class="sxs-lookup"><span data-stu-id="0a4d2-107">`[ServiceContract]` and `[ServiceContractAttribute]` do the same thing.</span></span> <span data-ttu-id="0a4d2-108">Lo mismo se cumple para `[OperationContract]` y `[OperationContractAttribute]` .</span><span class="sxs-lookup"><span data-stu-id="0a4d2-108">The same thing is true for `[OperationContract]` and `[OperationContractAttribute]`.</span></span> <span data-ttu-id="0a4d2-109">En cada caso, la primera es la abreviatura de este último.</span><span class="sxs-lookup"><span data-stu-id="0a4d2-109">In each case, the former is shorthand for the latter.</span></span>  
  
 <span data-ttu-id="0a4d2-110">Para obtener más información acerca de los contratos de servicio, consulte [diseño de contratos de servicio](../designing-service-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="0a4d2-110">For more information about service contracts, see [Designing Service Contracts](../designing-service-contracts.md).</span></span>  
  
### <a name="creating-a-windows-communication-foundation-contract-with-a-class"></a><span data-ttu-id="0a4d2-111">Creación de un contrato de Windows Communication Foundation con una clase</span><span class="sxs-lookup"><span data-stu-id="0a4d2-111">Creating a Windows Communication Foundation contract with a class</span></span>  
  
1. <span data-ttu-id="0a4d2-112">Cree una nueva clase con Visual Basic, C# o cualquier otro lenguaje de Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="0a4d2-112">Create a new class using Visual Basic, C#, or any other common language runtime language.</span></span>  
  
2. <span data-ttu-id="0a4d2-113">Aplique la clase <xref:System.ServiceModel.ServiceContractAttribute> a la clase.</span><span class="sxs-lookup"><span data-stu-id="0a4d2-113">Apply the <xref:System.ServiceModel.ServiceContractAttribute> class to the class.</span></span>  
  
3. <span data-ttu-id="0a4d2-114">Cree los métodos en la clase.</span><span class="sxs-lookup"><span data-stu-id="0a4d2-114">Create methods in the class.</span></span>  
  
4. <span data-ttu-id="0a4d2-115">Aplique la <xref:System.ServiceModel.OperationContractAttribute> clase a cada método que debe exponerse como parte del contrato de WCF público.</span><span class="sxs-lookup"><span data-stu-id="0a4d2-115">Apply the <xref:System.ServiceModel.OperationContractAttribute> class to each method that must be exposed as part of the public WCF contract.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0a4d2-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0a4d2-116">Example</span></span>  

 <span data-ttu-id="0a4d2-117">El ejemplo de código siguiente muestra una clase que define un contrato de servicio.</span><span class="sxs-lookup"><span data-stu-id="0a4d2-117">The following code example shows a class that defines a service contract.</span></span>  
  
 [!code-csharp[c_HowTo_CreateContractWithClass#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createcontractwithclass/cs/source.cs#1)]
 [!code-vb[c_HowTo_CreateContractWithClass#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_createcontractwithclass/vb/source.vb#1)]  
  
 <span data-ttu-id="0a4d2-118">Los métodos que tienen aplicada la clase <xref:System.ServiceModel.OperationContractAttribute> usan de forma predeterminada un patrón de mensaje solicitud-respuesta.</span><span class="sxs-lookup"><span data-stu-id="0a4d2-118">The methods that have the <xref:System.ServiceModel.OperationContractAttribute> class applied use a request-reply message pattern by default.</span></span> <span data-ttu-id="0a4d2-119">Para obtener más información sobre este patrón de mensaje, consulte [Cómo: crear un contrato de Request-Reply](how-to-create-a-request-reply-contract.md).</span><span class="sxs-lookup"><span data-stu-id="0a4d2-119">For more information about this message pattern, see [How to: Create a Request-Reply Contract](how-to-create-a-request-reply-contract.md).</span></span> <span data-ttu-id="0a4d2-120">Puede crear y utilizar también otros patrones de mensaje estableciendo las propiedades del atributo.</span><span class="sxs-lookup"><span data-stu-id="0a4d2-120">You can also create and use other message patterns by setting properties of the attribute.</span></span> <span data-ttu-id="0a4d2-121">Para obtener más ejemplos, consulte [Cómo: crear un contrato de One-Way](how-to-create-a-one-way-contract.md) y [Cómo: crear un contrato dúplex](how-to-create-a-duplex-contract.md).</span><span class="sxs-lookup"><span data-stu-id="0a4d2-121">For more examples, see [How to: Create a One-Way Contract](how-to-create-a-one-way-contract.md) and [How to: Create a Duplex Contract](how-to-create-a-duplex-contract.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a4d2-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="0a4d2-122">See also</span></span>

- <xref:System.ServiceModel.ServiceContractAttribute>
- <xref:System.ServiceModel.OperationContractAttribute>
