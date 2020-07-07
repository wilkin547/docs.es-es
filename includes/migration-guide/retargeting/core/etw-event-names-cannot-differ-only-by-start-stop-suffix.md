---
ms.openlocfilehash: 0e25d5d9b545e5cb400cbf701fb13da572fadf10
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614677"
---
### <a name="etw-event-names-cannot-differ-only-by-a-start-or-stop-suffix"></a><span data-ttu-id="7b2d8-101">Los nombres de eventos de ETW no pueden diferir solamente en un sufijo "Start" o "Stop".</span><span class="sxs-lookup"><span data-stu-id="7b2d8-101">ETW event names cannot differ only by a "Start" or "Stop" suffix</span></span>

#### <a name="details"></a><span data-ttu-id="7b2d8-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="7b2d8-102">Details</span></span>

<span data-ttu-id="7b2d8-103">En .NET Framework 4.6 y 4.6.1, el entorno de ejecución inicia una excepción <xref:System.ArgumentException> cuando dos nombres de evento de Seguimiento de eventos para Windows (ETW) solamente difieren en un sufijo "Start" o "Stop" (como cuando un evento se denomina `LogUser` y otro `LogUserStart`).</span><span class="sxs-lookup"><span data-stu-id="7b2d8-103">In the .NET Framework 4.6 and 4.6.1, the runtime throws an <xref:System.ArgumentException> when two Event Tracing for Windows (ETW) event names differ only by a "Start" or "Stop" suffix (as when one event is named `LogUser` and another is named `LogUserStart`).</span></span> <span data-ttu-id="7b2d8-104">En este caso, el entorno en tiempo de ejecución no puede crear el origen de eventos, que no puede emitir ningún registro.</span><span class="sxs-lookup"><span data-stu-id="7b2d8-104">In this case, the runtime cannot construct the event source, which cannot emit any logging.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="7b2d8-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="7b2d8-105">Suggestion</span></span>

<span data-ttu-id="7b2d8-106">Para evitar la excepción, asegúrese de que no haya dos nombres de evento que solo difieran en un sufijo "Start" o "Stop". Este requisito se ha eliminado a partir de .NET Framework 4.6.2; el entorno de ejecución puede eliminar la ambigüedad de los nombres de evento que solo difieren en el sufijo "Start" y "Stop".</span><span class="sxs-lookup"><span data-stu-id="7b2d8-106">To prevent the exception, ensure that no two event names differ only by a "Start" or "Stop" suffix.This requirement is removed starting with the .NET Framework 4.6.2; the runtime can disambiguate event names that differ only by the "Start" and "Stop" suffix.</span></span>

| <span data-ttu-id="7b2d8-107">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="7b2d8-107">Name</span></span>    | <span data-ttu-id="7b2d8-108">Valor</span><span class="sxs-lookup"><span data-stu-id="7b2d8-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="7b2d8-109">Ámbito</span><span class="sxs-lookup"><span data-stu-id="7b2d8-109">Scope</span></span>   | <span data-ttu-id="7b2d8-110">Borde</span><span class="sxs-lookup"><span data-stu-id="7b2d8-110">Edge</span></span>        |
| <span data-ttu-id="7b2d8-111">Versión</span><span class="sxs-lookup"><span data-stu-id="7b2d8-111">Version</span></span> | <span data-ttu-id="7b2d8-112">4.6</span><span class="sxs-lookup"><span data-stu-id="7b2d8-112">4.6</span></span>         |
| <span data-ttu-id="7b2d8-113">Tipo</span><span class="sxs-lookup"><span data-stu-id="7b2d8-113">Type</span></span>    | <span data-ttu-id="7b2d8-114">Redestinación</span><span class="sxs-lookup"><span data-stu-id="7b2d8-114">Retargeting</span></span> |
