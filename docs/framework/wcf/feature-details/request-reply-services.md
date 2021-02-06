---
description: 'Más información acerca de: Request-Reply Services'
title: Servicios de solicitud-respuesta
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Communication Foundation [WCF], request-reply services
- contracts [WCF], request-reply services
- WCF [WCF], request-reply services
- request-reply contracts [WCF]
ms.assetid: 2fa710f1-47f4-4598-b063-3ab3bd22ebba
ms.openlocfilehash: 804441d91577623b2a5fac9292f183628f9e542e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99632833"
---
# <a name="request-reply-services"></a><span data-ttu-id="71b2f-103">Servicios de solicitud-respuesta</span><span class="sxs-lookup"><span data-stu-id="71b2f-103">Request-Reply Services</span></span>

<span data-ttu-id="71b2f-104">Los servicios de solicitud-respuesta son el tipo predeterminado de contrato de operación en Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="71b2f-104">Request-reply services are the default type of operation contract in Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="71b2f-105">Los clientes realizan las llamadas a operaciones de servicio y esperan una respuesta del servicio.</span><span class="sxs-lookup"><span data-stu-id="71b2f-105">Clients make calls to service operations and wait for a response from the service.</span></span> <span data-ttu-id="71b2f-106">Puede realizar llamadas a una operación de servicio de manera sincrónica, donde el cliente se bloquea hasta que recibe una respuesta del servicio o la llamada supera el tiempo de espera, o de forma asincrónica, donde el cliente realiza una llamada a la operación del servicio, continúa funcionando y recibe la respuesta del servicio en otro subproceso.</span><span class="sxs-lookup"><span data-stu-id="71b2f-106">You can perform calls to a service operation either synchronously, where the client blocks until it receives a response from the service or the call times, or asynchronously, where the client makes a call to the service operation, continues working, and receives the response from the service on another thread.</span></span>  
  
 <span data-ttu-id="71b2f-107">Para crear un contrato de servicios de la respuesta de la solicitud, defina su contrato de servicios y aplique la clase <xref:System.ServiceModel.OperationContractAttribute> a cada operación, como se muestra en el código de muestra siguiente.</span><span class="sxs-lookup"><span data-stu-id="71b2f-107">To create a request-reply service contract, define your service contract, and apply the <xref:System.ServiceModel.OperationContractAttribute> class to each operation, as shown in the following sample code.</span></span>  
  
```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface IRequestReplyCalculator  
{  
    [OperationContract]  
    double Add(double n1, double n2);  
}  
```  
  
 <span data-ttu-id="71b2f-108">No tiene que establecer la propiedad <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> en `false` porque se trata del comportamiento predeterminado.</span><span class="sxs-lookup"><span data-stu-id="71b2f-108">You do not have to set the  <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> property to `false` because this is the default behavior.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71b2f-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="71b2f-109">See also</span></span>

- [<span data-ttu-id="71b2f-110">Servicios unidireccionales</span><span class="sxs-lookup"><span data-stu-id="71b2f-110">One-Way Services</span></span>](one-way-services.md)
- [<span data-ttu-id="71b2f-111">Servicios dúplex</span><span class="sxs-lookup"><span data-stu-id="71b2f-111">Duplex Services</span></span>](duplex-services.md)
