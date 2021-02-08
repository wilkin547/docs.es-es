---
description: 'Más información acerca de cómo: declarar errores en contratos de servicio'
title: Procedimiento para declarar errores en contratos de servicios
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e8da98e7-d22f-4f60-ac82-3fb0928a353f
ms.openlocfilehash: 1d83840386338747c983d8c4e9a788a452b9c4b0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99793264"
---
# <a name="how-to-declare-faults-in-service-contracts"></a><span data-ttu-id="6a405-103">Procedimiento para declarar errores en contratos de servicios</span><span class="sxs-lookup"><span data-stu-id="6a405-103">How to: Declare Faults in Service Contracts</span></span>

<span data-ttu-id="6a405-104">En código administrado, las excepciones se inician al producirse condiciones de error.</span><span class="sxs-lookup"><span data-stu-id="6a405-104">In managed code, exceptions are thrown when error conditions occur.</span></span> <span data-ttu-id="6a405-105">Sin embargo, en las aplicaciones de Windows Communication Foundation (WCF), los contratos de servicio especifican qué información de error se devuelve a los clientes mediante la declaración de errores de SOAP en el contrato de servicio.</span><span class="sxs-lookup"><span data-stu-id="6a405-105">In Windows Communication Foundation (WCF) applications, however, service contracts specify what error information is returned to clients by declaring SOAP faults in the service contract.</span></span> <span data-ttu-id="6a405-106">Para obtener información general sobre la relación entre las excepciones y los errores, vea [especificar y controlar errores en contratos y servicios](specifying-and-handling-faults-in-contracts-and-services.md).</span><span class="sxs-lookup"><span data-stu-id="6a405-106">For an overview of the relationship between exceptions and faults, see [Specifying and Handling Faults in Contracts and Services](specifying-and-handling-faults-in-contracts-and-services.md).</span></span>

## <a name="create-a-service-contract-that-specifies-a-soap-fault"></a><span data-ttu-id="6a405-107">Crear un contrato de servicio que especifica un error de SOAP</span><span class="sxs-lookup"><span data-stu-id="6a405-107">Create a service contract that specifies a SOAP fault</span></span>

1. <span data-ttu-id="6a405-108">Crear un contrato de servicio que contiene al menos una operación.</span><span class="sxs-lookup"><span data-stu-id="6a405-108">Create a service contract that contains at least one operation.</span></span> <span data-ttu-id="6a405-109">Para obtener un ejemplo, consulte [Cómo: definir un contrato de servicio](how-to-define-a-wcf-service-contract.md).</span><span class="sxs-lookup"><span data-stu-id="6a405-109">For an example, see [How to: Define a Service Contract](how-to-define-a-wcf-service-contract.md).</span></span>

2. <span data-ttu-id="6a405-110">Seleccione una operación capaz de especificar una condición de error sobre la que los clientes esperan ser informados.</span><span class="sxs-lookup"><span data-stu-id="6a405-110">Select an operation that can specify an error condition about which clients can expect to be notified.</span></span> <span data-ttu-id="6a405-111">Para decidir qué condiciones de error justifican la devolución de errores SOAP a los clientes, consulte [especificación y control de errores en contratos y servicios](specifying-and-handling-faults-in-contracts-and-services.md).</span><span class="sxs-lookup"><span data-stu-id="6a405-111">To decide which error conditions justify returning SOAP faults to clients, see [Specifying and Handling Faults in Contracts and Services](specifying-and-handling-faults-in-contracts-and-services.md).</span></span>

