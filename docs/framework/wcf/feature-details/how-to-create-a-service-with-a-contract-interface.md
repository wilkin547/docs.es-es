---
title: Filtrar para crear un servicio con una interfaz de contrato
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7b6803f6-d6f9-4cc2-9f1b-6f4c920475d5
ms.openlocfilehash: c31a954d659b3f686f8b9780276a4719064e60cc
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59128718"
---
# <a name="how-to-create-a-service-with-a-contract-interface"></a><span data-ttu-id="7eccd-102">Filtrar para crear un servicio con una interfaz de contrato</span><span class="sxs-lookup"><span data-stu-id="7eccd-102">How to: Create a Service with a Contract Interface</span></span>
<span data-ttu-id="7eccd-103">Es la mejor manera de crear un contrato de Windows Communication Foundation (WCF) mediante el uso de una interfaz.</span><span class="sxs-lookup"><span data-stu-id="7eccd-103">The preferred way to create a Windows Communication Foundation (WCF) contract is by using an interface.</span></span> <span data-ttu-id="7eccd-104">Este contrato especifica la colección y estructura de mensajes requeridas para obtener acceso a las operaciones que el servicio proporciona.</span><span class="sxs-lookup"><span data-stu-id="7eccd-104">This contract specifies the collection and structure of messages required to access the operations the service offers.</span></span> <span data-ttu-id="7eccd-105">Esta interfaz define los tipos de entrada y salida aplicando la clase <xref:System.ServiceModel.ServiceContractAttribute> a la interfaz y la clase <xref:System.ServiceModel.OperationContractAttribute> a los métodos que desee exponer.</span><span class="sxs-lookup"><span data-stu-id="7eccd-105">This interface defines the input and output types by applying the <xref:System.ServiceModel.ServiceContractAttribute> class to the interface and the <xref:System.ServiceModel.OperationContractAttribute> class to the methods that you want to expose.</span></span>  
  
 <span data-ttu-id="7eccd-106">Para obtener más información sobre los contratos de servicio, consulte [Designing Service Contracts](../../../../docs/framework/wcf/designing-service-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="7eccd-106">For more information about service contracts, see [Designing Service Contracts](../../../../docs/framework/wcf/designing-service-contracts.md).</span></span>  
  
### <a name="creating-a-wcf-contract-with-an-interface"></a><span data-ttu-id="7eccd-107">Creación de un contrato WCF con una interfaz</span><span class="sxs-lookup"><span data-stu-id="7eccd-107">Creating a WCF contract with an interface</span></span>  
  
1.  <span data-ttu-id="7eccd-108">Cree una nueva interfaz utilizando Visual Basic, C#, o cualquier otro lenguaje de common language runtime.</span><span class="sxs-lookup"><span data-stu-id="7eccd-108">Create a new interface using Visual Basic, C#, or any other common language runtime language.</span></span>  
  
2.  <span data-ttu-id="7eccd-109">Aplique la clase <xref:System.ServiceModel.ServiceContractAttribute> a la interfaz.</span><span class="sxs-lookup"><span data-stu-id="7eccd-109">Apply the <xref:System.ServiceModel.ServiceContractAttribute> class to the interface.</span></span>  
  
3.  <span data-ttu-id="7eccd-110">Defina los métodos en la interfaz.</span><span class="sxs-lookup"><span data-stu-id="7eccd-110">Define the methods in the interface.</span></span>  
  
4.  <span data-ttu-id="7eccd-111">Aplicar el <xref:System.ServiceModel.OperationContractAttribute> clase a cada método que se debe exponer como parte del contrato público de WCF.</span><span class="sxs-lookup"><span data-stu-id="7eccd-111">Apply the <xref:System.ServiceModel.OperationContractAttribute> class to each method that must be exposed as part of the public WCF contract.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7eccd-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7eccd-112">Example</span></span>  
 <span data-ttu-id="7eccd-113">El siguiente ejemplo de código muestra una interfaz que define un contrato de servicio.</span><span class="sxs-lookup"><span data-stu-id="7eccd-113">The following code example shows an interface that defines a service contract.</span></span>  
  
 [!code-csharp[c_HowTo_CreateContractWithInterface#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createcontractwithinterface/cs/source.cs#1)]
 [!code-vb[c_HowTo_CreateContractWithInterface#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_createcontractwithinterface/vb/source.vb#1)]  
  
 <span data-ttu-id="7eccd-114">Los métodos que tienen aplicada la clase <xref:System.ServiceModel.OperationContractAttribute> usan de forma predeterminada un patrón de mensaje solicitud-respuesta.</span><span class="sxs-lookup"><span data-stu-id="7eccd-114">The methods that have the <xref:System.ServiceModel.OperationContractAttribute> class applied use a request-reply message pattern by default.</span></span> <span data-ttu-id="7eccd-115">Para obtener más información sobre este patrón de mensaje, vea [Cómo: Crear un contrato de solicitud-respuesta](../../../../docs/framework/wcf/feature-details/how-to-create-a-request-reply-contract.md).</span><span class="sxs-lookup"><span data-stu-id="7eccd-115">For more information about this message pattern, see [How to: Create a Request-Reply Contract](../../../../docs/framework/wcf/feature-details/how-to-create-a-request-reply-contract.md).</span></span> <span data-ttu-id="7eccd-116">Puede crear y utilizar también otros patrones de mensaje estableciendo las propiedades del atributo.</span><span class="sxs-lookup"><span data-stu-id="7eccd-116">You can also create and use other message patterns by setting properties of the attribute.</span></span> <span data-ttu-id="7eccd-117">Para obtener más ejemplos, vea [Cómo: Crear un contrato unidireccional](../../../../docs/framework/wcf/feature-details/how-to-create-a-one-way-contract.md) y [Cómo: Crear un contrato dúplex](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).</span><span class="sxs-lookup"><span data-stu-id="7eccd-117">For more examples, see [How to: Create a One-Way Contract](../../../../docs/framework/wcf/feature-details/how-to-create-a-one-way-contract.md) and [How to: Create a Duplex Contract](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7eccd-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="7eccd-118">See also</span></span>

- <xref:System.ServiceModel.ServiceContractAttribute>
- <xref:System.ServiceModel.OperationContractAttribute>
