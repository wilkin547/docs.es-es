---
title: Resumen del tipo de seguimiento
ms.date: 03/30/2017
ms.assetid: e639410b-d1d1-479c-b78e-a4701d4e4085
ms.openlocfilehash: 8f54f71ef63338708a29fac5557c7c7e8f257f58
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2019
ms.locfileid: "70856012"
---
# <a name="trace-type-summary"></a><span data-ttu-id="1a887-102">Resumen del tipo de seguimiento</span><span class="sxs-lookup"><span data-stu-id="1a887-102">Trace Type Summary</span></span>
<span data-ttu-id="1a887-103">[Niveles de origen](https://go.microsoft.com/fwlink/?LinkID=94943) define varios niveles de seguimiento: Crítico, error, ADVERTENCIA, información y detallado, además de proporcionar una descripción de la `ActivityTracing` marca, que alterna la salida del límite de seguimiento y los eventos de transferencia de actividad.</span><span class="sxs-lookup"><span data-stu-id="1a887-103">[Source Levels](https://go.microsoft.com/fwlink/?LinkID=94943) defines various trace levels: Critical, Error, Warning, Information, and Verbose, as well as provides description of the `ActivityTracing` flag, which toggles the output of trace boundary and activity transfer events.</span></span>  
  
 <span data-ttu-id="1a887-104">También puede revisar [TraceEventType](https://go.microsoft.com/fwlink/?LinkId=95169) para ver los tipos de seguimientos que se pueden emitir <xref:System.Diagnostics>desde.</span><span class="sxs-lookup"><span data-stu-id="1a887-104">You can also review [TraceEventType](https://go.microsoft.com/fwlink/?LinkId=95169) for the types of traces which can be emitted from <xref:System.Diagnostics>.</span></span>  
  
 <span data-ttu-id="1a887-105">La tabla siguiente enumera los más importantes.</span><span class="sxs-lookup"><span data-stu-id="1a887-105">The following table lists the most important ones.</span></span>  
  
|<span data-ttu-id="1a887-106">Tipo de traza</span><span class="sxs-lookup"><span data-stu-id="1a887-106">Trace Type</span></span>|<span data-ttu-id="1a887-107">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="1a887-107">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="1a887-108">Crítico</span><span class="sxs-lookup"><span data-stu-id="1a887-108">Critical</span></span>|<span data-ttu-id="1a887-109">Error irrecuperable o bloqueo de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="1a887-109">Fatal error or application crash.</span></span>|  
|<span data-ttu-id="1a887-110">Error</span><span class="sxs-lookup"><span data-stu-id="1a887-110">Error</span></span>|<span data-ttu-id="1a887-111">Error recuperable.</span><span class="sxs-lookup"><span data-stu-id="1a887-111">Recoverable error.</span></span>|  
|<span data-ttu-id="1a887-112">Advertencia</span><span class="sxs-lookup"><span data-stu-id="1a887-112">Warning</span></span>|<span data-ttu-id="1a887-113">Mensaje informativo.</span><span class="sxs-lookup"><span data-stu-id="1a887-113">Informational message.</span></span>|  
|<span data-ttu-id="1a887-114">Información</span><span class="sxs-lookup"><span data-stu-id="1a887-114">Information</span></span>|<span data-ttu-id="1a887-115">Problema no crítico.</span><span class="sxs-lookup"><span data-stu-id="1a887-115">Non-critical problem.</span></span>|  
|<span data-ttu-id="1a887-116">Detallado</span><span class="sxs-lookup"><span data-stu-id="1a887-116">Verbose</span></span>|<span data-ttu-id="1a887-117">Traza de depuración.</span><span class="sxs-lookup"><span data-stu-id="1a887-117">Debugging trace.</span></span>|  
|<span data-ttu-id="1a887-118">Iniciar</span><span class="sxs-lookup"><span data-stu-id="1a887-118">Start</span></span>|<span data-ttu-id="1a887-119">Inicio de una unidad lógica de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="1a887-119">Starting of a logical unit of processing.</span></span>|  
|<span data-ttu-id="1a887-120">Suspender</span><span class="sxs-lookup"><span data-stu-id="1a887-120">Suspend</span></span>|<span data-ttu-id="1a887-121">Suspensión de una unidad lógica de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="1a887-121">Suspension of a logical unit of processing.</span></span>|  
|<span data-ttu-id="1a887-122">Reanudar</span><span class="sxs-lookup"><span data-stu-id="1a887-122">Resume</span></span>|<span data-ttu-id="1a887-123">Reanudación de una unidad lógica de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="1a887-123">Resumption of a logical unit of processing.</span></span>|  
|<span data-ttu-id="1a887-124">Detener</span><span class="sxs-lookup"><span data-stu-id="1a887-124">Stop</span></span>|<span data-ttu-id="1a887-125">Detención de una unidad lógica de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="1a887-125">Stopping of a logical unit of processing.</span></span>|  
|<span data-ttu-id="1a887-126">Transferir</span><span class="sxs-lookup"><span data-stu-id="1a887-126">Transfer</span></span>|<span data-ttu-id="1a887-127">Cambio de la identidad de correlación.</span><span class="sxs-lookup"><span data-stu-id="1a887-127">Changing of correlation identity.</span></span>|  
  
 <span data-ttu-id="1a887-128">Una actividad se define como una combinación de los tipos de trazas anteriores.</span><span class="sxs-lookup"><span data-stu-id="1a887-128">An activity is defined as a combination of the trace types above.</span></span>  
  
 <span data-ttu-id="1a887-129">La siguiente expresión se utiliza habitualmente para definir una actividad ideal en un ámbito local (origen de la traza),</span><span class="sxs-lookup"><span data-stu-id="1a887-129">The following is a regular expression that defines an ideal activity in a local (trace source) scope,</span></span>  
  
 `R = Start (Critical | Error | Warning | Information | Verbose | Transfer | (Transfer Suspend Transfer Resume) )* Stop`  
  
 <span data-ttu-id="1a887-130">Esto significa que una actividad debe satisfacer las condiciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="1a887-130">This means that an activity must satisfy the following conditions.</span></span>  
  
- <span data-ttu-id="1a887-131">Debe iniciarse y detenerse por trazas de inicio y detención, respectivamente</span><span class="sxs-lookup"><span data-stu-id="1a887-131">It must start and stop respectively by a Start and Stop traces</span></span>  
  
- <span data-ttu-id="1a887-132">Debe tener una traza de transferencia que preceda inmediatamente a una traza de suspensión o reanudación</span><span class="sxs-lookup"><span data-stu-id="1a887-132">It must have a Transfer trace immediately preceding a Suspend or Resume trace</span></span>  
  
- <span data-ttu-id="1a887-133">No debe presentar traza alguna entre las trazas de suspensión y reanudación, en caso de que éstas existan</span><span class="sxs-lookup"><span data-stu-id="1a887-133">It must not have any traces between the Suspend and Resume traces if such traces exist</span></span>  
  
- <span data-ttu-id="1a887-134">Puede tener cuantas trazas crítico/error/advertencia/información/detalles/transferencia, siempre y cuando se cumplan las condiciones anteriores</span><span class="sxs-lookup"><span data-stu-id="1a887-134">It can have any and as many of critical/Error/Warning/Information/Verbose/Transfer traces as long as the previous conditions are observed</span></span>  
  
 <span data-ttu-id="1a887-135">La siguiente expresión se utiliza habitualmente para definir una actividad ideal en el ámbito global,</span><span class="sxs-lookup"><span data-stu-id="1a887-135">The following is a regular expression that defines an ideal activity in the global scope,</span></span>  
  
`R+`  
  
 <span data-ttu-id="1a887-136">en la que R es la expresión regular para una actividad en el ámbito local.</span><span class="sxs-lookup"><span data-stu-id="1a887-136">with R being the regular expression for an activity in the local scope.</span></span> <span data-ttu-id="1a887-137">Esto se traduce en,</span><span class="sxs-lookup"><span data-stu-id="1a887-137">This translates to,</span></span>  
  
`[R+ = Start ( Critical | Error | Warning | Information | Verbose | Transfer | (Transfer Suspend Transfer Resume) )* Stop]+`
