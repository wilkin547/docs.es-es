---
title: Implementación de contratos de servicio
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- implementing service contracts [WCF]
ms.assetid: aefb6f56-47e3-4f24-ab0a-9bc07bf9885f
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5e477b11893d2b74ebe1674225e05b13cb9f67ca
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/30/2018
---
# <a name="implementing-service-contracts"></a><span data-ttu-id="736e4-102">Implementación de contratos de servicio</span><span class="sxs-lookup"><span data-stu-id="736e4-102">Implementing Service Contracts</span></span>
<span data-ttu-id="736e4-103">Un servicio es una clase que expone la funcionalidad disponible a los clientes en uno o más puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="736e4-103">A service is a class that exposes functionality available to clients at one or more endpoints.</span></span> <span data-ttu-id="736e4-104">Para crear un servicio, escriba una clase que implemente un contrato [!INCLUDE[indigo1](../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="736e4-104">To create a service, write a class that implements a [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] contract.</span></span> <span data-ttu-id="736e4-105">Hay dos maneras de hacerlo.</span><span class="sxs-lookup"><span data-stu-id="736e4-105">You can do this in one of two ways.</span></span> <span data-ttu-id="736e4-106">Puede definir el contrato separadamente como una interfaz y, a continuación, crear una clase que implemente esa interfaz.</span><span class="sxs-lookup"><span data-stu-id="736e4-106">You can define the contract separately as an interface and then create a class that implements that interface.</span></span> <span data-ttu-id="736e4-107">También puede crear la clase y el contrato directamente colocando el atributo <xref:System.ServiceModel.ServiceContractAttribute> en la misma clase y el atributo <xref:System.ServiceModel.OperationContractAttribute> en los métodos disponibles para los clientes del servicio.</span><span class="sxs-lookup"><span data-stu-id="736e4-107">Alternatively, you can create the class and contract directly by placing the <xref:System.ServiceModel.ServiceContractAttribute> attribute on the class itself and the <xref:System.ServiceModel.OperationContractAttribute> attribute on the methods available to the clients of the service.</span></span>  
  
## <a name="creating-a-service-class"></a><span data-ttu-id="736e4-108">Crear una clase de servicio</span><span class="sxs-lookup"><span data-stu-id="736e4-108">Creating a service class</span></span>  
 <span data-ttu-id="736e4-109">A continuación, se muestra un ejemplo de un servicio que implementa un contrato `IMath` que se ha definido separadamente.</span><span class="sxs-lookup"><span data-stu-id="736e4-109">The following is an example of a service that implements an `IMath` contract that has been defined separately.</span></span>  
  
```csharp  
// Define the IMath contract.  
[ServiceContract]  
public interface IMath  
{  
    [OperationContract]   
    double Add(double A, double B);  
  
    [OperationContract]  
    double Multiply (double A, double B);  
}  
  
// Implement the IMath contract in the MathService class.  
public class MathService : IMath  
{  
    public double Add (double A, double B) { return A + B; }  
    public double Multiply (double A, double B) { return A * B; }  
}  
```  
  
 <span data-ttu-id="736e4-110">De forma alternativa, un servicio puede exponer un contrato directamente.</span><span class="sxs-lookup"><span data-stu-id="736e4-110">Alternatively, a service can expose a contract directly.</span></span> <span data-ttu-id="736e4-111">A continuación, se muestra un ejemplo de una clase de servicio que define e implementa un contrato `MathService`.</span><span class="sxs-lookup"><span data-stu-id="736e4-111">The following is an example of a service class that defines and implements a `MathService` contract.</span></span>  
  
```csharp  
// Define the MathService contract directly on the service class.  
[ServiceContract]  
class MathService  
{  
    [OperationContract]  
    public double Add(double A, double B) { return A + B; }  
    [OperationContract]  
    private double Multiply (double A, double B) { return A * B; }  
}  
```  
  
 <span data-ttu-id="736e4-112">Tenga en cuenta que los servicios anteriores exponen contratos diferentes porque los nombres del contrato son diferentes.</span><span class="sxs-lookup"><span data-stu-id="736e4-112">Note that the preceding services expose different contracts because the contract names are different.</span></span> <span data-ttu-id="736e4-113">En el primer caso, el contrato expuesto se denomina "`IMath`" mientras que, en el segundo caso, el contrato se denomina" `MathService`".</span><span class="sxs-lookup"><span data-stu-id="736e4-113">In the first case, the exposed contract is named "`IMath`" while in the second case the contract is named "`MathService`".</span></span>  
  
 <span data-ttu-id="736e4-114">Puede establecer algunas cosas en el servicio y niveles de implementación de operación, como simultaneidad y creación de instancias.</span><span class="sxs-lookup"><span data-stu-id="736e4-114">You can set a few things at the service and operation implementation levels, such as concurrency and instancing.</span></span> <span data-ttu-id="736e4-115">Para obtener más información, consulte [diseñar e implementar servicios](../../../docs/framework/wcf/designing-and-implementing-services.md).</span><span class="sxs-lookup"><span data-stu-id="736e4-115">For more information, see [Designing and Implementing Services](../../../docs/framework/wcf/designing-and-implementing-services.md).</span></span>  
  
 <span data-ttu-id="736e4-116">Después de implementar un contrato de servicios, debe crear uno o más puntos de conexión para el servicio.</span><span class="sxs-lookup"><span data-stu-id="736e4-116">After implementing a service contract, you must create one or more endpoints for the service.</span></span> <span data-ttu-id="736e4-117">Para obtener más información, consulte [información general de creación de punto de conexión](../../../docs/framework/wcf/endpoint-creation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="736e4-117">For more information, see [Endpoint Creation Overview](../../../docs/framework/wcf/endpoint-creation-overview.md).</span></span> <span data-ttu-id="736e4-118">Para obtener más información acerca de cómo ejecutar un servicio, consulte [servicios de hospedaje](../../../docs/framework/wcf/hosting-services.md).</span><span class="sxs-lookup"><span data-stu-id="736e4-118">For more information about how to run a service, see [Hosting Services](../../../docs/framework/wcf/hosting-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="736e4-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="736e4-119">See Also</span></span>  
 [<span data-ttu-id="736e4-120">Diseño e implementación de servicios</span><span class="sxs-lookup"><span data-stu-id="736e4-120">Designing and Implementing Services</span></span>](../../../docs/framework/wcf/designing-and-implementing-services.md)  
 [<span data-ttu-id="736e4-121">Creación de un servicio con una clase de contrato</span><span class="sxs-lookup"><span data-stu-id="736e4-121">How to: Create a Service with a Contract Class</span></span>](../../../docs/framework/wcf/feature-details/how-to-create-a-wcf-contract-with-a-class.md)  
 [<span data-ttu-id="736e4-122">Creación de un servicio con una interfaz de contrato</span><span class="sxs-lookup"><span data-stu-id="736e4-122">How to: Create a Service with a Contract Interface</span></span>](../../../docs/framework/wcf/feature-details/how-to-create-a-service-with-a-contract-interface.md)  
 [<span data-ttu-id="736e4-123">Especificación del comportamiento en tiempo de ejecución del servicio</span><span class="sxs-lookup"><span data-stu-id="736e4-123">Specifying Service Run-Time Behavior</span></span>](../../../docs/framework/wcf/specifying-service-run-time-behavior.md)
