---
description: 'Más información acerca de cómo: crear un servicio con una interfaz de contrato'
title: Procedimiento para crear un servicio con una interfaz de contrato
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7b6803f6-d6f9-4cc2-9f1b-6f4c920475d5
ms.openlocfilehash: 5080f6bb45030811b87f952fb62a74801bc1ef88
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99793836"
---
# <a name="how-to-create-a-service-with-a-contract-interface"></a><span data-ttu-id="385aa-103">Procedimiento para crear un servicio con una interfaz de contrato</span><span class="sxs-lookup"><span data-stu-id="385aa-103">How to: Create a Service with a Contract Interface</span></span>

<span data-ttu-id="385aa-104">La manera preferida de crear un contrato de Windows Communication Foundation (WCF) es mediante una interfaz.</span><span class="sxs-lookup"><span data-stu-id="385aa-104">The preferred way to create a Windows Communication Foundation (WCF) contract is by using an interface.</span></span> <span data-ttu-id="385aa-105">Este contrato especifica la colección y estructura de mensajes requeridas para obtener acceso a las operaciones que el servicio proporciona.</span><span class="sxs-lookup"><span data-stu-id="385aa-105">This contract specifies the collection and structure of messages required to access the operations the service offers.</span></span> <span data-ttu-id="385aa-106">Esta interfaz define los tipos de entrada y salida aplicando la clase <xref:System.ServiceModel.ServiceContractAttribute> a la interfaz y la clase <xref:System.ServiceModel.OperationContractAttribute> a los métodos que desee exponer.</span><span class="sxs-lookup"><span data-stu-id="385aa-106">This interface defines the input and output types by applying the <xref:System.ServiceModel.ServiceContractAttribute> class to the interface and the <xref:System.ServiceModel.OperationContractAttribute> class to the methods that you want to expose.</span></span>  
  
 <span data-ttu-id="385aa-107">Para obtener más información acerca de los contratos de servicio, consulte [diseño de contratos de servicio](../designing-service-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="385aa-107">For more information about service contracts, see [Designing Service Contracts](../designing-service-contracts.md).</span></span>  
  
### <a name="creating-a-wcf-contract-with-an-interface"></a><span data-ttu-id="385aa-108">Creación de un contrato WCF con una interfaz</span><span class="sxs-lookup"><span data-stu-id="385aa-108">Creating a WCF contract with an interface</span></span>  
  
1. <span data-ttu-id="385aa-109">Cree una nueva interfaz con Visual Basic, C# o cualquier otro lenguaje de Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="385aa-109">Create a new interface using Visual Basic, C#, or any other common language runtime language.</span></span>  
  
2. <span data-ttu-id="385aa-110">Aplique la clase <xref:System.ServiceModel.ServiceContractAttribute> a la interfaz.</span><span class="sxs-lookup"><span data-stu-id="385aa-110">Apply the <xref:System.ServiceModel.ServiceContractAttribute> class to the interface.</span></span>  
  
3. <span data-ttu-id="385aa-111">Defina los métodos en la interfaz.</span><span class="sxs-lookup"><span data-stu-id="385aa-111">Define the methods in the interface.</span></span>  
  
4. <span data-ttu-id="385aa-112">Aplique la <xref:System.ServiceModel.OperationContractAttribute> clase a cada método que debe exponerse como parte del contrato de WCF público.</span><span class="sxs-lookup"><span data-stu-id="385aa-112">Apply the <xref:System.ServiceModel.OperationContractAttribute> class to each method that must be exposed as part of the public WCF contract.</span></span>  
  
## <a name="example"></a><span data-ttu-id="385aa-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="385aa-113">Example</span></span>  

 <span data-ttu-id="385aa-114">El siguiente ejemplo de código muestra una interfaz que define un contrato de servicio.</span><span class="sxs-lookup"><span data-stu-id="385aa-114">The following code example shows an interface that defines a service contract.</span></span>  
  
 [!code-csharp[c_HowTo_CreateContractWithInterface#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createcontractwithinterface/cs/source.cs#1)]
 [!code-vb[c_HowTo_CreateContractWithInterface#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_createcontractwithinterface/vb/source.vb#1)]  
  
 <span data-ttu-id="385aa-115">Los métodos que tienen aplicada la clase <xref:System.ServiceModel.OperationContractAttribute> usan de forma predeterminada un patrón de mensaje solicitud-respuesta.</span><span class="sxs-lookup"><span data-stu-id="385aa-115">The methods that have the <xref:System.ServiceModel.OperationContractAttribute> class applied use a request-reply message pattern by default.</span></span> <span data-ttu-id="385aa-116">Para obtener más información sobre este patrón de mensaje, consulte [Cómo: crear un contrato de Request-Reply](how-to-create-a-request-reply-contract.md).</span><span class="sxs-lookup"><span data-stu-id="385aa-116">For more information about this message pattern, see [How to: Create a Request-Reply Contract](how-to-create-a-request-reply-contract.md).</span></span> <span data-ttu-id="385aa-117">Puede crear y utilizar también otros patrones de mensaje estableciendo las propiedades del atributo.</span><span class="sxs-lookup"><span data-stu-id="385aa-117">You can also create and use other message patterns by setting properties of the attribute.</span></span> <span data-ttu-id="385aa-118">Para obtener más ejemplos, consulte [Cómo: crear un contrato de One-Way](how-to-create-a-one-way-contract.md) y [Cómo: crear un contrato dúplex](how-to-create-a-duplex-contract.md).</span><span class="sxs-lookup"><span data-stu-id="385aa-118">For more examples, see [How to: Create a One-Way Contract](how-to-create-a-one-way-contract.md) and [How to: Create a Duplex Contract](how-to-create-a-duplex-contract.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="385aa-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="385aa-119">See also</span></span>

- <xref:System.ServiceModel.ServiceContractAttribute>
- <xref:System.ServiceModel.OperationContractAttribute>
