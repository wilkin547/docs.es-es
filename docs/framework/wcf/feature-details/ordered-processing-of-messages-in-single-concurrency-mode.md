---
description: 'Más información sobre: procesamiento ordenado de mensajes en modo de simultaneidad única'
title: Procesamiento de mensajes por orden en modo de simultaneidad única
ms.date: 03/30/2017
ms.assetid: a90f5662-a796-46cd-ae33-30a4072838af
ms.openlocfilehash: 2dd876f1831dda8b388108f238810be333e693be
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99733689"
---
# <a name="ordered-processing-of-messages-in-single-concurrency-mode"></a>Procesamiento de mensajes por orden en modo de simultaneidad única

WCF no ofrece ninguna garantía sobre el orden en el que se procesan los mensajes, a menos que el canal subyacente tenga sesiones.  Por ejemplo, un servicio WCF que usa MsmqInputChannel, que no es un canal con sesión, no podrá procesar los mensajes en orden. Hay algunas circunstancias en las que un desarrollador puede desear el comportamiento de procesamiento en orden pero no desea utilizar sesiones. En este tema se describe cómo configurar este comportamiento cuando un servicio se ejecuta en modo de simultaneidad única.  
  
## <a name="in-order-message-processing"></a>Procesamiento de mensajes en orden  

 Se ha agregado un nuevo atributo denominado <xref:System.ServiceModel.ServiceBehaviorAttribute.EnsureOrderedDispatch%2A> a <xref:System.ServiceModel.ServiceBehaviorAttribute>. Cuando <xref:System.ServiceModel.ServiceBehaviorAttribute.EnsureOrderedDispatch%2A> se establece en true y <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A> se establece en <xref:System.ServiceModel.ConcurrencyMode.Single>, los mensajes enviados al servicio se procesará en orden. El fragmento de código siguiente muestra cómo establecer estos atributos.  
  
```csharp
[ServiceBehavior(ConcurrencyMode = ConcurrencyMode.Single, EnsureOrderedDispatch = true )]  
    class Service : IService  
    {  
         // ...  
    }  
```  
  
 Si <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A> se establece en cualquier otro valor, se produce <xref:System.InvalidOperationException>.  
  
## <a name="see-also"></a>Vea también

- [Sesiones, creación de instancias y simultaneidad](sessions-instancing-and-concurrency.md)
- [Simultaneidad](../samples/concurrency.md)
