---
title: Procesamiento de mensajes por orden en modo de simultaneidad única
ms.date: 03/30/2017
ms.assetid: a90f5662-a796-46cd-ae33-30a4072838af
ms.openlocfilehash: ecabb9a6e838b0137c538d76c554646356ea87f5
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2019
ms.locfileid: "70991502"
---
# <a name="ordered-processing-of-messages-in-single-concurrency-mode"></a><span data-ttu-id="e4f4c-102">Procesamiento de mensajes por orden en modo de simultaneidad única</span><span class="sxs-lookup"><span data-stu-id="e4f4c-102">Ordered Processing of Messages in Single Concurrency Mode</span></span>
<span data-ttu-id="e4f4c-103">WCF no ofrece ninguna garantía sobre el orden en el que se procesan los mensajes, a menos que el canal subyacente tenga sesiones.</span><span class="sxs-lookup"><span data-stu-id="e4f4c-103">WCF makes no guarantees about the order in which messages are processed, unless the underlying channel is sessionful.</span></span>  <span data-ttu-id="e4f4c-104">Por ejemplo, un servicio WCF que usa MsmqInputChannel, que no es un canal con sesión, no podrá procesar los mensajes en orden.</span><span class="sxs-lookup"><span data-stu-id="e4f4c-104">For instance, a WCF service that uses MsmqInputChannel, which is not a sessionful channel, will fail to process messages in order.</span></span> <span data-ttu-id="e4f4c-105">Hay algunas circunstancias en las que un desarrollador puede desear el comportamiento de procesamiento en orden pero no desea utilizar sesiones.</span><span class="sxs-lookup"><span data-stu-id="e4f4c-105">There are some circumstances where a developer may want the in order processing behavior but not want to use sessions.</span></span> <span data-ttu-id="e4f4c-106">En este tema se describe cómo configurar este comportamiento cuando un servicio se ejecuta en modo de simultaneidad única.</span><span class="sxs-lookup"><span data-stu-id="e4f4c-106">This topic describes how to configure this behavior when a service is running in Single Concurrency Mode.</span></span>  
  
## <a name="in-order-message-processing"></a><span data-ttu-id="e4f4c-107">Procesamiento de mensajes en orden</span><span class="sxs-lookup"><span data-stu-id="e4f4c-107">In-order Message Processing</span></span>  
 <span data-ttu-id="e4f4c-108">Se ha agregado un nuevo atributo denominado <xref:System.ServiceModel.ServiceBehaviorAttribute.EnsureOrderedDispatch%2A> a <xref:System.ServiceModel.ServiceBehaviorAttribute>.</span><span class="sxs-lookup"><span data-stu-id="e4f4c-108">A new attribute called <xref:System.ServiceModel.ServiceBehaviorAttribute.EnsureOrderedDispatch%2A> has been added to the <xref:System.ServiceModel.ServiceBehaviorAttribute>.</span></span> <span data-ttu-id="e4f4c-109">Cuando <xref:System.ServiceModel.ServiceBehaviorAttribute.EnsureOrderedDispatch%2A> se establece en true y <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A> se establece en <xref:System.ServiceModel.ConcurrencyMode.Single>, los mensajes enviados al servicio se procesará en orden.</span><span class="sxs-lookup"><span data-stu-id="e4f4c-109">When <xref:System.ServiceModel.ServiceBehaviorAttribute.EnsureOrderedDispatch%2A> is set to true and <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A> is set to <xref:System.ServiceModel.ConcurrencyMode.Single> messages sent to the service will be processed in order.</span></span> <span data-ttu-id="e4f4c-110">El fragmento de código siguiente muestra cómo establecer estos atributos.</span><span class="sxs-lookup"><span data-stu-id="e4f4c-110">The following code snippet illustrates how to set these attributes.</span></span>  
  
```csharp
[ServiceBehavior(ConcurrencyMode = ConcurrencyMode.Single, EnsureOrderedDispatch = true )]  
    class Service : IService  
    {  
         // ...  
    }  
```  
  
 <span data-ttu-id="e4f4c-111">Si <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A> se establece en cualquier otro valor, se produce <xref:System.InvalidOperationException>.</span><span class="sxs-lookup"><span data-stu-id="e4f4c-111">If <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A> is set to any other value, an <xref:System.InvalidOperationException> is thrown.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4f4c-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="e4f4c-112">See also</span></span>

- [<span data-ttu-id="e4f4c-113">Sesiones, creación de instancias y simultaneidad</span><span class="sxs-lookup"><span data-stu-id="e4f4c-113">Sessions, Instancing, and Concurrency</span></span>](../../../../docs/framework/wcf/feature-details/sessions-instancing-and-concurrency.md)
- [<span data-ttu-id="e4f4c-114">Simultaneidad</span><span class="sxs-lookup"><span data-stu-id="e4f4c-114">Concurrency</span></span>](../../../../docs/framework/wcf/samples/concurrency.md)