3. <span data-ttu-id="6a405-112">Aplique <xref:System.ServiceModel.FaultContractAttribute?displayProperty=nameWithType> a la operación seleccionada y pase un tipo de error serializable al constructor.</span><span class="sxs-lookup"><span data-stu-id="6a405-112">Apply a <xref:System.ServiceModel.FaultContractAttribute?displayProperty=nameWithType> to the selected operation and pass a serializable fault type to the constructor.</span></span> <span data-ttu-id="6a405-113">Para obtener más información sobre la creación y el uso de tipos serializables, vea [especificar transferencia de datos en contratos de servicio](./feature-details/specifying-data-transfer-in-service-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="6a405-113">For details about creating and using serializable types, see [Specifying Data Transfer in Service Contracts](./feature-details/specifying-data-transfer-in-service-contracts.md).</span></span> <span data-ttu-id="6a405-114">El ejemplo siguiente muestra cómo especificar que la operación `SampleMethod` puede producir un `GreetingFault`.</span><span class="sxs-lookup"><span data-stu-id="6a405-114">The following example shows how to specify that the `SampleMethod` operation can result in a `GreetingFault`.</span></span>

     [!code-csharp[FaultContractAttribute#4](~/samples/snippets/csharp/VS_Snippets_CFX/faultcontractattribute/cs/services.cs#4)]
     [!code-vb[FaultContractAttribute#4](~/samples/snippets/visualbasic/VS_Snippets_CFX/faultcontractattribute/vb/services.vb#4)]

4. <span data-ttu-id="6a405-115">Repita los pasos 2 y 3 en todas las operaciones del contrato que comunican las condiciones de error a los clientes.</span><span class="sxs-lookup"><span data-stu-id="6a405-115">Repeat steps 2 and 3 for all operations in the contract that communicate error conditions to clients.</span></span>

## <a name="implementing-an-operation-to-return-a-specified-soap-fault"></a><span data-ttu-id="6a405-116">Implementar una operación para devolver un error de SOAP especificado</span><span class="sxs-lookup"><span data-stu-id="6a405-116">Implementing an Operation to Return a Specified SOAP Fault</span></span>

 <span data-ttu-id="6a405-117">Cuando una operación especifica que un error de SOAP concreto puede devolverse (como en el procedimiento anterior) para comunicar una condición de error a la aplicación que realiza la llamada, el siguiente paso es implementar esa especificación.</span><span class="sxs-lookup"><span data-stu-id="6a405-117">Once an operation has specified that a specific SOAP fault can be returned (such as in the preceding procedure) to communicate an error condition to a calling application, the next step is to implement that specification.</span></span>

### <a name="throw-the-specified-soap-fault-in-the-operation"></a><span data-ttu-id="6a405-118">Iniciar el error de SOAP especificado en la operación</span><span class="sxs-lookup"><span data-stu-id="6a405-118">Throw the specified SOAP fault in the operation</span></span>

1. <span data-ttu-id="6a405-119">Cuando se produce una condición de error especificada en un <xref:System.ServiceModel.FaultContractAttribute>, inicie una nueva <xref:System.ServiceModel.FaultException%601?displayProperty=nameWithType> en la que el error de SOAP especificado es el parámetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="6a405-119">When a <xref:System.ServiceModel.FaultContractAttribute>-specified error condition occurs in an operation, throw a new <xref:System.ServiceModel.FaultException%601?displayProperty=nameWithType> where the specified SOAP fault is the type parameter.</span></span> <span data-ttu-id="6a405-120">El siguiente ejemplo muestra cómo iniciar el `GreetingFault` en `SampleMethod` mostrado en el procedimiento anterior y en la sección de código siguiente.</span><span class="sxs-lookup"><span data-stu-id="6a405-120">The following example shows how to throw the `GreetingFault` in the `SampleMethod` shown in the preceding procedure and in the following Code section.</span></span>

     [!code-csharp[FaultContractAttribute#5](~/samples/snippets/csharp/VS_Snippets_CFX/faultcontractattribute/cs/services.cs#5)]
     [!code-vb[FaultContractAttribute#5](~/samples/snippets/visualbasic/VS_Snippets_CFX/faultcontractattribute/vb/services.vb#5)]

## <a name="example"></a><span data-ttu-id="6a405-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6a405-121">Example</span></span>

<span data-ttu-id="6a405-122">El ejemplo de código siguiente muestra la implementación de una operación única que especifica `GreetingFault` para la operación `SampleMethod`.</span><span class="sxs-lookup"><span data-stu-id="6a405-122">The following code example shows an implementation of a single operation that specifies a `GreetingFault` for the `SampleMethod` operation.</span></span>

[!code-csharp[FaultContractAttribute#1](~/samples/snippets/csharp/VS_Snippets_CFX/faultcontractattribute/cs/services.cs#1)]
[!code-vb[FaultContractAttribute#1](~/samples/snippets/visualbasic/VS_Snippets_CFX/faultcontractattribute/vb/services.vb#1)]

## <a name="see-also"></a><span data-ttu-id="6a405-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="6a405-123">See also</span></span>

- <xref:System.ServiceModel.FaultContractAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.FaultException%601?displayProperty=nameWithType>
