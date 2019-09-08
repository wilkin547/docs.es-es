---
title: CoordinatorRecoveryLogEntryCorrupt
ms.date: 03/30/2017
ms.assetid: 3cd0c3e3-84c8-4d43-a561-a8851c78e565
ms.openlocfilehash: de9d27e74088b1bac9c8a401c5af2b119fc8e90e
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70797988"
---
# <a name="coordinatorrecoverylogentrycorrupt"></a><span data-ttu-id="64b9a-102">CoordinatorRecoveryLogEntryCorrupt</span><span class="sxs-lookup"><span data-stu-id="64b9a-102">CoordinatorRecoveryLogEntryCorrupt</span></span>
<span data-ttu-id="64b9a-103">Id.: 139</span><span class="sxs-lookup"><span data-stu-id="64b9a-103">Id: 139</span></span>  
  
 <span data-ttu-id="64b9a-104">Gravedad Error</span><span class="sxs-lookup"><span data-stu-id="64b9a-104">Severity: Error</span></span>  
  
 <span data-ttu-id="64b9a-105">Categoría TransactionBridge</span><span class="sxs-lookup"><span data-stu-id="64b9a-105">Category: TransactionBridge</span></span>  
  
## <a name="description"></a><span data-ttu-id="64b9a-106">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="64b9a-106">Description</span></span>  
 <span data-ttu-id="64b9a-107">Este evento indica que una entrada del registro de recuperación de coordinador estaba dañada y no se pudo deserializar.</span><span class="sxs-lookup"><span data-stu-id="64b9a-107">This event indicates that a  coordinator recovery log entry was corrupt and could not be deserialized.</span></span> <span data-ttu-id="64b9a-108">Se pueden producir pérdidas de datos como resultado de este error.</span><span class="sxs-lookup"><span data-stu-id="64b9a-108">Data loss may result from this error.</span></span> <span data-ttu-id="64b9a-109">El evento detalla una lista de id. de transacción, datos de recuperación (codificados con Base64), excepción, nombre de proceso e id. de proceso.</span><span class="sxs-lookup"><span data-stu-id="64b9a-109">The event lists the Transaction ID, Recovery data (Base64 encoded), exception, process name and process ID.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64b9a-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="64b9a-110">See also</span></span>

- [<span data-ttu-id="64b9a-111">Registro de eventos</span><span class="sxs-lookup"><span data-stu-id="64b9a-111">Event Logging</span></span>](index.md)
- [<span data-ttu-id="64b9a-112">Referencia general de eventos</span><span class="sxs-lookup"><span data-stu-id="64b9a-112">Events General Reference</span></span>](events-general-reference.md)
