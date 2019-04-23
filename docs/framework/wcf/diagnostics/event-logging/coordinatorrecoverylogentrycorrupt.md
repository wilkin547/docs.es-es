---
title: CoordinatorRecoveryLogEntryCorrupt
ms.date: 03/30/2017
ms.assetid: 3cd0c3e3-84c8-4d43-a561-a8851c78e565
ms.openlocfilehash: faf4a07badb71588c601cd9390e4d8e3f187e629
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59121633"
---
# <a name="coordinatorrecoverylogentrycorrupt"></a><span data-ttu-id="fd39c-102">CoordinatorRecoveryLogEntryCorrupt</span><span class="sxs-lookup"><span data-stu-id="fd39c-102">CoordinatorRecoveryLogEntryCorrupt</span></span>
<span data-ttu-id="fd39c-103">Id.: 139</span><span class="sxs-lookup"><span data-stu-id="fd39c-103">Id: 139</span></span>  
  
 <span data-ttu-id="fd39c-104">Gravedad: Error</span><span class="sxs-lookup"><span data-stu-id="fd39c-104">Severity: Error</span></span>  
  
 <span data-ttu-id="fd39c-105">Categoría: TransactionBridge</span><span class="sxs-lookup"><span data-stu-id="fd39c-105">Category: TransactionBridge</span></span>  
  
## <a name="description"></a><span data-ttu-id="fd39c-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="fd39c-106">Description</span></span>  
 <span data-ttu-id="fd39c-107">Este evento indica que una entrada del registro de recuperación de coordinador estaba dañada y no se pudo deserializar.</span><span class="sxs-lookup"><span data-stu-id="fd39c-107">This event indicates that a  coordinator recovery log entry was corrupt and could not be deserialized.</span></span> <span data-ttu-id="fd39c-108">Se pueden producir pérdidas de datos como resultado de este error.</span><span class="sxs-lookup"><span data-stu-id="fd39c-108">Data loss may result from this error.</span></span> <span data-ttu-id="fd39c-109">El evento detalla una lista de id. de transacción, datos de recuperación (codificados con Base64), excepción, nombre de proceso e id. de proceso.</span><span class="sxs-lookup"><span data-stu-id="fd39c-109">The event lists the Transaction ID, Recovery data (Base64 encoded), exception, process name and process ID.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd39c-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="fd39c-110">See also</span></span>

- [<span data-ttu-id="fd39c-111">Registro de eventos</span><span class="sxs-lookup"><span data-stu-id="fd39c-111">Event Logging</span></span>](../../../../../docs/framework/wcf/diagnostics/event-logging/index.md)
- [<span data-ttu-id="fd39c-112">Referencia general de eventos</span><span class="sxs-lookup"><span data-stu-id="fd39c-112">Events General Reference</span></span>](../../../../../docs/framework/wcf/diagnostics/event-logging/events-general-reference.md)
