---
title: Resumen del tipo de seguimiento
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e639410b-d1d1-479c-b78e-a4701d4e4085
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fe4222ac124174341a28035c955a2a9bef4a167c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="trace-type-summary"></a><span data-ttu-id="8086a-102">Resumen del tipo de seguimiento</span><span class="sxs-lookup"><span data-stu-id="8086a-102">Trace Type Summary</span></span>
<span data-ttu-id="8086a-103">[Niveles de origen](http://go.microsoft.com/fwlink/?LinkID=94943) define distintos niveles de seguimiento: crítico, Error, advertencia, información y detallado, así, proporciona una descripción de la `ActivityTracing` marca, que alterna el resultado de seguimiento de eventos de transferencia de límite y la actividad.</span><span class="sxs-lookup"><span data-stu-id="8086a-103">[Source Levels](http://go.microsoft.com/fwlink/?LinkID=94943) defines various trace levels: Critical, Error, Warning, Information, and Verbose, as well as provides description of the `ActivityTracing` flag, which toggles the output of trace boundary and activity transfer events.</span></span>  
  
 <span data-ttu-id="8086a-104">También puede revisar [TraceEventType](http://go.microsoft.com/fwlink/?LinkId=95169) para los tipos de seguimientos que se pueden emitir desde <xref:System.Diagnostics>.</span><span class="sxs-lookup"><span data-stu-id="8086a-104">You can also review [TraceEventType](http://go.microsoft.com/fwlink/?LinkId=95169) for the types of traces which can be emitted from <xref:System.Diagnostics>.</span></span>  
  
 <span data-ttu-id="8086a-105">La tabla siguiente enumera los más importantes.</span><span class="sxs-lookup"><span data-stu-id="8086a-105">The following table lists the most important ones.</span></span>  
  
|<span data-ttu-id="8086a-106">Tipo de traza</span><span class="sxs-lookup"><span data-stu-id="8086a-106">Trace Type</span></span>|<span data-ttu-id="8086a-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="8086a-107">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="8086a-108">Crítico</span><span class="sxs-lookup"><span data-stu-id="8086a-108">Critical</span></span>|<span data-ttu-id="8086a-109">Error irrecuperable o bloqueo de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="8086a-109">Fatal error or application crash.</span></span>|  
|<span data-ttu-id="8086a-110">Error</span><span class="sxs-lookup"><span data-stu-id="8086a-110">Error</span></span>|<span data-ttu-id="8086a-111">Error recuperable.</span><span class="sxs-lookup"><span data-stu-id="8086a-111">Recoverable error.</span></span>|  
|<span data-ttu-id="8086a-112">Advertencia</span><span class="sxs-lookup"><span data-stu-id="8086a-112">Warning</span></span>|<span data-ttu-id="8086a-113">Mensaje informativo.</span><span class="sxs-lookup"><span data-stu-id="8086a-113">Informational message.</span></span>|  
|<span data-ttu-id="8086a-114">Información</span><span class="sxs-lookup"><span data-stu-id="8086a-114">Information</span></span>|<span data-ttu-id="8086a-115">Problema no crítico.</span><span class="sxs-lookup"><span data-stu-id="8086a-115">Non-critical problem.</span></span>|  
|<span data-ttu-id="8086a-116">Detallado</span><span class="sxs-lookup"><span data-stu-id="8086a-116">Verbose</span></span>|<span data-ttu-id="8086a-117">Traza de depuración.</span><span class="sxs-lookup"><span data-stu-id="8086a-117">Debugging trace.</span></span>|  
|<span data-ttu-id="8086a-118">Iniciar</span><span class="sxs-lookup"><span data-stu-id="8086a-118">Start</span></span>|<span data-ttu-id="8086a-119">Inicio de una unidad lógica de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="8086a-119">Starting of a logical unit of processing.</span></span>|  
|<span data-ttu-id="8086a-120">Suspender</span><span class="sxs-lookup"><span data-stu-id="8086a-120">Suspend</span></span>|<span data-ttu-id="8086a-121">Suspensión de una unidad lógica de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="8086a-121">Suspension of a logical unit of processing.</span></span>|  
|<span data-ttu-id="8086a-122">Reanudar</span><span class="sxs-lookup"><span data-stu-id="8086a-122">Resume</span></span>|<span data-ttu-id="8086a-123">Reanudación de una unidad lógica de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="8086a-123">Resumption of a logical unit of processing.</span></span>|  
|<span data-ttu-id="8086a-124">Detener</span><span class="sxs-lookup"><span data-stu-id="8086a-124">Stop</span></span>|<span data-ttu-id="8086a-125">Detención de una unidad lógica de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="8086a-125">Stopping of a logical unit of processing.</span></span>|  
|<span data-ttu-id="8086a-126">Transferir</span><span class="sxs-lookup"><span data-stu-id="8086a-126">Transfer</span></span>|<span data-ttu-id="8086a-127">Cambio de la identidad de correlación.</span><span class="sxs-lookup"><span data-stu-id="8086a-127">Changing of correlation identity.</span></span>|  
  
 <span data-ttu-id="8086a-128">Una actividad se define como una combinación de los tipos de trazas anteriores.</span><span class="sxs-lookup"><span data-stu-id="8086a-128">An activity is defined as a combination of the trace types above.</span></span>  
  
 <span data-ttu-id="8086a-129">La siguiente expresión se utiliza habitualmente para definir una actividad ideal en un ámbito local (origen de la traza),</span><span class="sxs-lookup"><span data-stu-id="8086a-129">The following is a regular expression that defines an ideal activity in a local (trace source) scope,</span></span>  
  
 `R = Start (Critical | Error | Warning | Information | Verbose | Transfer | (Transfer Suspend Transfer Resume) )* Stop`  
  
 <span data-ttu-id="8086a-130">Esto significa que una actividad debe satisfacer las condiciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="8086a-130">This means that an activity must satisfy the following conditions.</span></span>  
  
-   <span data-ttu-id="8086a-131">Debe iniciarse y detenerse por trazas de inicio y detención, respectivamente</span><span class="sxs-lookup"><span data-stu-id="8086a-131">It must start and stop respectively by a Start and Stop traces</span></span>  
  
-   <span data-ttu-id="8086a-132">Debe tener una traza de transferencia que preceda inmediatamente a una traza de suspensión o reanudación</span><span class="sxs-lookup"><span data-stu-id="8086a-132">It must have a Transfer trace immediately preceding a Suspend or Resume trace</span></span>  
  
-   <span data-ttu-id="8086a-133">No debe presentar traza alguna entre las trazas de suspensión y reanudación, en caso de que éstas existan</span><span class="sxs-lookup"><span data-stu-id="8086a-133">It must not have any traces between the Suspend and Resume traces if such traces exist</span></span>  
  
-   <span data-ttu-id="8086a-134">Puede tener cuantas trazas crítico/error/advertencia/información/detalles/transferencia, siempre y cuando se cumplan las condiciones anteriores</span><span class="sxs-lookup"><span data-stu-id="8086a-134">It can have any and as many of critical/Error/Warning/Information/Verbose/Transfer traces as long as the previous conditions are observed</span></span>  
  
 <span data-ttu-id="8086a-135">La siguiente expresión se utiliza habitualmente para definir una actividad ideal en el ámbito global,</span><span class="sxs-lookup"><span data-stu-id="8086a-135">The following is a regular expression that defines an ideal activity in the global scope,</span></span>  
  
```  
R+   
```  
  
 <span data-ttu-id="8086a-136">en la que R es la expresión regular para una actividad en el ámbito local.</span><span class="sxs-lookup"><span data-stu-id="8086a-136">with R being the regular expression for an activity in the local scope.</span></span> <span data-ttu-id="8086a-137">Esto se traduce en,</span><span class="sxs-lookup"><span data-stu-id="8086a-137">This translates to,</span></span>  
  
```  
[R+ = Start ( Critical | Error | Warning | Information | Verbose | Transfer | (Transfer Suspend Transfer Resume) )* Stop]+  
```
