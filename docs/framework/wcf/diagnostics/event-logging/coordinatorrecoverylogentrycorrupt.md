---
title: CoordinatorRecoveryLogEntryCorrupt
ms.date: 03/30/2017
ms.assetid: 3cd0c3e3-84c8-4d43-a561-a8851c78e565
ms.openlocfilehash: 0dc74b784d8a9ed3ab27bb4b8d3de34143f6ce07
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54639489"
---
# <a name="coordinatorrecoverylogentrycorrupt"></a><span data-ttu-id="f8739-102">CoordinatorRecoveryLogEntryCorrupt</span><span class="sxs-lookup"><span data-stu-id="f8739-102">CoordinatorRecoveryLogEntryCorrupt</span></span>
<span data-ttu-id="f8739-103">Id.: 139</span><span class="sxs-lookup"><span data-stu-id="f8739-103">Id: 139</span></span>  
  
 <span data-ttu-id="f8739-104">Gravedad: Error</span><span class="sxs-lookup"><span data-stu-id="f8739-104">Severity: Error</span></span>  
  
 <span data-ttu-id="f8739-105">Categoría: TransactionBridge</span><span class="sxs-lookup"><span data-stu-id="f8739-105">Category: TransactionBridge</span></span>  
  
## <a name="description"></a><span data-ttu-id="f8739-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="f8739-106">Description</span></span>  
 <span data-ttu-id="f8739-107">Este evento indica que una entrada del registro de recuperación de coordinador estaba dañada y no se pudo deserializar.</span><span class="sxs-lookup"><span data-stu-id="f8739-107">This event indicates that a  coordinator recovery log entry was corrupt and could not be deserialized.</span></span> <span data-ttu-id="f8739-108">Se pueden producir pérdidas de datos como resultado de este error.</span><span class="sxs-lookup"><span data-stu-id="f8739-108">Data loss may result from this error.</span></span> <span data-ttu-id="f8739-109">El evento detalla una lista de id. de transacción, datos de recuperación (codificados con Base64), excepción, nombre de proceso e id. de proceso.</span><span class="sxs-lookup"><span data-stu-id="f8739-109">The event lists the Transaction ID, Recovery data (Base64 encoded), exception, process name and process ID.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8739-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="f8739-110">See also</span></span>
- [<span data-ttu-id="f8739-111">Registro de eventos</span><span class="sxs-lookup"><span data-stu-id="f8739-111">Event Logging</span></span>](../../../../../docs/framework/wcf/diagnostics/event-logging/index.md)
- [<span data-ttu-id="f8739-112">Referencia general de eventos</span><span class="sxs-lookup"><span data-stu-id="f8739-112">Events General Reference</span></span>](../../../../../docs/framework/wcf/diagnostics/event-logging/events-general-reference.md)
