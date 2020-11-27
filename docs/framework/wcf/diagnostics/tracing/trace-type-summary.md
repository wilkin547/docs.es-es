---
title: Resumen del tipo de seguimiento
ms.date: 03/30/2017
ms.assetid: e639410b-d1d1-479c-b78e-a4701d4e4085
ms.openlocfilehash: e8d222d6f093f5db3bd620194bfde7edd4b998a8
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96259250"
---
# <a name="trace-type-summary"></a><span data-ttu-id="fbdd3-102">Resumen del tipo de seguimiento</span><span class="sxs-lookup"><span data-stu-id="fbdd3-102">Trace Type Summary</span></span>

<span data-ttu-id="fbdd3-103">[Niveles de origen](xref:System.Diagnostics.SourceLevels) define varios niveles de seguimiento: crítico, error, ADVERTENCIA, información y detallado, así como una descripción de la `ActivityTracing` marca, que alterna la salida del límite de seguimiento y los eventos de transferencia de actividad.</span><span class="sxs-lookup"><span data-stu-id="fbdd3-103">[Source Levels](xref:System.Diagnostics.SourceLevels) defines various trace levels: Critical, Error, Warning, Information, and Verbose, as well as provides a description of the `ActivityTracing` flag, which toggles the output of trace boundary and activity transfer events.</span></span>  
  
 <span data-ttu-id="fbdd3-104">También puede revisar <xref:System.Diagnostics.TraceEventType> los tipos de seguimientos que se pueden emitir desde <xref:System.Diagnostics> .</span><span class="sxs-lookup"><span data-stu-id="fbdd3-104">You can also review <xref:System.Diagnostics.TraceEventType> for the types of traces which can be emitted from <xref:System.Diagnostics>.</span></span>  
  
 <span data-ttu-id="fbdd3-105">La tabla siguiente enumera los más importantes.</span><span class="sxs-lookup"><span data-stu-id="fbdd3-105">The following table lists the most important ones.</span></span>  
  
|<span data-ttu-id="fbdd3-106">Tipo de traza</span><span class="sxs-lookup"><span data-stu-id="fbdd3-106">Trace Type</span></span>|<span data-ttu-id="fbdd3-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="fbdd3-107">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="fbdd3-108">Crítico</span><span class="sxs-lookup"><span data-stu-id="fbdd3-108">Critical</span></span>|<span data-ttu-id="fbdd3-109">Error irrecuperable o bloqueo de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="fbdd3-109">Fatal error or application crash.</span></span>|  
|<span data-ttu-id="fbdd3-110">Error</span><span class="sxs-lookup"><span data-stu-id="fbdd3-110">Error</span></span>|<span data-ttu-id="fbdd3-111">Error recuperable.</span><span class="sxs-lookup"><span data-stu-id="fbdd3-111">Recoverable error.</span></span>|  
|<span data-ttu-id="fbdd3-112">Advertencia</span><span class="sxs-lookup"><span data-stu-id="fbdd3-112">Warning</span></span>|<span data-ttu-id="fbdd3-113">Mensaje informativo.</span><span class="sxs-lookup"><span data-stu-id="fbdd3-113">Informational message.</span></span>|  
|<span data-ttu-id="fbdd3-114">Información</span><span class="sxs-lookup"><span data-stu-id="fbdd3-114">Information</span></span>|<span data-ttu-id="fbdd3-115">Problema no crítico.</span><span class="sxs-lookup"><span data-stu-id="fbdd3-115">Non-critical problem.</span></span>|  
|<span data-ttu-id="fbdd3-116">Verbose</span><span class="sxs-lookup"><span data-stu-id="fbdd3-116">Verbose</span></span>|<span data-ttu-id="fbdd3-117">Traza de depuración.</span><span class="sxs-lookup"><span data-stu-id="fbdd3-117">Debugging trace.</span></span>|  
|<span data-ttu-id="fbdd3-118">Inicio</span><span class="sxs-lookup"><span data-stu-id="fbdd3-118">Start</span></span>|<span data-ttu-id="fbdd3-119">Inicio de una unidad lógica de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="fbdd3-119">Starting of a logical unit of processing.</span></span>|  
|<span data-ttu-id="fbdd3-120">Suspender</span><span class="sxs-lookup"><span data-stu-id="fbdd3-120">Suspend</span></span>|<span data-ttu-id="fbdd3-121">Suspensión de una unidad lógica de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="fbdd3-121">Suspension of a logical unit of processing.</span></span>|  
|<span data-ttu-id="fbdd3-122">Reanudar</span><span class="sxs-lookup"><span data-stu-id="fbdd3-122">Resume</span></span>|<span data-ttu-id="fbdd3-123">Reanudación de una unidad lógica de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="fbdd3-123">Resumption of a logical unit of processing.</span></span>|  
|<span data-ttu-id="fbdd3-124">Stop</span><span class="sxs-lookup"><span data-stu-id="fbdd3-124">Stop</span></span>|<span data-ttu-id="fbdd3-125">Detención de una unidad lógica de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="fbdd3-125">Stopping of a logical unit of processing.</span></span>|  
|<span data-ttu-id="fbdd3-126">Transferencia</span><span class="sxs-lookup"><span data-stu-id="fbdd3-126">Transfer</span></span>|<span data-ttu-id="fbdd3-127">Cambio de la identidad de correlación.</span><span class="sxs-lookup"><span data-stu-id="fbdd3-127">Changing of correlation identity.</span></span>|  
  
 <span data-ttu-id="fbdd3-128">Una actividad se define como una combinación de los tipos de trazas anteriores.</span><span class="sxs-lookup"><span data-stu-id="fbdd3-128">An activity is defined as a combination of the trace types above.</span></span>  
  
 <span data-ttu-id="fbdd3-129">La siguiente expresión se utiliza habitualmente para definir una actividad ideal en un ámbito local (origen de la traza),</span><span class="sxs-lookup"><span data-stu-id="fbdd3-129">The following is a regular expression that defines an ideal activity in a local (trace source) scope,</span></span>  
  
 `R = Start (Critical | Error | Warning | Information | Verbose | Transfer | (Transfer Suspend Transfer Resume) )* Stop`  
  
 <span data-ttu-id="fbdd3-130">Esto significa que una actividad debe satisfacer las condiciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="fbdd3-130">This means that an activity must satisfy the following conditions.</span></span>  
  
