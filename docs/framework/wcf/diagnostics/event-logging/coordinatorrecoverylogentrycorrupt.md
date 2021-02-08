---
description: 'Más información acerca de: CoordinatorRecoveryLogEntryCorrupt'
title: CoordinatorRecoveryLogEntryCorrupt
ms.date: 03/30/2017
ms.assetid: 3cd0c3e3-84c8-4d43-a561-a8851c78e565
ms.openlocfilehash: 3a848c634a226b34023a24898f9827162b4dafc7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99771345"
---
# <a name="coordinatorrecoverylogentrycorrupt"></a><span data-ttu-id="46405-103">CoordinatorRecoveryLogEntryCorrupt</span><span class="sxs-lookup"><span data-stu-id="46405-103">CoordinatorRecoveryLogEntryCorrupt</span></span>

<span data-ttu-id="46405-104">ID.: 139</span><span class="sxs-lookup"><span data-stu-id="46405-104">Id: 139</span></span>  
  
 <span data-ttu-id="46405-105">Gravedad: error</span><span class="sxs-lookup"><span data-stu-id="46405-105">Severity: Error</span></span>  
  
 <span data-ttu-id="46405-106">Categoría: TransactionBridge</span><span class="sxs-lookup"><span data-stu-id="46405-106">Category: TransactionBridge</span></span>  
  
## <a name="description"></a><span data-ttu-id="46405-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="46405-107">Description</span></span>  

 <span data-ttu-id="46405-108">Este evento indica que una entrada del registro de recuperación de coordinador estaba dañada y no se pudo deserializar.</span><span class="sxs-lookup"><span data-stu-id="46405-108">This event indicates that a  coordinator recovery log entry was corrupt and could not be deserialized.</span></span> <span data-ttu-id="46405-109">Se pueden producir pérdidas de datos como resultado de este error.</span><span class="sxs-lookup"><span data-stu-id="46405-109">Data loss may result from this error.</span></span> <span data-ttu-id="46405-110">El evento detalla una lista de id. de transacción, datos de recuperación (codificados con Base64), excepción, nombre de proceso e id. de proceso.</span><span class="sxs-lookup"><span data-stu-id="46405-110">The event lists the Transaction ID, Recovery data (Base64 encoded), exception, process name and process ID.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46405-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="46405-111">See also</span></span>

- [<span data-ttu-id="46405-112">Registro de eventos</span><span class="sxs-lookup"><span data-stu-id="46405-112">Event Logging</span></span>](index.md)
- [<span data-ttu-id="46405-113">Referencia general de eventos</span><span class="sxs-lookup"><span data-stu-id="46405-113">Events General Reference</span></span>](events-general-reference.md)
