---
title: Servicios de solicitud-respuesta
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Communication Foundation [WCF], request-reply services
- contracts [WCF], request-reply services
- WCF [WCF], request-reply services
- request-reply contracts [WCF]
ms.assetid: 2fa710f1-47f4-4598-b063-3ab3bd22ebba
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: a38a90d4e9ec249f91e8bfda88c646c006890d8d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="request-reply-services"></a><span data-ttu-id="eeead-102">Servicios de solicitud-respuesta</span><span class="sxs-lookup"><span data-stu-id="eeead-102">Request-Reply Services</span></span>
<span data-ttu-id="eeead-103">Los servicios de solicitud-respuesta son el tipo predeterminado de contrato de operación en [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="eeead-103">Request-reply services are the default type of operation contract in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span></span> <span data-ttu-id="eeead-104">Los clientes realizan las llamadas a operaciones de servicio y esperan una respuesta del servicio.</span><span class="sxs-lookup"><span data-stu-id="eeead-104">Clients make calls to service operations and wait for a response from the service.</span></span> <span data-ttu-id="eeead-105">Puede realizar llamadas a una operación de servicio de manera sincrónica, donde el cliente se bloquea hasta que recibe una respuesta del servicio o la llamada supera el tiempo de espera, o de forma asincrónica, donde el cliente realiza una llamada a la operación del servicio, continúa funcionando y recibe la respuesta del servicio en otro subproceso.</span><span class="sxs-lookup"><span data-stu-id="eeead-105">You can perform calls to a service operation either synchronously, where the client blocks until it receives a response from the service or the call times, or asynchronously, where the client makes a call to the service operation, continues working, and receives the response from the service on another thread.</span></span>  
  
 <span data-ttu-id="eeead-106">Para crear un contrato de servicios de la respuesta de la solicitud, defina su contrato de servicios y aplique la clase <xref:System.ServiceModel.OperationContractAttribute> a cada operación, como se muestra en el código de muestra siguiente.</span><span class="sxs-lookup"><span data-stu-id="eeead-106">To create a request-reply service contract, define your service contract, and apply the <xref:System.ServiceModel.OperationContractAttribute> class to each operation, as shown in the following sample code.</span></span>  
  
```  
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface IRequestReplyCalculator  
{  
    [OperationContract]  
    double Add(double n1, double n2);  
}  
```  
  
 <span data-ttu-id="eeead-107">No tiene que establecer la propiedad <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> en `false` porque se trata del comportamiento predeterminado.</span><span class="sxs-lookup"><span data-stu-id="eeead-107">You do not have to set the  <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> property to `false` because this is the default behavior.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eeead-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="eeead-108">See Also</span></span>  
 [<span data-ttu-id="eeead-109">Servicios unidireccionales</span><span class="sxs-lookup"><span data-stu-id="eeead-109">One-Way Services</span></span>](../../../../docs/framework/wcf/feature-details/one-way-services.md)  
 [<span data-ttu-id="eeead-110">Servicios dúplex</span><span class="sxs-lookup"><span data-stu-id="eeead-110">Duplex Services</span></span>](../../../../docs/framework/wcf/feature-details/duplex-services.md)