- <span data-ttu-id="fbdd3-131">Debe iniciarse y detenerse por trazas de inicio y detención, respectivamente</span><span class="sxs-lookup"><span data-stu-id="fbdd3-131">It must start and stop respectively by a Start and Stop traces</span></span>  
  
- <span data-ttu-id="fbdd3-132">Debe tener una traza de transferencia que preceda inmediatamente a una traza de suspensión o reanudación</span><span class="sxs-lookup"><span data-stu-id="fbdd3-132">It must have a Transfer trace immediately preceding a Suspend or Resume trace</span></span>  
  
- <span data-ttu-id="fbdd3-133">No debe presentar traza alguna entre las trazas de suspensión y reanudación, en caso de que éstas existan</span><span class="sxs-lookup"><span data-stu-id="fbdd3-133">It must not have any traces between the Suspend and Resume traces if such traces exist</span></span>  
  
- <span data-ttu-id="fbdd3-134">Puede tener cuantas trazas crítico/error/advertencia/información/detalles/transferencia, siempre y cuando se cumplan las condiciones anteriores</span><span class="sxs-lookup"><span data-stu-id="fbdd3-134">It can have any and as many of critical/Error/Warning/Information/Verbose/Transfer traces as long as the previous conditions are observed</span></span>  
  
 <span data-ttu-id="fbdd3-135">La siguiente expresión se utiliza habitualmente para definir una actividad ideal en el ámbito global,</span><span class="sxs-lookup"><span data-stu-id="fbdd3-135">The following is a regular expression that defines an ideal activity in the global scope,</span></span>  
  
`R+`  
  
 <span data-ttu-id="fbdd3-136">en la que R es la expresión regular para una actividad en el ámbito local.</span><span class="sxs-lookup"><span data-stu-id="fbdd3-136">with R being the regular expression for an activity in the local scope.</span></span> <span data-ttu-id="fbdd3-137">Esto se traduce en,</span><span class="sxs-lookup"><span data-stu-id="fbdd3-137">This translates to,</span></span>  
  
`[R+ = Start ( Critical | Error | Warning | Information | Verbose | Transfer | (Transfer Suspend Transfer Resume) )* Stop]+`
