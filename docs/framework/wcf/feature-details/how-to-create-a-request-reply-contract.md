---
description: 'Más información acerca de cómo: crear un contrato de Request-Reply'
title: Procedimiento para crear un contrato de solicitud-respuesta
ms.date: 03/30/2017
ms.assetid: 801d90da-3d45-4284-9c9f-56c8aadb4060
ms.openlocfilehash: f5e63538a405aa451ffd3be114485604c00fa407
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99734703"
---
# <a name="how-to-create-a-request-reply-contract"></a><span data-ttu-id="81aeb-103">Procedimiento para crear un contrato de solicitud-respuesta</span><span class="sxs-lookup"><span data-stu-id="81aeb-103">How to: Create a Request-Reply Contract</span></span>

<span data-ttu-id="81aeb-104">Un contrato de solicitud-respuesta especifica un método que devuelve una respuesta.</span><span class="sxs-lookup"><span data-stu-id="81aeb-104">A request-reply contract specifies a method that returns a reply.</span></span> <span data-ttu-id="81aeb-105">La respuesta se debe enviar y correlacionar con la solicitud según las condiciones de este contrato.</span><span class="sxs-lookup"><span data-stu-id="81aeb-105">The reply must be sent and correlated to the request under the terms of this contract.</span></span> <span data-ttu-id="81aeb-106">Incluso si el método no devuelve ninguna respuesta (`void` en C#, o `Sub` en Visual Basic), la infraestructura crea y envía un mensaje vacío al autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="81aeb-106">Even if the method returns no reply (`void` in C#, or a `Sub` in Visual Basic), the infrastructure creates and sends an empty message to the caller.</span></span> <span data-ttu-id="81aeb-107">Para evitar que se envíe un mensaje de respuesta vacío, use un contrato unidireccional para la operación.</span><span class="sxs-lookup"><span data-stu-id="81aeb-107">To prevent the sending of an empty reply message, use a one-way contract for the operation.</span></span>  
  
### <a name="to-create-a-request-reply-contract"></a><span data-ttu-id="81aeb-108">Creación de un contrato de solicitud-respuesta</span><span class="sxs-lookup"><span data-stu-id="81aeb-108">To create a request-reply contract</span></span>  
  
1. <span data-ttu-id="81aeb-109">Cree una interfaz en el lenguaje de programación elegido.</span><span class="sxs-lookup"><span data-stu-id="81aeb-109">Create an interface in the programming language of your choice.</span></span>  
  
2. <span data-ttu-id="81aeb-110">Aplique el atributo <xref:System.ServiceModel.ServiceContractAttribute> a dicha interfaz.</span><span class="sxs-lookup"><span data-stu-id="81aeb-110">Apply the <xref:System.ServiceModel.ServiceContractAttribute> attribute to the interface.</span></span>  
  
3. <span data-ttu-id="81aeb-111">Aplique el atributo <xref:System.ServiceModel.OperationContractAttribute> a cada uno de los métodos que pueden invocar los clientes.</span><span class="sxs-lookup"><span data-stu-id="81aeb-111">Apply the <xref:System.ServiceModel.OperationContractAttribute> attribute to each method that clients can invoke.</span></span>  
  
4. <span data-ttu-id="81aeb-112">Opcional.</span><span class="sxs-lookup"><span data-stu-id="81aeb-112">Optional.</span></span> <span data-ttu-id="81aeb-113">Establezca el valor de la propiedad <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> en `true` para evitar que se envíe un mensaje de respuesta vacío.</span><span class="sxs-lookup"><span data-stu-id="81aeb-113">Set the value of the <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> property to `true` to prevent the sending of an empty reply message.</span></span> <span data-ttu-id="81aeb-114">De forma predeterminada, todas las operaciones son contratos de solicitud-respuesta.</span><span class="sxs-lookup"><span data-stu-id="81aeb-114">By default, all operations are request-reply contracts.</span></span>  
  
## <a name="example"></a><span data-ttu-id="81aeb-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="81aeb-115">Example</span></span>  

 <span data-ttu-id="81aeb-116">El siguiente ejemplo define un contrato para un servicio de calculadora que proporciona métodos `Add` y `Subtract`.</span><span class="sxs-lookup"><span data-stu-id="81aeb-116">The following sample defines a contract for a calculator service that provides `Add` and `Subtract` methods.</span></span> <span data-ttu-id="81aeb-117">El método `Multiply` no es parte del contrato, porque no está marcado por la clase <xref:System.ServiceModel.OperationContractAttribute> y, por tanto, los clientes no pueden acceder a él.</span><span class="sxs-lookup"><span data-stu-id="81aeb-117">The `Multiply` method is not part of the contract because it is not marked by the <xref:System.ServiceModel.OperationContractAttribute> class and so it is not accessible to clients.</span></span>  
  
```csharp
using System.ServiceModel;

[ServiceContract]
public interface ICalculator
{
    [OperationContract]
    // It would be equivalent to write explicitly:
    // [OperationContract(IsOneWay=false)]
    int Add(int a, int b);

    [OperationContract]
    int Subtract(int a, int b);

    int Multiply(int a, int b)
}
```
  
- <span data-ttu-id="81aeb-118">Para obtener más información sobre cómo especificar contratos de operación, vea la <xref:System.ServiceModel.OperationContractAttribute> clase y la <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="81aeb-118">For more information about how to specify operation contracts, see the <xref:System.ServiceModel.OperationContractAttribute> class and the <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> property.</span></span>  
  
- <span data-ttu-id="81aeb-119">La aplicación de los atributos <xref:System.ServiceModel.ServiceContractAttribute> y <xref:System.ServiceModel.OperationContractAttribute> permite la generación automática de definiciones de contrato de servicio en un Lenguaje de descripción de servicios Web (WSDL).</span><span class="sxs-lookup"><span data-stu-id="81aeb-119">Applying the <xref:System.ServiceModel.ServiceContractAttribute> and <xref:System.ServiceModel.OperationContractAttribute> attributes causes the automatic generation of service contract definitions in a Web Services Description Language (WSDL) document once the service is deployed.</span></span> <span data-ttu-id="81aeb-120">El documento se descarga agregando `?wsdl` a la dirección base HTTP del servicio.</span><span class="sxs-lookup"><span data-stu-id="81aeb-120">The document is downloaded by appending `?wsdl` to the HTTP base address for the service.</span></span> <span data-ttu-id="81aeb-121">Por ejemplo: `http://microsoft/CalculatorService?wsdl`</span><span class="sxs-lookup"><span data-stu-id="81aeb-121">For example, `http://microsoft/CalculatorService?wsdl`</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81aeb-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="81aeb-122">See also</span></span>

- <xref:System.ServiceModel.OperationContractAttribute>
- [<span data-ttu-id="81aeb-123">Diseño de contratos de servicios</span><span class="sxs-lookup"><span data-stu-id="81aeb-123">Designing Service Contracts</span></span>](../designing-service-contracts.md)
- [<span data-ttu-id="81aeb-124">Procedimiento para crear un contrato dúplex</span><span class="sxs-lookup"><span data-stu-id="81aeb-124">How to: Create a Duplex Contract</span></span>](how-to-create-a-duplex-contract.md)
