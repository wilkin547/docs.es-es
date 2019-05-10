---
title: Resumen del tipo de seguimiento
ms.date: 03/30/2017
ms.assetid: e639410b-d1d1-479c-b78e-a4701d4e4085
ms.openlocfilehash: 44446b58510e58758934a5eb964efc8643854879
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64647188"
---
# <a name="trace-type-summary"></a><span data-ttu-id="dd815-102">Resumen del tipo de seguimiento</span><span class="sxs-lookup"><span data-stu-id="dd815-102">Trace Type Summary</span></span>
<span data-ttu-id="dd815-103">[Niveles de origen](https://go.microsoft.com/fwlink/?LinkID=94943) definen los distintos niveles de seguimiento: Crítico, Error, advertencia, información y detallado, así, proporciona una descripción de la `ActivityTracing` marca, que alterna el resultado de seguimiento de eventos de transferencia de actividad y el límite.</span><span class="sxs-lookup"><span data-stu-id="dd815-103">[Source Levels](https://go.microsoft.com/fwlink/?LinkID=94943) defines various trace levels: Critical, Error, Warning, Information, and Verbose, as well as provides description of the `ActivityTracing` flag, which toggles the output of trace boundary and activity transfer events.</span></span>  
  
 <span data-ttu-id="dd815-104">También puede revisar [TraceEventType](https://go.microsoft.com/fwlink/?LinkId=95169) para los tipos de seguimiento que se puede emitir desde <xref:System.Diagnostics>.</span><span class="sxs-lookup"><span data-stu-id="dd815-104">You can also review [TraceEventType](https://go.microsoft.com/fwlink/?LinkId=95169) for the types of traces which can be emitted from <xref:System.Diagnostics>.</span></span>  
  
 <span data-ttu-id="dd815-105">La tabla siguiente enumera los más importantes.</span><span class="sxs-lookup"><span data-stu-id="dd815-105">The following table lists the most important ones.</span></span>  
  
|<span data-ttu-id="dd815-106">Tipo de traza</span><span class="sxs-lookup"><span data-stu-id="dd815-106">Trace Type</span></span>|<span data-ttu-id="dd815-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="dd815-107">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="dd815-108">Crítico</span><span class="sxs-lookup"><span data-stu-id="dd815-108">Critical</span></span>|<span data-ttu-id="dd815-109">Error irrecuperable o bloqueo de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="dd815-109">Fatal error or application crash.</span></span>|  
|<span data-ttu-id="dd815-110">Error</span><span class="sxs-lookup"><span data-stu-id="dd815-110">Error</span></span>|<span data-ttu-id="dd815-111">Error recuperable.</span><span class="sxs-lookup"><span data-stu-id="dd815-111">Recoverable error.</span></span>|  
|<span data-ttu-id="dd815-112">Advertencia</span><span class="sxs-lookup"><span data-stu-id="dd815-112">Warning</span></span>|<span data-ttu-id="dd815-113">Mensaje informativo.</span><span class="sxs-lookup"><span data-stu-id="dd815-113">Informational message.</span></span>|  
|<span data-ttu-id="dd815-114">Información</span><span class="sxs-lookup"><span data-stu-id="dd815-114">Information</span></span>|<span data-ttu-id="dd815-115">Problema no crítico.</span><span class="sxs-lookup"><span data-stu-id="dd815-115">Non-critical problem.</span></span>|  
|<span data-ttu-id="dd815-116">Detallado</span><span class="sxs-lookup"><span data-stu-id="dd815-116">Verbose</span></span>|<span data-ttu-id="dd815-117">Traza de depuración.</span><span class="sxs-lookup"><span data-stu-id="dd815-117">Debugging trace.</span></span>|  
|<span data-ttu-id="dd815-118">Iniciar</span><span class="sxs-lookup"><span data-stu-id="dd815-118">Start</span></span>|<span data-ttu-id="dd815-119">Inicio de una unidad lógica de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="dd815-119">Starting of a logical unit of processing.</span></span>|  
|<span data-ttu-id="dd815-120">Suspender</span><span class="sxs-lookup"><span data-stu-id="dd815-120">Suspend</span></span>|<span data-ttu-id="dd815-121">Suspensión de una unidad lógica de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="dd815-121">Suspension of a logical unit of processing.</span></span>|  
|<span data-ttu-id="dd815-122">Reanudar</span><span class="sxs-lookup"><span data-stu-id="dd815-122">Resume</span></span>|<span data-ttu-id="dd815-123">Reanudación de una unidad lógica de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="dd815-123">Resumption of a logical unit of processing.</span></span>|  
|<span data-ttu-id="dd815-124">Detener</span><span class="sxs-lookup"><span data-stu-id="dd815-124">Stop</span></span>|<span data-ttu-id="dd815-125">Detención de una unidad lógica de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="dd815-125">Stopping of a logical unit of processing.</span></span>|  
|<span data-ttu-id="dd815-126">Transferir</span><span class="sxs-lookup"><span data-stu-id="dd815-126">Transfer</span></span>|<span data-ttu-id="dd815-127">Cambio de la identidad de correlación.</span><span class="sxs-lookup"><span data-stu-id="dd815-127">Changing of correlation identity.</span></span>|  
  
 <span data-ttu-id="dd815-128">Una actividad se define como una combinación de los tipos de trazas anteriores.</span><span class="sxs-lookup"><span data-stu-id="dd815-128">An activity is defined as a combination of the trace types above.</span></span>  
  
 <span data-ttu-id="dd815-129">La siguiente expresión se utiliza habitualmente para definir una actividad ideal en un ámbito local (origen de la traza),</span><span class="sxs-lookup"><span data-stu-id="dd815-129">The following is a regular expression that defines an ideal activity in a local (trace source) scope,</span></span>  
  
 `R = Start (Critical | Error | Warning | Information | Verbose | Transfer | (Transfer Suspend Transfer Resume) )* Stop`  
  
 <span data-ttu-id="dd815-130">Esto significa que una actividad debe satisfacer las condiciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="dd815-130">This means that an activity must satisfy the following conditions.</span></span>  
  
- <span data-ttu-id="dd815-131">Debe iniciarse y detenerse por trazas de inicio y detención, respectivamente</span><span class="sxs-lookup"><span data-stu-id="dd815-131">It must start and stop respectively by a Start and Stop traces</span></span>  
  
- <span data-ttu-id="dd815-132">Debe tener una traza de transferencia que preceda inmediatamente a una traza de suspensión o reanudación</span><span class="sxs-lookup"><span data-stu-id="dd815-132">It must have a Transfer trace immediately preceding a Suspend or Resume trace</span></span>  
  
- <span data-ttu-id="dd815-133">No debe presentar traza alguna entre las trazas de suspensión y reanudación, en caso de que éstas existan</span><span class="sxs-lookup"><span data-stu-id="dd815-133">It must not have any traces between the Suspend and Resume traces if such traces exist</span></span>  
  
- <span data-ttu-id="dd815-134">Puede tener cuantas trazas crítico/error/advertencia/información/detalles/transferencia, siempre y cuando se cumplan las condiciones anteriores</span><span class="sxs-lookup"><span data-stu-id="dd815-134">It can have any and as many of critical/Error/Warning/Information/Verbose/Transfer traces as long as the previous conditions are observed</span></span>  
  
 <span data-ttu-id="dd815-135">La siguiente expresión se utiliza habitualmente para definir una actividad ideal en el ámbito global,</span><span class="sxs-lookup"><span data-stu-id="dd815-135">The following is a regular expression that defines an ideal activity in the global scope,</span></span>  
  
```  
R+   
```  
  
 <span data-ttu-id="dd815-136">en la que R es la expresión regular para una actividad en el ámbito local.</span><span class="sxs-lookup"><span data-stu-id="dd815-136">with R being the regular expression for an activity in the local scope.</span></span> <span data-ttu-id="dd815-137">Esto se traduce en,</span><span class="sxs-lookup"><span data-stu-id="dd815-137">This translates to,</span></span>  
  
```  
[R+ = Start ( Critical | Error | Warning | Information | Verbose | Transfer | (Transfer Suspend Transfer Resume) )* Stop]+  
```
