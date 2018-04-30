---
title: Procedimiento para crear un servicio con una interfaz de contrato
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
ms.assetid: 7b6803f6-d6f9-4cc2-9f1b-6f4c920475d5
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b4af593edd355ed89da8c5b2c79a4c029b966fe4
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/30/2018
---
# <a name="how-to-create-a-service-with-a-contract-interface"></a><span data-ttu-id="f155a-102">Procedimiento para crear un servicio con una interfaz de contrato</span><span class="sxs-lookup"><span data-stu-id="f155a-102">How to: Create a Service with a Contract Interface</span></span>
<span data-ttu-id="f155a-103">La manera preferida de crear un contrato de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] es utilizar una interfaz.</span><span class="sxs-lookup"><span data-stu-id="f155a-103">The preferred way to create a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] contract is by using an interface.</span></span> <span data-ttu-id="f155a-104">Este contrato especifica la colección y estructura de mensajes requeridas para obtener acceso a las operaciones que el servicio proporciona.</span><span class="sxs-lookup"><span data-stu-id="f155a-104">This contract specifies the collection and structure of messages required to access the operations the service offers.</span></span> <span data-ttu-id="f155a-105">Esta interfaz define los tipos de entrada y salida aplicando la clase <xref:System.ServiceModel.ServiceContractAttribute> a la interfaz y la clase <xref:System.ServiceModel.OperationContractAttribute> a los métodos que desee exponer.</span><span class="sxs-lookup"><span data-stu-id="f155a-105">This interface defines the input and output types by applying the <xref:System.ServiceModel.ServiceContractAttribute> class to the interface and the <xref:System.ServiceModel.OperationContractAttribute> class to the methods that you want to expose.</span></span>  
  
 <span data-ttu-id="f155a-106">Para obtener más información acerca de los contratos de servicio, consulte [diseñar contratos de servicio](../../../../docs/framework/wcf/designing-service-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="f155a-106">For more information about service contracts, see [Designing Service Contracts](../../../../docs/framework/wcf/designing-service-contracts.md).</span></span>  
  
### <a name="creating-a-wcf-contract-with-an-interface"></a><span data-ttu-id="f155a-107">Creación de un contrato WCF con una interfaz</span><span class="sxs-lookup"><span data-stu-id="f155a-107">Creating a WCF contract with an interface</span></span>  
  
1.  <span data-ttu-id="f155a-108">Crear una nueva interfaz mediante Visual Basic, C# o cualquier otro lenguaje de common language runtime.</span><span class="sxs-lookup"><span data-stu-id="f155a-108">Create a new interface using Visual Basic, C#, or any other common language runtime language.</span></span>  
  
2.  <span data-ttu-id="f155a-109">Aplique la clase <xref:System.ServiceModel.ServiceContractAttribute> a la interfaz.</span><span class="sxs-lookup"><span data-stu-id="f155a-109">Apply the <xref:System.ServiceModel.ServiceContractAttribute> class to the interface.</span></span>  
  
3.  <span data-ttu-id="f155a-110">Defina los métodos en la interfaz.</span><span class="sxs-lookup"><span data-stu-id="f155a-110">Define the methods in the interface.</span></span>  
  
4.  <span data-ttu-id="f155a-111">Aplique la clase <xref:System.ServiceModel.OperationContractAttribute> a cada método que debe exponerse como parte del contrato público de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f155a-111">Apply the <xref:System.ServiceModel.OperationContractAttribute> class to each method that must be exposed as part of the public [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] contract.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f155a-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f155a-112">Example</span></span>  
 <span data-ttu-id="f155a-113">El siguiente ejemplo de código muestra una interfaz que define un contrato de servicio.</span><span class="sxs-lookup"><span data-stu-id="f155a-113">The following code example shows an interface that defines a service contract.</span></span>  
  
 [!code-csharp[c_HowTo_CreateContractWithInterface#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createcontractwithinterface/cs/source.cs#1)]
 [!code-vb[c_HowTo_CreateContractWithInterface#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_createcontractwithinterface/vb/source.vb#1)]  
  
 <span data-ttu-id="f155a-114">Los métodos que tienen aplicada la clase <xref:System.ServiceModel.OperationContractAttribute> usan de forma predeterminada un patrón de mensaje solicitud-respuesta.</span><span class="sxs-lookup"><span data-stu-id="f155a-114">The methods that have the <xref:System.ServiceModel.OperationContractAttribute> class applied use a request-reply message pattern by default.</span></span> <span data-ttu-id="f155a-115">Para obtener más información sobre este patrón de mensaje, consulte [Cómo: crear un contrato de solicitud-respuesta](../../../../docs/framework/wcf/feature-details/how-to-create-a-request-reply-contract.md).</span><span class="sxs-lookup"><span data-stu-id="f155a-115">For more information about this message pattern, see [How to: Create a Request-Reply Contract](../../../../docs/framework/wcf/feature-details/how-to-create-a-request-reply-contract.md).</span></span> <span data-ttu-id="f155a-116">Puede crear y utilizar también otros patrones de mensaje estableciendo las propiedades del atributo.</span><span class="sxs-lookup"><span data-stu-id="f155a-116">You can also create and use other message patterns by setting properties of the attribute.</span></span> <span data-ttu-id="f155a-117">Para obtener más ejemplos, vea [Cómo: crear un contrato unidireccional](../../../../docs/framework/wcf/feature-details/how-to-create-a-one-way-contract.md) y [Cómo: crear un contrato dúplex](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).</span><span class="sxs-lookup"><span data-stu-id="f155a-117">For more examples, see [How to: Create a One-Way Contract](../../../../docs/framework/wcf/feature-details/how-to-create-a-one-way-contract.md) and [How to: Create a Duplex Contract](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f155a-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="f155a-118">See Also</span></span>  
 <xref:System.ServiceModel.ServiceContractAttribute>  
 <xref:System.ServiceModel.OperationContractAttribute>
