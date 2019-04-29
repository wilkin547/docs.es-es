---
title: Procedimiento para declarar errores en contratos de servicios
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e8da98e7-d22f-4f60-ac82-3fb0928a353f
ms.openlocfilehash: 0e173f71201d5f98a04d2ad922469e4ff6666681
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61929290"
---
# <a name="how-to-declare-faults-in-service-contracts"></a><span data-ttu-id="61628-102">Procedimiento para declarar errores en contratos de servicios</span><span class="sxs-lookup"><span data-stu-id="61628-102">How to: Declare Faults in Service Contracts</span></span>
<span data-ttu-id="61628-103">En código administrado, las excepciones se inician al producirse condiciones de error.</span><span class="sxs-lookup"><span data-stu-id="61628-103">In managed code, exceptions are thrown when error conditions occur.</span></span> <span data-ttu-id="61628-104">Sin embargo, en las aplicaciones de Windows Communication Foundation (WCF), los contratos de servicio especifican qué información de error se devuelve a los clientes mediante la declaración de los errores de SOAP en el contrato de servicio.</span><span class="sxs-lookup"><span data-stu-id="61628-104">In Windows Communication Foundation (WCF) applications, however, service contracts specify what error information is returned to clients by declaring SOAP faults in the service contract.</span></span> <span data-ttu-id="61628-105">Para obtener información general de la relación entre las excepciones y errores, vea [especificar y controlar errores en contratos y servicios](../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md).</span><span class="sxs-lookup"><span data-stu-id="61628-105">For an overview of the relationship between exceptions and faults, see [Specifying and Handling Faults in Contracts and Services](../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md).</span></span>  
  
### <a name="create-a-service-contract-that-specifies-a-soap-fault"></a><span data-ttu-id="61628-106">Crear un contrato de servicio que especifica un error de SOAP</span><span class="sxs-lookup"><span data-stu-id="61628-106">Create a service contract that specifies a SOAP fault</span></span>  
  
1. <span data-ttu-id="61628-107">Crear un contrato de servicio que contiene al menos una operación.</span><span class="sxs-lookup"><span data-stu-id="61628-107">Create a service contract that contains at least one operation.</span></span> <span data-ttu-id="61628-108">Como ejemplo, vea [Cómo: Definir un contrato de servicio](../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md).</span><span class="sxs-lookup"><span data-stu-id="61628-108">For an example, see [How to: Define a Service Contract](../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md).</span></span>  
  
2. <span data-ttu-id="61628-109">Seleccione una operación capaz de especificar una condición de error sobre la que los clientes esperan ser informados.</span><span class="sxs-lookup"><span data-stu-id="61628-109">Select an operation that can specify an error condition about which clients can expect to be notified.</span></span> <span data-ttu-id="61628-110">Para decidir qué condiciones de error justifican la devolución de errores de SOAP a los clientes, vea [especificar y controlar errores en contratos y servicios](../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md).</span><span class="sxs-lookup"><span data-stu-id="61628-110">To decide which error conditions justify returning SOAP faults to clients, see [Specifying and Handling Faults in Contracts and Services](../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md).</span></span>  
  
