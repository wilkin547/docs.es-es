---
title: Procesamiento de mensajes por orden en modo de simultaneidad única
ms.date: 03/30/2017
ms.assetid: a90f5662-a796-46cd-ae33-30a4072838af
ms.openlocfilehash: bbbc1f62931abda438c3d06b514518b1199b649e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33493925"
---
# <a name="ordered-processing-of-messages-in-single-concurrency-mode"></a>Procesamiento de mensajes por orden en modo de simultaneidad única
WCF ofrece ninguna garantía sobre el orden en que se procesan los mensajes, a menos que el canal subyacente es con sesión.  Por ejemplo, un servicio WCF que usa MsmqInputChannel, que no es un canal con sesión, se producirá un error al procesar mensajes en orden. Hay algunas circunstancias donde un desarrollador puede desea el comportamiento de procesamiento de pedidos en pero no desea utilizar las sesiones. En este tema se describe cómo configurar este comportamiento cuando un servicio se ejecuta en modo de simultaneidad única.  
  
## <a name="in-order-message-processing"></a>Procesamiento de mensajes en orden  
 Se ha agregado un nuevo atributo denominado <xref:System.ServiceModel.ServiceBehaviorAttribute.EnsureOrderedDispatch%2A> a <xref:System.ServiceModel.ServiceBehaviorAttribute>. Cuando <xref:System.ServiceModel.ServiceBehaviorAttribute.EnsureOrderedDispatch%2A> se establece en true y <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A> se establece en <xref:System.ServiceModel.ConcurrencyMode.Single>, los mensajes enviados al servicio se procesará en orden. El fragmento de código siguiente muestra cómo establecer estos atributos.  
  
```  
[ServiceBehavior(ConcurrencyMode = ConcurrencyMode.Single, EnsureOrderedDispatch = true )]  
    class Service : IService  
    {  
         // ...  
    }  
```  
  
 Si <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A> se establece en cualquier otro valor, se produce <xref:System.InvalidOperationException>.  
  
## <a name="see-also"></a>Vea también  
 [Sesiones, creación de instancias y simultaneidad](../../../../docs/framework/wcf/feature-details/sessions-instancing-and-concurrency.md)  
 [Simultaneidad](../../../../docs/framework/wcf/samples/concurrency.md)
