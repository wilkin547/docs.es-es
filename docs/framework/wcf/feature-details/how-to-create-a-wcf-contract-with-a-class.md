---
title: Procedimiento Crear un contrato de Windows Communication Foundation con una clase
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1ad69393-3915-4e7f-9b91-b6fc59c6f5ba
ms.openlocfilehash: 37d0e6fae8ad0f3a91f1bead23fb5823fc52d420
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59313232"
---
# <a name="how-to-create-a-windows-communication-foundation-contract-with-a-class"></a><span data-ttu-id="e1d3a-102">Procedimiento Crear un contrato de Windows Communication Foundation con una clase</span><span class="sxs-lookup"><span data-stu-id="e1d3a-102">How to: Create a Windows Communication Foundation Contract with a Class</span></span>
<span data-ttu-id="e1d3a-103">Es la mejor manera de crear un contrato de Windows Communication Foundation (WCF) mediante el uso de una interfaz.</span><span class="sxs-lookup"><span data-stu-id="e1d3a-103">The preferred way of creating a Windows Communication Foundation (WCF) contract is by using an interface.</span></span> <span data-ttu-id="e1d3a-104">Para obtener más información, vea [Cómo: Definir un contrato de servicio](../../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md).</span><span class="sxs-lookup"><span data-stu-id="e1d3a-104">For more information, see [How to: Define a Service Contract](../../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md).</span></span> <span data-ttu-id="e1d3a-105">Una alternativa, descrita aquí, es crear una clase y después aplicar directamente el atributo <xref:System.ServiceModel.ServiceContractAttribute> a la clase directamente y el atributo <xref:System.ServiceModel.OperationContractAttribute> a cada uno de los métodos de la clase que forman parte del contrato.</span><span class="sxs-lookup"><span data-stu-id="e1d3a-105">An alternative, outlined here, is to create a class and then apply the <xref:System.ServiceModel.ServiceContractAttribute> attribute to the class directly and the <xref:System.ServiceModel.OperationContractAttribute> attribute to each of the methods in the class that are part of the contract.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="e1d3a-106">`[ServiceContract]` y `[ServiceContractAttribute]` hacen lo mismo.</span><span class="sxs-lookup"><span data-stu-id="e1d3a-106">`[ServiceContract]` and `[ServiceContractAttribute]` do the same thing.</span></span> <span data-ttu-id="e1d3a-107">Lo mismo es cierto para `[OperationContract]` y `[OperationContractAttribute]`.</span><span class="sxs-lookup"><span data-stu-id="e1d3a-107">The same thing is true for `[OperationContract]` and `[OperationContractAttribute]`.</span></span> <span data-ttu-id="e1d3a-108">En cada caso, el primero es una abreviatura para el último.</span><span class="sxs-lookup"><span data-stu-id="e1d3a-108">In each case, the former is shorthand for the latter.</span></span>  
  
 <span data-ttu-id="e1d3a-109">Para obtener más información sobre los contratos de servicio, consulte [Designing Service Contracts](../../../../docs/framework/wcf/designing-service-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="e1d3a-109">For more information about service contracts, see [Designing Service Contracts](../../../../docs/framework/wcf/designing-service-contracts.md).</span></span>  
  
### <a name="creating-a-windows-communication-foundation-contract-with-a-class"></a><span data-ttu-id="e1d3a-110">Creación de un contrato de Windows Communication Foundation con una clase</span><span class="sxs-lookup"><span data-stu-id="e1d3a-110">Creating a Windows Communication Foundation contract with a class</span></span>  
  
1. <span data-ttu-id="e1d3a-111">Cree una nueva clase utilizando Visual Basic, C#, o cualquier otro lenguaje de common language runtime.</span><span class="sxs-lookup"><span data-stu-id="e1d3a-111">Create a new class using Visual Basic, C#, or any other common language runtime language.</span></span>  
  
2. <span data-ttu-id="e1d3a-112">Aplique la clase <xref:System.ServiceModel.ServiceContractAttribute> a la clase.</span><span class="sxs-lookup"><span data-stu-id="e1d3a-112">Apply the <xref:System.ServiceModel.ServiceContractAttribute> class to the class.</span></span>  
  
3. <span data-ttu-id="e1d3a-113">Cree los métodos en la clase.</span><span class="sxs-lookup"><span data-stu-id="e1d3a-113">Create methods in the class.</span></span>  
  
4. <span data-ttu-id="e1d3a-114">Aplicar el <xref:System.ServiceModel.OperationContractAttribute> clase a cada método que se debe exponer como parte del contrato público de WCF.</span><span class="sxs-lookup"><span data-stu-id="e1d3a-114">Apply the <xref:System.ServiceModel.OperationContractAttribute> class to each method that must be exposed as part of the public WCF contract.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e1d3a-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e1d3a-115">Example</span></span>  
 <span data-ttu-id="e1d3a-116">El ejemplo de código siguiente muestra una clase que define un contrato de servicio.</span><span class="sxs-lookup"><span data-stu-id="e1d3a-116">The following code example shows a class that defines a service contract.</span></span>  
  
 [!code-csharp[c_HowTo_CreateContractWithClass#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createcontractwithclass/cs/source.cs#1)]
 [!code-vb[c_HowTo_CreateContractWithClass#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_createcontractwithclass/vb/source.vb#1)]  
  
 <span data-ttu-id="e1d3a-117">Los métodos que tienen aplicada la clase <xref:System.ServiceModel.OperationContractAttribute> usan de forma predeterminada un patrón de mensaje solicitud-respuesta.</span><span class="sxs-lookup"><span data-stu-id="e1d3a-117">The methods that have the <xref:System.ServiceModel.OperationContractAttribute> class applied use a request-reply message pattern by default.</span></span> <span data-ttu-id="e1d3a-118">Para obtener más información sobre este patrón de mensaje, vea [Cómo: Crear un contrato de solicitud-respuesta](../../../../docs/framework/wcf/feature-details/how-to-create-a-request-reply-contract.md).</span><span class="sxs-lookup"><span data-stu-id="e1d3a-118">For more information about this message pattern, see [How to: Create a Request-Reply Contract](../../../../docs/framework/wcf/feature-details/how-to-create-a-request-reply-contract.md).</span></span> <span data-ttu-id="e1d3a-119">Puede crear y utilizar también otros patrones de mensaje estableciendo las propiedades del atributo.</span><span class="sxs-lookup"><span data-stu-id="e1d3a-119">You can also create and use other message patterns by setting properties of the attribute.</span></span> <span data-ttu-id="e1d3a-120">Para obtener más ejemplos, vea [Cómo: Crear un contrato unidireccional](../../../../docs/framework/wcf/feature-details/how-to-create-a-one-way-contract.md) y [Cómo: Crear un contrato dúplex](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).</span><span class="sxs-lookup"><span data-stu-id="e1d3a-120">For more examples, see [How to: Create a One-Way Contract](../../../../docs/framework/wcf/feature-details/how-to-create-a-one-way-contract.md) and [How to: Create a Duplex Contract](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1d3a-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="e1d3a-121">See also</span></span>

- <xref:System.ServiceModel.ServiceContractAttribute>
- <xref:System.ServiceModel.OperationContractAttribute>
