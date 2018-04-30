---
title: Creación de un contrato de solicitud-respuesta
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 801d90da-3d45-4284-9c9f-56c8aadb4060
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2a272eaa88a53814daea9d515550a37f7991ecb8
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/30/2018
---
# <a name="how-to-create-a-request-reply-contract"></a><span data-ttu-id="30ab8-102">Creación de un contrato de solicitud-respuesta</span><span class="sxs-lookup"><span data-stu-id="30ab8-102">How to: Create a Request-Reply Contract</span></span>
<span data-ttu-id="30ab8-103">Un contrato de solicitud-respuesta especifica un método que devuelve una respuesta.</span><span class="sxs-lookup"><span data-stu-id="30ab8-103">A request-reply contract specifies a method that returns a reply.</span></span> <span data-ttu-id="30ab8-104">La respuesta se debe enviar y correlacionar con la solicitud según las condiciones de este contrato.</span><span class="sxs-lookup"><span data-stu-id="30ab8-104">The reply must be sent and correlated to the request under the terms of this contract.</span></span> <span data-ttu-id="30ab8-105">Incluso si el método no devuelve ninguna respuesta (`void` en C#, o `Sub` en Visual Basic), la infraestructura crea y envía un mensaje vacío al autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="30ab8-105">Even if the method returns no reply (`void` in C#, or a `Sub` in Visual Basic), the infrastructure creates and sends an empty message to the caller.</span></span> <span data-ttu-id="30ab8-106">Para evitar que se envíe un mensaje de respuesta vacío, use un contrato unidireccional para la operación.</span><span class="sxs-lookup"><span data-stu-id="30ab8-106">To prevent the sending of an empty reply message, use a one-way contract for the operation.</span></span>  
  
### <a name="to-create-a-request-reply-contract"></a><span data-ttu-id="30ab8-107">Creación de un contrato de solicitud-respuesta</span><span class="sxs-lookup"><span data-stu-id="30ab8-107">To create a request-reply contract</span></span>  
  
1.  <span data-ttu-id="30ab8-108">Cree una interfaz en el lenguaje de programación elegido.</span><span class="sxs-lookup"><span data-stu-id="30ab8-108">Create an interface in the programming language of your choice.</span></span>  
  
2.  <span data-ttu-id="30ab8-109">Aplique el atributo <xref:System.ServiceModel.ServiceContractAttribute> a dicha interfaz.</span><span class="sxs-lookup"><span data-stu-id="30ab8-109">Apply the <xref:System.ServiceModel.ServiceContractAttribute> attribute to the interface.</span></span>  
  
3.  <span data-ttu-id="30ab8-110">Aplique el atributo <xref:System.ServiceModel.OperationContractAttribute> a cada uno de los métodos que pueden invocar los clientes.</span><span class="sxs-lookup"><span data-stu-id="30ab8-110">Apply the <xref:System.ServiceModel.OperationContractAttribute> attribute to each method that clients can invoke.</span></span>  
  
4.  <span data-ttu-id="30ab8-111">Opcional.</span><span class="sxs-lookup"><span data-stu-id="30ab8-111">Optional.</span></span> <span data-ttu-id="30ab8-112">Establezca el valor de la propiedad <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> en `true` para evitar que se envíe un mensaje de respuesta vacío.</span><span class="sxs-lookup"><span data-stu-id="30ab8-112">Set the value of the <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> property to `true` to prevent the sending of an empty reply message.</span></span> <span data-ttu-id="30ab8-113">De forma predeterminada, todas las operaciones son contratos de solicitud-respuesta.</span><span class="sxs-lookup"><span data-stu-id="30ab8-113">By default, all operations are request-reply contracts.</span></span>  
  
## <a name="example"></a><span data-ttu-id="30ab8-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="30ab8-114">Example</span></span>  
 <span data-ttu-id="30ab8-115">El siguiente ejemplo define un contrato para un servicio de calculadora que proporciona métodos `Add` y `Subtract`.</span><span class="sxs-lookup"><span data-stu-id="30ab8-115">The following sample defines a contract for a calculator service that provides `Add` and `Subtract` methods.</span></span> <span data-ttu-id="30ab8-116">El método `Multiply` no es parte del contrato, porque no está marcado por la clase <xref:System.ServiceModel.OperationContractAttribute> y, por tanto, los clientes no pueden acceder a él.</span><span class="sxs-lookup"><span data-stu-id="30ab8-116">The `Multiply` method is not part of the contract because it is not marked by the <xref:System.ServiceModel.OperationContractAttribute> class and so it is not accessible to clients.</span></span>  
  
```
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
  
-   <span data-ttu-id="30ab8-117">Para obtener más información sobre cómo especificar contratos de operación, consulte el <xref:System.ServiceModel.OperationContractAttribute> clase y el <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="30ab8-117">For more information about how to specify operation contracts, see the <xref:System.ServiceModel.OperationContractAttribute> class and the <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> property.</span></span>  
  
-   <span data-ttu-id="30ab8-118">La aplicación de los atributos <xref:System.ServiceModel.ServiceContractAttribute> y <xref:System.ServiceModel.OperationContractAttribute> permite la generación automática de definiciones de contrato de servicio en un Lenguaje de descripción de servicios Web (WSDL).</span><span class="sxs-lookup"><span data-stu-id="30ab8-118">Applying the <xref:System.ServiceModel.ServiceContractAttribute> and <xref:System.ServiceModel.OperationContractAttribute> attributes causes the automatic generation of service contract definitions in a Web Services Description Language (WSDL) document once the service is deployed.</span></span> <span data-ttu-id="30ab8-119">El documento se descarga agregando `?wsdl` a la dirección base HTTP del servicio.</span><span class="sxs-lookup"><span data-stu-id="30ab8-119">The document is downloaded by appending `?wsdl` to the HTTP base address for the service.</span></span> <span data-ttu-id="30ab8-120">Por ejemplo, `http://microsoft/CalculatorService?wsdl`.</span><span class="sxs-lookup"><span data-stu-id="30ab8-120">For example, `http://microsoft/CalculatorService?wsdl`</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30ab8-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="30ab8-121">See Also</span></span>  
 <xref:System.ServiceModel.OperationContractAttribute>  
 [<span data-ttu-id="30ab8-122">Diseño de contratos de servicio</span><span class="sxs-lookup"><span data-stu-id="30ab8-122">Designing Service Contracts</span></span>](../../../../docs/framework/wcf/designing-service-contracts.md)  
 [<span data-ttu-id="30ab8-123">Creación de un contrato dúplex</span><span class="sxs-lookup"><span data-stu-id="30ab8-123">How to: Create a Duplex Contract</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md)
