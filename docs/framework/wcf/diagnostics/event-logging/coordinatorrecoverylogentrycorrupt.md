---
title: CoordinatorRecoveryLogEntryCorrupt
ms.date: 03/30/2017
ms.assetid: 3cd0c3e3-84c8-4d43-a561-a8851c78e565
ms.openlocfilehash: c3174e70d42385923674a3db5f696a0f64eda29f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96295370"
---
# <a name="coordinatorrecoverylogentrycorrupt"></a><span data-ttu-id="f347d-102">CoordinatorRecoveryLogEntryCorrupt</span><span class="sxs-lookup"><span data-stu-id="f347d-102">CoordinatorRecoveryLogEntryCorrupt</span></span>

<span data-ttu-id="f347d-103">ID.: 139</span><span class="sxs-lookup"><span data-stu-id="f347d-103">Id: 139</span></span>  
  
 <span data-ttu-id="f347d-104">Gravedad: error</span><span class="sxs-lookup"><span data-stu-id="f347d-104">Severity: Error</span></span>  
  
 <span data-ttu-id="f347d-105">Categoría: TransactionBridge</span><span class="sxs-lookup"><span data-stu-id="f347d-105">Category: TransactionBridge</span></span>  
  
## <a name="description"></a><span data-ttu-id="f347d-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="f347d-106">Description</span></span>  

 <span data-ttu-id="f347d-107">Este evento indica que una entrada del registro de recuperación de coordinador estaba dañada y no se pudo deserializar.</span><span class="sxs-lookup"><span data-stu-id="f347d-107">This event indicates that a  coordinator recovery log entry was corrupt and could not be deserialized.</span></span> <span data-ttu-id="f347d-108">Se pueden producir pérdidas de datos como resultado de este error.</span><span class="sxs-lookup"><span data-stu-id="f347d-108">Data loss may result from this error.</span></span> <span data-ttu-id="f347d-109">El evento detalla una lista de id. de transacción, datos de recuperación (codificados con Base64), excepción, nombre de proceso e id. de proceso.</span><span class="sxs-lookup"><span data-stu-id="f347d-109">The event lists the Transaction ID, Recovery data (Base64 encoded), exception, process name and process ID.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f347d-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="f347d-110">See also</span></span>

- [<span data-ttu-id="f347d-111">Registro de eventos</span><span class="sxs-lookup"><span data-stu-id="f347d-111">Event Logging</span></span>](index.md)
- [<span data-ttu-id="f347d-112">Referencia general de eventos</span><span class="sxs-lookup"><span data-stu-id="f347d-112">Events General Reference</span></span>](events-general-reference.md)
