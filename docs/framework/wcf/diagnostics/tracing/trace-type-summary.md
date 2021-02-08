---
description: 'Más información acerca de: Resumen del tipo de seguimiento'
title: Resumen del tipo de seguimiento
ms.date: 03/30/2017
ms.assetid: e639410b-d1d1-479c-b78e-a4701d4e4085
ms.openlocfilehash: ebfe9de16766494a6aebe0a8d2501954855dc4df
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99803222"
---
# <a name="trace-type-summary"></a><span data-ttu-id="e0a84-103">Resumen del tipo de seguimiento</span><span class="sxs-lookup"><span data-stu-id="e0a84-103">Trace Type Summary</span></span>

<span data-ttu-id="e0a84-104">[Niveles de origen](xref:System.Diagnostics.SourceLevels) define varios niveles de seguimiento: crítico, error, ADVERTENCIA, información y detallado, así como una descripción de la `ActivityTracing` marca, que alterna la salida del límite de seguimiento y los eventos de transferencia de actividad.</span><span class="sxs-lookup"><span data-stu-id="e0a84-104">[Source Levels](xref:System.Diagnostics.SourceLevels) defines various trace levels: Critical, Error, Warning, Information, and Verbose, as well as provides a description of the `ActivityTracing` flag, which toggles the output of trace boundary and activity transfer events.</span></span>  
  
 <span data-ttu-id="e0a84-105">También puede revisar <xref:System.Diagnostics.TraceEventType> los tipos de seguimientos que se pueden emitir desde <xref:System.Diagnostics> .</span><span class="sxs-lookup"><span data-stu-id="e0a84-105">You can also review <xref:System.Diagnostics.TraceEventType> for the types of traces which can be emitted from <xref:System.Diagnostics>.</span></span>  
  
 <span data-ttu-id="e0a84-106">La tabla siguiente enumera los más importantes.</span><span class="sxs-lookup"><span data-stu-id="e0a84-106">The following table lists the most important ones.</span></span>  
  
|<span data-ttu-id="e0a84-107">Tipo de traza</span><span class="sxs-lookup"><span data-stu-id="e0a84-107">Trace Type</span></span>|<span data-ttu-id="e0a84-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="e0a84-108">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="e0a84-109">Crítico</span><span class="sxs-lookup"><span data-stu-id="e0a84-109">Critical</span></span>|<span data-ttu-id="e0a84-110">Error irrecuperable o bloqueo de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e0a84-110">Fatal error or application crash.</span></span>|  
|<span data-ttu-id="e0a84-111">Error</span><span class="sxs-lookup"><span data-stu-id="e0a84-111">Error</span></span>|<span data-ttu-id="e0a84-112">Error recuperable.</span><span class="sxs-lookup"><span data-stu-id="e0a84-112">Recoverable error.</span></span>|  
|<span data-ttu-id="e0a84-113">Advertencia</span><span class="sxs-lookup"><span data-stu-id="e0a84-113">Warning</span></span>|<span data-ttu-id="e0a84-114">Mensaje informativo.</span><span class="sxs-lookup"><span data-stu-id="e0a84-114">Informational message.</span></span>|  
|<span data-ttu-id="e0a84-115">Información</span><span class="sxs-lookup"><span data-stu-id="e0a84-115">Information</span></span>|<span data-ttu-id="e0a84-116">Problema no crítico.</span><span class="sxs-lookup"><span data-stu-id="e0a84-116">Non-critical problem.</span></span>|  
|<span data-ttu-id="e0a84-117">Verbose</span><span class="sxs-lookup"><span data-stu-id="e0a84-117">Verbose</span></span>|<span data-ttu-id="e0a84-118">Traza de depuración.</span><span class="sxs-lookup"><span data-stu-id="e0a84-118">Debugging trace.</span></span>|  
|<span data-ttu-id="e0a84-119">Start</span><span class="sxs-lookup"><span data-stu-id="e0a84-119">Start</span></span>|<span data-ttu-id="e0a84-120">Inicio de una unidad lógica de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="e0a84-120">Starting of a logical unit of processing.</span></span>|  
|<span data-ttu-id="e0a84-121">Suspender</span><span class="sxs-lookup"><span data-stu-id="e0a84-121">Suspend</span></span>|<span data-ttu-id="e0a84-122">Suspensión de una unidad lógica de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="e0a84-122">Suspension of a logical unit of processing.</span></span>|  
|<span data-ttu-id="e0a84-123">Reanudar</span><span class="sxs-lookup"><span data-stu-id="e0a84-123">Resume</span></span>|<span data-ttu-id="e0a84-124">Reanudación de una unidad lógica de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="e0a84-124">Resumption of a logical unit of processing.</span></span>|  
|<span data-ttu-id="e0a84-125">Stop</span><span class="sxs-lookup"><span data-stu-id="e0a84-125">Stop</span></span>|<span data-ttu-id="e0a84-126">Detención de una unidad lógica de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="e0a84-126">Stopping of a logical unit of processing.</span></span>|  
|<span data-ttu-id="e0a84-127">Transferencia</span><span class="sxs-lookup"><span data-stu-id="e0a84-127">Transfer</span></span>|<span data-ttu-id="e0a84-128">Cambio de la identidad de correlación.</span><span class="sxs-lookup"><span data-stu-id="e0a84-128">Changing of correlation identity.</span></span>|  
  
 <span data-ttu-id="e0a84-129">Una actividad se define como una combinación de los tipos de trazas anteriores.</span><span class="sxs-lookup"><span data-stu-id="e0a84-129">An activity is defined as a combination of the trace types above.</span></span>  
  
 <span data-ttu-id="e0a84-130">La siguiente expresión se utiliza habitualmente para definir una actividad ideal en un ámbito local (origen de la traza),</span><span class="sxs-lookup"><span data-stu-id="e0a84-130">The following is a regular expression that defines an ideal activity in a local (trace source) scope,</span></span>  
  
 `R = Start (Critical | Error | Warning | Information | Verbose | Transfer | (Transfer Suspend Transfer Resume) )* Stop`  
  
 <span data-ttu-id="e0a84-131">Esto significa que una actividad debe satisfacer las condiciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="e0a84-131">This means that an activity must satisfy the following conditions.</span></span>  
  
