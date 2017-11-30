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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 1db6f8dc4136623f35767c122dbea46fd4706b85
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="coordinatorrecoverylogentrycorrupt"></a><span data-ttu-id="51768-102">CoordinatorRecoveryLogEntryCorrupt</span><span class="sxs-lookup"><span data-stu-id="51768-102">CoordinatorRecoveryLogEntryCorrupt</span></span>
<span data-ttu-id="51768-103">Id.: 139</span><span class="sxs-lookup"><span data-stu-id="51768-103">Id: 139</span></span>  
  
 <span data-ttu-id="51768-104">Gravedad: error</span><span class="sxs-lookup"><span data-stu-id="51768-104">Severity: Error</span></span>  
  
 <span data-ttu-id="51768-105">Categoría: TransactionBridge</span><span class="sxs-lookup"><span data-stu-id="51768-105">Category: TransactionBridge</span></span>  
  
## <a name="description"></a><span data-ttu-id="51768-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="51768-106">Description</span></span>  
 <span data-ttu-id="51768-107">Este evento indica que una entrada del registro de recuperación de coordinador estaba dañada y no se pudo deserializar.</span><span class="sxs-lookup"><span data-stu-id="51768-107">This event indicates that a  coordinator recovery log entry was corrupt and could not be deserialized.</span></span> <span data-ttu-id="51768-108">Se pueden producir pérdidas de datos como resultado de este error.</span><span class="sxs-lookup"><span data-stu-id="51768-108">Data loss may result from this error.</span></span> <span data-ttu-id="51768-109">El evento detalla una lista de id. de transacción, datos de recuperación (codificados con Base64), excepción, nombre de proceso e id. de proceso.</span><span class="sxs-lookup"><span data-stu-id="51768-109">The event lists the Transaction ID, Recovery data (Base64 encoded), exception, process name and process ID.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51768-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="51768-110">See Also</span></span>  
 [<span data-ttu-id="51768-111">Registro de eventos</span><span class="sxs-lookup"><span data-stu-id="51768-111">Event Logging</span></span>](../../../../../docs/framework/wcf/diagnostics/event-logging/index.md)  
 [<span data-ttu-id="51768-112">Referencia General de eventos</span><span class="sxs-lookup"><span data-stu-id="51768-112">Events General Reference</span></span>](../../../../../docs/framework/wcf/diagnostics/event-logging/events-general-reference.md)
