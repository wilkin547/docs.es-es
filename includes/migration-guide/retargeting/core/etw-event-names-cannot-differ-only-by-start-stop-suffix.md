---
ms.openlocfilehash: 71c81cf188fa4c2300661f10eb87e7ae00e031f6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "67804401"
---
### <a name="etw-event-names-cannot-differ-only-by-a-start-or-stop-suffix"></a><span data-ttu-id="7142b-101">Los nombres de eventos de ETW no pueden diferir solamente en un sufijo "Start" o "Stop".</span><span class="sxs-lookup"><span data-stu-id="7142b-101">ETW event names cannot differ only by a "Start" or "Stop" suffix</span></span>

|   |   |
|---|---|
|<span data-ttu-id="7142b-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="7142b-102">Details</span></span>|<span data-ttu-id="7142b-103">En .NET Framework 4.6 y 4.6.1, el entorno de ejecución inicia una excepción <xref:System.ArgumentException> cuando dos nombres de evento de Seguimiento de eventos para Windows (ETW) solamente difieren en un sufijo &quot;Start&quot; o &quot;Stop&quot; (como cuando un evento se denomina <code>LogUser</code> y otro <code>LogUserStart</code>).</span><span class="sxs-lookup"><span data-stu-id="7142b-103">In the .NET Framework 4.6 and 4.6.1, the runtime throws an <xref:System.ArgumentException> when two Event Tracing for Windows (ETW) event names differ only by a &quot;Start&quot; or &quot;Stop&quot; suffix (as when one event is named <code>LogUser</code> and another is named <code>LogUserStart</code>).</span></span> <span data-ttu-id="7142b-104">En este caso, el entorno en tiempo de ejecución no puede crear el origen de eventos, que no puede emitir ningún registro.</span><span class="sxs-lookup"><span data-stu-id="7142b-104">In this case, the runtime cannot construct the event source, which cannot emit any logging.</span></span>|
|<span data-ttu-id="7142b-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="7142b-105">Suggestion</span></span>|<span data-ttu-id="7142b-106">Para evitar la excepción, asegúrese de que no haya dos nombres de evento que solo difieran en un sufijo &quot;Start&quot; o &quot;Stop&quot;. Este requisito se ha eliminado a partir de .NET Framework 4.6.2; el entorno de ejecución puede eliminar la ambigüedad de los nombres de evento que solo difieren en el sufijo &quot;Start&quot; y &quot;Stop&quot;.</span><span class="sxs-lookup"><span data-stu-id="7142b-106">To prevent the exception, ensure that no two event names differ only by a &quot;Start&quot; or &quot;Stop&quot; suffix.This requirement is removed starting with the .NET Framework 4.6.2; the runtime can disambiguate event names that differ only by the &quot;Start&quot; and &quot;Stop&quot; suffix.</span></span>|
|<span data-ttu-id="7142b-107">Ámbito</span><span class="sxs-lookup"><span data-stu-id="7142b-107">Scope</span></span>|<span data-ttu-id="7142b-108">Borde</span><span class="sxs-lookup"><span data-stu-id="7142b-108">Edge</span></span>|
|<span data-ttu-id="7142b-109">Versión</span><span class="sxs-lookup"><span data-stu-id="7142b-109">Version</span></span>|<span data-ttu-id="7142b-110">4.6</span><span class="sxs-lookup"><span data-stu-id="7142b-110">4.6</span></span>|
|<span data-ttu-id="7142b-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="7142b-111">Type</span></span>|<span data-ttu-id="7142b-112">Redestinación</span><span class="sxs-lookup"><span data-stu-id="7142b-112">Retargeting</span></span>|