3. <span data-ttu-id="61628-111">Aplique <xref:System.ServiceModel.FaultContractAttribute?displayProperty=nameWithType> a la operación seleccionada y pase un tipo de error serializable al constructor.</span><span class="sxs-lookup"><span data-stu-id="61628-111">Apply a <xref:System.ServiceModel.FaultContractAttribute?displayProperty=nameWithType> to the selected operation and pass a serializable fault type to the constructor.</span></span> <span data-ttu-id="61628-112">Para obtener más información sobre cómo crear y utilizar tipos serializables, consulte [Specifying Data Transfer in Service Contracts](../../../docs/framework/wcf/feature-details/specifying-data-transfer-in-service-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="61628-112">For details about creating and using serializable types, see [Specifying Data Transfer in Service Contracts](../../../docs/framework/wcf/feature-details/specifying-data-transfer-in-service-contracts.md).</span></span> <span data-ttu-id="61628-113">El ejemplo siguiente muestra cómo especificar que la operación `SampleMethod` puede producir un `GreetingFault`.</span><span class="sxs-lookup"><span data-stu-id="61628-113">The following example shows how to specify that the `SampleMethod` operation can result in a `GreetingFault`.</span></span>  
  
     [!code-csharp[FaultContractAttribute#4](../../../samples/snippets/csharp/VS_Snippets_CFX/faultcontractattribute/cs/services.cs#4)]
     [!code-vb[FaultContractAttribute#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/faultcontractattribute/vb/services.vb#4)]  
  
4. <span data-ttu-id="61628-114">Repita los pasos 2 y 3 en todas las operaciones del contrato que comunican las condiciones de error a los clientes.</span><span class="sxs-lookup"><span data-stu-id="61628-114">Repeat steps 2 and 3 for all operations in the contract that communicate error conditions to clients.</span></span>  
  
## <a name="implementing-an-operation-to-return-a-specified-soap-fault"></a><span data-ttu-id="61628-115">Implementar una operación para devolver un error de SOAP especificado</span><span class="sxs-lookup"><span data-stu-id="61628-115">Implementing an Operation to Return a Specified SOAP Fault</span></span>  
 <span data-ttu-id="61628-116">Cuando una operación especifica que un error de SOAP concreto puede devolverse (como en el procedimiento anterior) para comunicar una condición de error a la aplicación que realiza la llamada, el siguiente paso es implementar esa especificación.</span><span class="sxs-lookup"><span data-stu-id="61628-116">Once an operation has specified that a specific SOAP fault can be returned (such as in the preceding procedure) to communicate an error condition to a calling application, the next step is to implement that specification.</span></span>  
  
#### <a name="throw-the-specified-soap-fault-in-the-operation"></a><span data-ttu-id="61628-117">Iniciar el error de SOAP especificado en la operación</span><span class="sxs-lookup"><span data-stu-id="61628-117">Throw the specified SOAP fault in the operation</span></span>  
  
1. <span data-ttu-id="61628-118">Cuando se produce una condición de error especificada en un <xref:System.ServiceModel.FaultContractAttribute>, inicie una nueva <xref:System.ServiceModel.FaultException%601?displayProperty=nameWithType> en la que el error de SOAP especificado es el parámetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="61628-118">When a <xref:System.ServiceModel.FaultContractAttribute>-specified error condition occurs in an operation, throw a new <xref:System.ServiceModel.FaultException%601?displayProperty=nameWithType> where the specified SOAP fault is the type parameter.</span></span> <span data-ttu-id="61628-119">El siguiente ejemplo muestra cómo iniciar el `GreetingFault` en `SampleMethod` mostrado en el procedimiento anterior y en la sección de código siguiente.</span><span class="sxs-lookup"><span data-stu-id="61628-119">The following example shows how to throw the `GreetingFault` in the `SampleMethod` shown in the preceding procedure and in the following Code section.</span></span>  
  
     [!code-csharp[FaultContractAttribute#5](../../../samples/snippets/csharp/VS_Snippets_CFX/faultcontractattribute/cs/services.cs#5)]
     [!code-vb[FaultContractAttribute#5](../../../samples/snippets/visualbasic/VS_Snippets_CFX/faultcontractattribute/vb/services.vb#5)]  
  
## <a name="example"></a><span data-ttu-id="61628-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="61628-120">Example</span></span>  
 <span data-ttu-id="61628-121">El ejemplo de código siguiente muestra la implementación de una operación única que especifica `GreetingFault` para la operación `SampleMethod`.</span><span class="sxs-lookup"><span data-stu-id="61628-121">The following code example shows an implementation of a single operation that specifies a `GreetingFault` for the `SampleMethod` operation.</span></span>  
  
 [!code-csharp[FaultContractAttribute#1](../../../samples/snippets/csharp/VS_Snippets_CFX/faultcontractattribute/cs/services.cs#1)]
 [!code-vb[FaultContractAttribute#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/faultcontractattribute/vb/services.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="61628-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="61628-122">See also</span></span>

- <xref:System.ServiceModel.FaultContractAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.FaultException%601?displayProperty=nameWithType>
