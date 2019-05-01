---
title: CoordinatorRecoveryLogEntryCorrupt
ms.date: 03/30/2017
ms.assetid: 3cd0c3e3-84c8-4d43-a561-a8851c78e565
ms.openlocfilehash: faf4a07badb71588c601cd9390e4d8e3f187e629
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61969655"
---
# <a name="coordinatorrecoverylogentrycorrupt"></a><span data-ttu-id="e8fc3-102">CoordinatorRecoveryLogEntryCorrupt</span><span class="sxs-lookup"><span data-stu-id="e8fc3-102">CoordinatorRecoveryLogEntryCorrupt</span></span>
<span data-ttu-id="e8fc3-103">Id.: 139</span><span class="sxs-lookup"><span data-stu-id="e8fc3-103">Id: 139</span></span>  
  
 <span data-ttu-id="e8fc3-104">Gravedad: Error</span><span class="sxs-lookup"><span data-stu-id="e8fc3-104">Severity: Error</span></span>  
  
 <span data-ttu-id="e8fc3-105">Categoría: TransactionBridge</span><span class="sxs-lookup"><span data-stu-id="e8fc3-105">Category: TransactionBridge</span></span>  
  
## <a name="description"></a><span data-ttu-id="e8fc3-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="e8fc3-106">Description</span></span>  
 <span data-ttu-id="e8fc3-107">Este evento indica que una entrada del registro de recuperación de coordinador estaba dañada y no se pudo deserializar.</span><span class="sxs-lookup"><span data-stu-id="e8fc3-107">This event indicates that a  coordinator recovery log entry was corrupt and could not be deserialized.</span></span> <span data-ttu-id="e8fc3-108">Se pueden producir pérdidas de datos como resultado de este error.</span><span class="sxs-lookup"><span data-stu-id="e8fc3-108">Data loss may result from this error.</span></span> <span data-ttu-id="e8fc3-109">El evento detalla una lista de id. de transacción, datos de recuperación (codificados con Base64), excepción, nombre de proceso e id. de proceso.</span><span class="sxs-lookup"><span data-stu-id="e8fc3-109">The event lists the Transaction ID, Recovery data (Base64 encoded), exception, process name and process ID.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8fc3-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="e8fc3-110">See also</span></span>

- [<span data-ttu-id="e8fc3-111">Registro de eventos</span><span class="sxs-lookup"><span data-stu-id="e8fc3-111">Event Logging</span></span>](../../../../../docs/framework/wcf/diagnostics/event-logging/index.md)
- [<span data-ttu-id="e8fc3-112">Referencia general de eventos</span><span class="sxs-lookup"><span data-stu-id="e8fc3-112">Events General Reference</span></span>](../../../../../docs/framework/wcf/diagnostics/event-logging/events-general-reference.md)
