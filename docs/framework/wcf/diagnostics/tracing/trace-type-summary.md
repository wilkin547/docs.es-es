---
title: Resumen del tipo de seguimiento
ms.date: 03/30/2017
ms.assetid: e639410b-d1d1-479c-b78e-a4701d4e4085
ms.openlocfilehash: 73777df2b58b14947c416ce409bcb42d439499ec
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2018
ms.locfileid: "43403848"
---
# <a name="trace-type-summary"></a><span data-ttu-id="5cfed-102">Resumen del tipo de seguimiento</span><span class="sxs-lookup"><span data-stu-id="5cfed-102">Trace Type Summary</span></span>
<span data-ttu-id="5cfed-103">[Niveles de origen](https://go.microsoft.com/fwlink/?LinkID=94943) definen los distintos niveles de seguimiento: crítico, Error, advertencia, información y detallado, así, proporciona una descripción de la `ActivityTracing` marca, que alterna el resultado de seguimiento de eventos de transferencia de actividad y el límite.</span><span class="sxs-lookup"><span data-stu-id="5cfed-103">[Source Levels](https://go.microsoft.com/fwlink/?LinkID=94943) defines various trace levels: Critical, Error, Warning, Information, and Verbose, as well as provides description of the `ActivityTracing` flag, which toggles the output of trace boundary and activity transfer events.</span></span>  
  
 <span data-ttu-id="5cfed-104">También puede revisar [TraceEventType](https://go.microsoft.com/fwlink/?LinkId=95169) para los tipos de seguimiento que se puede emitir desde <xref:System.Diagnostics>.</span><span class="sxs-lookup"><span data-stu-id="5cfed-104">You can also review [TraceEventType](https://go.microsoft.com/fwlink/?LinkId=95169) for the types of traces which can be emitted from <xref:System.Diagnostics>.</span></span>  
  
 <span data-ttu-id="5cfed-105">La tabla siguiente enumera los más importantes.</span><span class="sxs-lookup"><span data-stu-id="5cfed-105">The following table lists the most important ones.</span></span>  
  
|<span data-ttu-id="5cfed-106">Tipo de traza</span><span class="sxs-lookup"><span data-stu-id="5cfed-106">Trace Type</span></span>|<span data-ttu-id="5cfed-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="5cfed-107">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="5cfed-108">Crítico</span><span class="sxs-lookup"><span data-stu-id="5cfed-108">Critical</span></span>|<span data-ttu-id="5cfed-109">Error irrecuperable o bloqueo de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="5cfed-109">Fatal error or application crash.</span></span>|  
|<span data-ttu-id="5cfed-110">Error</span><span class="sxs-lookup"><span data-stu-id="5cfed-110">Error</span></span>|<span data-ttu-id="5cfed-111">Error recuperable.</span><span class="sxs-lookup"><span data-stu-id="5cfed-111">Recoverable error.</span></span>|  
|<span data-ttu-id="5cfed-112">Advertencia</span><span class="sxs-lookup"><span data-stu-id="5cfed-112">Warning</span></span>|<span data-ttu-id="5cfed-113">Mensaje informativo.</span><span class="sxs-lookup"><span data-stu-id="5cfed-113">Informational message.</span></span>|  
|<span data-ttu-id="5cfed-114">Información</span><span class="sxs-lookup"><span data-stu-id="5cfed-114">Information</span></span>|<span data-ttu-id="5cfed-115">Problema no crítico.</span><span class="sxs-lookup"><span data-stu-id="5cfed-115">Non-critical problem.</span></span>|  
|<span data-ttu-id="5cfed-116">Detallado</span><span class="sxs-lookup"><span data-stu-id="5cfed-116">Verbose</span></span>|<span data-ttu-id="5cfed-117">Traza de depuración.</span><span class="sxs-lookup"><span data-stu-id="5cfed-117">Debugging trace.</span></span>|  
|<span data-ttu-id="5cfed-118">Iniciar</span><span class="sxs-lookup"><span data-stu-id="5cfed-118">Start</span></span>|<span data-ttu-id="5cfed-119">Inicio de una unidad lógica de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="5cfed-119">Starting of a logical unit of processing.</span></span>|  
|<span data-ttu-id="5cfed-120">Suspender</span><span class="sxs-lookup"><span data-stu-id="5cfed-120">Suspend</span></span>|<span data-ttu-id="5cfed-121">Suspensión de una unidad lógica de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="5cfed-121">Suspension of a logical unit of processing.</span></span>|  
|<span data-ttu-id="5cfed-122">Reanudar</span><span class="sxs-lookup"><span data-stu-id="5cfed-122">Resume</span></span>|<span data-ttu-id="5cfed-123">Reanudación de una unidad lógica de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="5cfed-123">Resumption of a logical unit of processing.</span></span>|  
|<span data-ttu-id="5cfed-124">Detener</span><span class="sxs-lookup"><span data-stu-id="5cfed-124">Stop</span></span>|<span data-ttu-id="5cfed-125">Detención de una unidad lógica de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="5cfed-125">Stopping of a logical unit of processing.</span></span>|  
|<span data-ttu-id="5cfed-126">Transferir</span><span class="sxs-lookup"><span data-stu-id="5cfed-126">Transfer</span></span>|<span data-ttu-id="5cfed-127">Cambio de la identidad de correlación.</span><span class="sxs-lookup"><span data-stu-id="5cfed-127">Changing of correlation identity.</span></span>|  
  
 <span data-ttu-id="5cfed-128">Una actividad se define como una combinación de los tipos de trazas anteriores.</span><span class="sxs-lookup"><span data-stu-id="5cfed-128">An activity is defined as a combination of the trace types above.</span></span>  
  
 <span data-ttu-id="5cfed-129">La siguiente expresión se utiliza habitualmente para definir una actividad ideal en un ámbito local (origen de la traza),</span><span class="sxs-lookup"><span data-stu-id="5cfed-129">The following is a regular expression that defines an ideal activity in a local (trace source) scope,</span></span>  
  
 `R = Start (Critical | Error | Warning | Information | Verbose | Transfer | (Transfer Suspend Transfer Resume) )* Stop`  
  
 <span data-ttu-id="5cfed-130">Esto significa que una actividad debe satisfacer las condiciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="5cfed-130">This means that an activity must satisfy the following conditions.</span></span>  
  
-   <span data-ttu-id="5cfed-131">Debe iniciarse y detenerse por trazas de inicio y detención, respectivamente</span><span class="sxs-lookup"><span data-stu-id="5cfed-131">It must start and stop respectively by a Start and Stop traces</span></span>  
  
-   <span data-ttu-id="5cfed-132">Debe tener una traza de transferencia que preceda inmediatamente a una traza de suspensión o reanudación</span><span class="sxs-lookup"><span data-stu-id="5cfed-132">It must have a Transfer trace immediately preceding a Suspend or Resume trace</span></span>  
  
-   <span data-ttu-id="5cfed-133">No debe presentar traza alguna entre las trazas de suspensión y reanudación, en caso de que éstas existan</span><span class="sxs-lookup"><span data-stu-id="5cfed-133">It must not have any traces between the Suspend and Resume traces if such traces exist</span></span>  
  
-   <span data-ttu-id="5cfed-134">Puede tener cuantas trazas crítico/error/advertencia/información/detalles/transferencia, siempre y cuando se cumplan las condiciones anteriores</span><span class="sxs-lookup"><span data-stu-id="5cfed-134">It can have any and as many of critical/Error/Warning/Information/Verbose/Transfer traces as long as the previous conditions are observed</span></span>  
  
 <span data-ttu-id="5cfed-135">La siguiente expresión se utiliza habitualmente para definir una actividad ideal en el ámbito global,</span><span class="sxs-lookup"><span data-stu-id="5cfed-135">The following is a regular expression that defines an ideal activity in the global scope,</span></span>  
  
```  
R+   
```  
  
 <span data-ttu-id="5cfed-136">en la que R es la expresión regular para una actividad en el ámbito local.</span><span class="sxs-lookup"><span data-stu-id="5cfed-136">with R being the regular expression for an activity in the local scope.</span></span> <span data-ttu-id="5cfed-137">Esto se traduce en,</span><span class="sxs-lookup"><span data-stu-id="5cfed-137">This translates to,</span></span>  
  
```  
[R+ = Start ( Critical | Error | Warning | Information | Verbose | Transfer | (Transfer Suspend Transfer Resume) )* Stop]+  
```
