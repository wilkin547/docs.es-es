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
# <a name="request-reply-services"></a>Servicios de solicitud-respuesta

Los servicios de solicitud-respuesta son el tipo predeterminado de contrato de operación en Windows Communication Foundation (WCF). Los clientes realizan las llamadas a operaciones de servicio y esperan una respuesta del servicio. Puede realizar llamadas a una operación de servicio de manera sincrónica, donde el cliente se bloquea hasta que recibe una respuesta del servicio o la llamada supera el tiempo de espera, o de forma asincrónica, donde el cliente realiza una llamada a la operación del servicio, continúa funcionando y recibe la respuesta del servicio en otro subproceso.  
  
 Para crear un contrato de servicios de la respuesta de la solicitud, defina su contrato de servicios y aplique la clase <xref:System.ServiceModel.OperationContractAttribute> a cada operación, como se muestra en el código de muestra siguiente.  
  
```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface IRequestReplyCalculator  
{  
    [OperationContract]  
    double Add(double n1, double n2);  
}  
```  
  
 No tiene que establecer la propiedad <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> en `false` porque se trata del comportamiento predeterminado.  
  
## <a name="see-also"></a>Vea también

- [Servicios unidireccionales](one-way-services.md)
- [Servicios dúplex](duplex-services.md)
