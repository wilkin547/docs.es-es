---
title: CoordinatorRecoveryLogEntryCorrupt
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3cd0c3e3-84c8-4d43-a561-a8851c78e565
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ae2b8a8bb536d914edd6c7154136867caee553b1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="coordinatorrecoverylogentrycorrupt"></a><span data-ttu-id="109ee-102">CoordinatorRecoveryLogEntryCorrupt</span><span class="sxs-lookup"><span data-stu-id="109ee-102">CoordinatorRecoveryLogEntryCorrupt</span></span>
<span data-ttu-id="109ee-103">Id.: 139</span><span class="sxs-lookup"><span data-stu-id="109ee-103">Id: 139</span></span>  
  
 <span data-ttu-id="109ee-104">Gravedad: error</span><span class="sxs-lookup"><span data-stu-id="109ee-104">Severity: Error</span></span>  
  
 <span data-ttu-id="109ee-105">Categoría: TransactionBridge</span><span class="sxs-lookup"><span data-stu-id="109ee-105">Category: TransactionBridge</span></span>  
  
## <a name="description"></a><span data-ttu-id="109ee-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="109ee-106">Description</span></span>  
 <span data-ttu-id="109ee-107">Este evento indica que una entrada del registro de recuperación de coordinador estaba dañada y no se pudo deserializar.</span><span class="sxs-lookup"><span data-stu-id="109ee-107">This event indicates that a  coordinator recovery log entry was corrupt and could not be deserialized.</span></span> <span data-ttu-id="109ee-108">Se pueden producir pérdidas de datos como resultado de este error.</span><span class="sxs-lookup"><span data-stu-id="109ee-108">Data loss may result from this error.</span></span> <span data-ttu-id="109ee-109">El evento detalla una lista de id. de transacción, datos de recuperación (codificados con Base64), excepción, nombre de proceso e id. de proceso.</span><span class="sxs-lookup"><span data-stu-id="109ee-109">The event lists the Transaction ID, Recovery data (Base64 encoded), exception, process name and process ID.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="109ee-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="109ee-110">See Also</span></span>  
 [<span data-ttu-id="109ee-111">Registro de eventos</span><span class="sxs-lookup"><span data-stu-id="109ee-111">Event Logging</span></span>](../../../../../docs/framework/wcf/diagnostics/event-logging/index.md)  
 [<span data-ttu-id="109ee-112">Referencia general de eventos</span><span class="sxs-lookup"><span data-stu-id="109ee-112">Events General Reference</span></span>](../../../../../docs/framework/wcf/diagnostics/event-logging/events-general-reference.md)