- <span data-ttu-id="e0a84-132">Debe iniciarse y detenerse por trazas de inicio y detención, respectivamente</span><span class="sxs-lookup"><span data-stu-id="e0a84-132">It must start and stop respectively by a Start and Stop traces</span></span>  
  
- <span data-ttu-id="e0a84-133">Debe tener una traza de transferencia que preceda inmediatamente a una traza de suspensión o reanudación</span><span class="sxs-lookup"><span data-stu-id="e0a84-133">It must have a Transfer trace immediately preceding a Suspend or Resume trace</span></span>  
  
- <span data-ttu-id="e0a84-134">No debe presentar traza alguna entre las trazas de suspensión y reanudación, en caso de que éstas existan</span><span class="sxs-lookup"><span data-stu-id="e0a84-134">It must not have any traces between the Suspend and Resume traces if such traces exist</span></span>  
  
- <span data-ttu-id="e0a84-135">Puede tener cuantas trazas crítico/error/advertencia/información/detalles/transferencia, siempre y cuando se cumplan las condiciones anteriores</span><span class="sxs-lookup"><span data-stu-id="e0a84-135">It can have any and as many of critical/Error/Warning/Information/Verbose/Transfer traces as long as the previous conditions are observed</span></span>  
  
 <span data-ttu-id="e0a84-136">La siguiente expresión se utiliza habitualmente para definir una actividad ideal en el ámbito global,</span><span class="sxs-lookup"><span data-stu-id="e0a84-136">The following is a regular expression that defines an ideal activity in the global scope,</span></span>  
  
`R+`  
  
 <span data-ttu-id="e0a84-137">en la que R es la expresión regular para una actividad en el ámbito local.</span><span class="sxs-lookup"><span data-stu-id="e0a84-137">with R being the regular expression for an activity in the local scope.</span></span> <span data-ttu-id="e0a84-138">Esto se traduce en,</span><span class="sxs-lookup"><span data-stu-id="e0a84-138">This translates to,</span></span>  
  
`[R+ = Start ( Critical | Error | Warning | Information | Verbose | Transfer | (Transfer Suspend Transfer Resume) )* Stop]+`
