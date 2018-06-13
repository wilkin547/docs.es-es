---
title: CoordinatorRecoveryLogEntryCorrupt
ms.date: 03/30/2017
ms.assetid: 3cd0c3e3-84c8-4d43-a561-a8851c78e565
ms.openlocfilehash: 3f51d1269f5ca89f4f02257c8accef3423aa7eb5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33472688"
---
# <a name="coordinatorrecoverylogentrycorrupt"></a><span data-ttu-id="71ea9-102">CoordinatorRecoveryLogEntryCorrupt</span><span class="sxs-lookup"><span data-stu-id="71ea9-102">CoordinatorRecoveryLogEntryCorrupt</span></span>
<span data-ttu-id="71ea9-103">Id.: 139</span><span class="sxs-lookup"><span data-stu-id="71ea9-103">Id: 139</span></span>  
  
 <span data-ttu-id="71ea9-104">Gravedad: error</span><span class="sxs-lookup"><span data-stu-id="71ea9-104">Severity: Error</span></span>  
  
 <span data-ttu-id="71ea9-105">Categoría: TransactionBridge</span><span class="sxs-lookup"><span data-stu-id="71ea9-105">Category: TransactionBridge</span></span>  
  
## <a name="description"></a><span data-ttu-id="71ea9-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="71ea9-106">Description</span></span>  
 <span data-ttu-id="71ea9-107">Este evento indica que una entrada del registro de recuperación de coordinador estaba dañada y no se pudo deserializar.</span><span class="sxs-lookup"><span data-stu-id="71ea9-107">This event indicates that a  coordinator recovery log entry was corrupt and could not be deserialized.</span></span> <span data-ttu-id="71ea9-108">Se pueden producir pérdidas de datos como resultado de este error.</span><span class="sxs-lookup"><span data-stu-id="71ea9-108">Data loss may result from this error.</span></span> <span data-ttu-id="71ea9-109">El evento detalla una lista de id. de transacción, datos de recuperación (codificados con Base64), excepción, nombre de proceso e id. de proceso.</span><span class="sxs-lookup"><span data-stu-id="71ea9-109">The event lists the Transaction ID, Recovery data (Base64 encoded), exception, process name and process ID.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71ea9-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="71ea9-110">See Also</span></span>  
 [<span data-ttu-id="71ea9-111">Registro de eventos</span><span class="sxs-lookup"><span data-stu-id="71ea9-111">Event Logging</span></span>](../../../../../docs/framework/wcf/diagnostics/event-logging/index.md)  
 [<span data-ttu-id="71ea9-112">Referencia general de eventos</span><span class="sxs-lookup"><span data-stu-id="71ea9-112">Events General Reference</span></span>](../../../../../docs/framework/wcf/diagnostics/event-logging/events-general-reference.md)
