---
title: "Mitigación: Llamadas al método EventSource.WriteEvent"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 327a9fdb-ba8e-40f7-89e5-4c89b46e594f
caps.latest.revision: 6
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 270f89183bced5d07598b1731f18acf90ec9715a
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="mitigation-eventsourcewriteevent-method-calls"></a><span data-ttu-id="3eccb-102">Mitigación: Llamadas al método EventSource.WriteEvent</span><span class="sxs-lookup"><span data-stu-id="3eccb-102">Mitigation: EventSource.WriteEvent Method Calls</span></span>
<span data-ttu-id="3eccb-103">[!INCLUDE[net_v451](../../../includes/net-v451-md.md)] fuerza un contrato entre un método de evento ETW de una clase derivada de <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> y el método <xref:System.Diagnostics.Tracing.EventSource.WriteEvent%2A> de su clase base.</span><span class="sxs-lookup"><span data-stu-id="3eccb-103">The [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] enforces a contract between an ETW event method in a class that is derived from <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> and  the <xref:System.Diagnostics.Tracing.EventSource.WriteEvent%2A> method of its base class.</span></span> <span data-ttu-id="3eccb-104">El método de evento ETW debe pasar al método <xref:System.Diagnostics.Tracing.EventSource.WriteEvent%2A> el identificador de evento seguido de los mismos argumentos que se pasaron al método del evento.</span><span class="sxs-lookup"><span data-stu-id="3eccb-104">The ETW event method must pass the <xref:System.Diagnostics.Tracing.EventSource.WriteEvent%2A> method the event ID followed by the same arguments that were passed to the event method.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="3eccb-105">Impacto</span><span class="sxs-lookup"><span data-stu-id="3eccb-105">Impact</span></span>  
 <span data-ttu-id="3eccb-106">Un método de evento ETW definido de la manera siguiente infringe el contrato:</span><span class="sxs-lookup"><span data-stu-id="3eccb-106">An ETW event method defined in the following way breaks the contract:</span></span>  
  
```  
[Event(2, Level = EventLevel.Informational)]  
public void Info2(string message)  
{  
   base.WriteEvent(2, message, "-");  
}  
```  
  
 <span data-ttu-id="3eccb-107">Cuando se infringe este contrato, se genera una excepción <xref:System.IndexOutOfRangeException> en tiempo de ejecución si un objeto <xref:System.Diagnostics.Tracing.EventListener> lee datos <xref:System.Diagnostics.Tracing.EventSource> en proceso.</span><span class="sxs-lookup"><span data-stu-id="3eccb-107">When this contract is violated, an <xref:System.IndexOutOfRangeException> exception is thrown at run time if an <xref:System.Diagnostics.Tracing.EventListener> object reads <xref:System.Diagnostics.Tracing.EventSource> data in process.</span></span>  
  
 <span data-ttu-id="3eccb-108">La definición de este método de evento ETW debe seguir este patrón:</span><span class="sxs-lookup"><span data-stu-id="3eccb-108">The definition for this ETW event method should follow this pattern:</span></span>  
  
```  
[Event(2, Level = EventLevel.Informational)]  
public void Info2(string message)  
{  
   base.WriteEvent(2, message);  
}  
```  
  
## <a name="mitigation"></a><span data-ttu-id="3eccb-109">Mitigación</span><span class="sxs-lookup"><span data-stu-id="3eccb-109">Mitigation</span></span>  
 <span data-ttu-id="3eccb-110">Debe modificar el código existente para que se ajuste al patrón requerido.</span><span class="sxs-lookup"><span data-stu-id="3eccb-110">You must modify existing code to conform to the required pattern.</span></span>  
  
 <span data-ttu-id="3eccb-111">Puede minimizar la cantidad de código que hay que cambiar definiendo dos métodos para llamar al método <xref:System.Diagnostics.Tracing.EventSource.WriteEvent%2A> , de la forma siguiente:</span><span class="sxs-lookup"><span data-stu-id="3eccb-111">You can minimize the amount of code that you have to change by defining two methods for calling the <xref:System.Diagnostics.Tracing.EventSource.WriteEvent%2A> method, as follows:</span></span>  
  
```  
[NonEvent]  
public void Info2(string message)  
{  
   Info2Internal(message, "-");  
}  
  
public void Info2Internal(string message, string prefix)  
{  
   WriteEvent(2, message, prefix);  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="3eccb-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="3eccb-112">See Also</span></span>  
 [<span data-ttu-id="3eccb-113">Cambios en el runtime</span><span class="sxs-lookup"><span data-stu-id="3eccb-113">Runtime Changes</span></span>](../../../docs/framework/migration-guide/runtime-changes-in-the-net-framework-4-5-1.md)

