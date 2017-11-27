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
# <a name="request-reply-services"></a>Servicios de solicitud-respuesta
Los servicios de solicitud-respuesta son el tipo predeterminado de contrato de operación en [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]. Los clientes realizan las llamadas a operaciones de servicio y esperan una respuesta del servicio. Puede realizar llamadas a una operación de servicio de manera sincrónica, donde el cliente se bloquea hasta que recibe una respuesta del servicio o la llamada supera el tiempo de espera, o de forma asincrónica, donde el cliente realiza una llamada a la operación del servicio, continúa funcionando y recibe la respuesta del servicio en otro subproceso.  
  
 Para crear un contrato de servicios de la respuesta de la solicitud, defina su contrato de servicios y aplique la clase <xref:System.ServiceModel.OperationContractAttribute> a cada operación, como se muestra en el código de muestra siguiente.  
  
```  
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface IRequestReplyCalculator  
{  
    [OperationContract]  
    double Add(double n1, double n2);  
}  
```  
  
 No tiene que establecer la propiedad <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> en `false` porque se trata del comportamiento predeterminado.  
  
## <a name="see-also"></a>Vea también  
 [Servicios unidireccionales](../../../../docs/framework/wcf/feature-details/one-way-services.md)  
 [Servicios dúplex](../../../../docs/framework/wcf/feature-details/duplex-services.md)
