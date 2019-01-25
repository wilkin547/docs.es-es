---
title: ParticipantRecoveryLogEntryCorrupt
ms.date: 03/30/2017
ms.assetid: ab34785f-f953-4428-93ca-3c50d3f50a4a
ms.openlocfilehash: 6856ac8b70ec30b795585b4ab2d2e76d1b61796c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54684507"
---
# <a name="participantrecoverylogentrycorrupt"></a><span data-ttu-id="b4cc0-102">ParticipantRecoveryLogEntryCorrupt</span><span class="sxs-lookup"><span data-stu-id="b4cc0-102">ParticipantRecoveryLogEntryCorrupt</span></span>
<span data-ttu-id="b4cc0-103">Id.: 138</span><span class="sxs-lookup"><span data-stu-id="b4cc0-103">Id: 138</span></span>  
  
 <span data-ttu-id="b4cc0-104">Gravedad: Error</span><span class="sxs-lookup"><span data-stu-id="b4cc0-104">Severity: Error</span></span>  
  
 <span data-ttu-id="b4cc0-105">Categoría: TransactionBridge</span><span class="sxs-lookup"><span data-stu-id="b4cc0-105">Category: TransactionBridge</span></span>  
  
## <a name="description"></a><span data-ttu-id="b4cc0-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="b4cc0-106">Description</span></span>  
 <span data-ttu-id="b4cc0-107">Este evento indica que una entrada de registro de recuperación participante estaba dañada y no se pudo deserializar.</span><span class="sxs-lookup"><span data-stu-id="b4cc0-107">This event indicates that a participant recovery log entry was corrupt and could not be deserialized.</span></span> <span data-ttu-id="b4cc0-108">Se pueden producir pérdidas de datos como resultado de este error.</span><span class="sxs-lookup"><span data-stu-id="b4cc0-108">Data loss may result from this error.</span></span> <span data-ttu-id="b4cc0-109">El evento detalla una lista de id. de transacción, datos de recuperación (codificados con Base64), excepción, nombre de proceso e id. de proceso.</span><span class="sxs-lookup"><span data-stu-id="b4cc0-109">The event lists the Transaction ID, Recovery data (Base64 encoded), exception, process name and process ID.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4cc0-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="b4cc0-110">See also</span></span>
- [<span data-ttu-id="b4cc0-111">Registro de eventos</span><span class="sxs-lookup"><span data-stu-id="b4cc0-111">Event Logging</span></span>](../../../../../docs/framework/wcf/diagnostics/event-logging/index.md)
- [<span data-ttu-id="b4cc0-112">Referencia general de eventos</span><span class="sxs-lookup"><span data-stu-id="b4cc0-112">Events General Reference</span></span>](../../../../../docs/framework/wcf/diagnostics/event-logging/events-general-reference.md)
