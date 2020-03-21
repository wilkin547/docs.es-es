---
title: Resumen del tipo de seguimiento
ms.date: 03/30/2017
ms.assetid: e639410b-d1d1-479c-b78e-a4701d4e4085
ms.openlocfilehash: 8ed6dceb19caa52f928f285064c60337e3f15a87
ms.sourcegitcommit: 515469828d0f040e01bde01df6b8e4eb43630b06
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2020
ms.locfileid: "78674838"
---
# <a name="trace-type-summary"></a><span data-ttu-id="9346a-102">Resumen del tipo de seguimiento</span><span class="sxs-lookup"><span data-stu-id="9346a-102">Trace Type Summary</span></span>
<span data-ttu-id="9346a-103">[Niveles](xref:System.Diagnostics.SourceLevels) de origen define varios niveles de seguimiento: Crítico, Error, Advertencia, Información `ActivityTracing` y Detallado, así como proporciona una descripción de la marca, que alterna la salida de los eventos de transferencia de actividad y límite de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="9346a-103">[Source Levels](xref:System.Diagnostics.SourceLevels) defines various trace levels: Critical, Error, Warning, Information, and Verbose, as well as provides a description of the `ActivityTracing` flag, which toggles the output of trace boundary and activity transfer events.</span></span>  
  
 <span data-ttu-id="9346a-104">También puede <xref:System.Diagnostics.TraceEventType> revisar los tipos de seguimientos <xref:System.Diagnostics>que se pueden emitir desde .</span><span class="sxs-lookup"><span data-stu-id="9346a-104">You can also review <xref:System.Diagnostics.TraceEventType> for the types of traces which can be emitted from <xref:System.Diagnostics>.</span></span>  
  
 <span data-ttu-id="9346a-105">La tabla siguiente enumera los más importantes.</span><span class="sxs-lookup"><span data-stu-id="9346a-105">The following table lists the most important ones.</span></span>  
  
|<span data-ttu-id="9346a-106">Tipo de traza</span><span class="sxs-lookup"><span data-stu-id="9346a-106">Trace Type</span></span>|<span data-ttu-id="9346a-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="9346a-107">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="9346a-108">Crítico</span><span class="sxs-lookup"><span data-stu-id="9346a-108">Critical</span></span>|<span data-ttu-id="9346a-109">Error irrecuperable o bloqueo de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="9346a-109">Fatal error or application crash.</span></span>|  
|<span data-ttu-id="9346a-110">Error</span><span class="sxs-lookup"><span data-stu-id="9346a-110">Error</span></span>|<span data-ttu-id="9346a-111">Error recuperable.</span><span class="sxs-lookup"><span data-stu-id="9346a-111">Recoverable error.</span></span>|  
|<span data-ttu-id="9346a-112">Advertencia</span><span class="sxs-lookup"><span data-stu-id="9346a-112">Warning</span></span>|<span data-ttu-id="9346a-113">Mensaje informativo.</span><span class="sxs-lookup"><span data-stu-id="9346a-113">Informational message.</span></span>|  
|<span data-ttu-id="9346a-114">Information</span><span class="sxs-lookup"><span data-stu-id="9346a-114">Information</span></span>|<span data-ttu-id="9346a-115">Problema no crítico.</span><span class="sxs-lookup"><span data-stu-id="9346a-115">Non-critical problem.</span></span>|  
|<span data-ttu-id="9346a-116">Verbose</span><span class="sxs-lookup"><span data-stu-id="9346a-116">Verbose</span></span>|<span data-ttu-id="9346a-117">Traza de depuración.</span><span class="sxs-lookup"><span data-stu-id="9346a-117">Debugging trace.</span></span>|  
|<span data-ttu-id="9346a-118">Start</span><span class="sxs-lookup"><span data-stu-id="9346a-118">Start</span></span>|<span data-ttu-id="9346a-119">Inicio de una unidad lógica de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="9346a-119">Starting of a logical unit of processing.</span></span>|  
|<span data-ttu-id="9346a-120">Suspender</span><span class="sxs-lookup"><span data-stu-id="9346a-120">Suspend</span></span>|<span data-ttu-id="9346a-121">Suspensión de una unidad lógica de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="9346a-121">Suspension of a logical unit of processing.</span></span>|  
|<span data-ttu-id="9346a-122">Reanudación</span><span class="sxs-lookup"><span data-stu-id="9346a-122">Resume</span></span>|<span data-ttu-id="9346a-123">Reanudación de una unidad lógica de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="9346a-123">Resumption of a logical unit of processing.</span></span>|  
|<span data-ttu-id="9346a-124">Stop</span><span class="sxs-lookup"><span data-stu-id="9346a-124">Stop</span></span>|<span data-ttu-id="9346a-125">Detención de una unidad lógica de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="9346a-125">Stopping of a logical unit of processing.</span></span>|  
|<span data-ttu-id="9346a-126">Transferir</span><span class="sxs-lookup"><span data-stu-id="9346a-126">Transfer</span></span>|<span data-ttu-id="9346a-127">Cambio de la identidad de correlación.</span><span class="sxs-lookup"><span data-stu-id="9346a-127">Changing of correlation identity.</span></span>|  
  
 <span data-ttu-id="9346a-128">Una actividad se define como una combinación de los tipos de trazas anteriores.</span><span class="sxs-lookup"><span data-stu-id="9346a-128">An activity is defined as a combination of the trace types above.</span></span>  
  
 <span data-ttu-id="9346a-129">La siguiente expresión se utiliza habitualmente para definir una actividad ideal en un ámbito local (origen de la traza),</span><span class="sxs-lookup"><span data-stu-id="9346a-129">The following is a regular expression that defines an ideal activity in a local (trace source) scope,</span></span>  
  
 `R = Start (Critical | Error | Warning | Information | Verbose | Transfer | (Transfer Suspend Transfer Resume) )* Stop`  
  
 <span data-ttu-id="9346a-130">Esto significa que una actividad debe satisfacer las condiciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="9346a-130">This means that an activity must satisfy the following conditions.</span></span>  
  
- <span data-ttu-id="9346a-131">Debe iniciarse y detenerse por trazas de inicio y detención, respectivamente</span><span class="sxs-lookup"><span data-stu-id="9346a-131">It must start and stop respectively by a Start and Stop traces</span></span>  
  
- <span data-ttu-id="9346a-132">Debe tener una traza de transferencia que preceda inmediatamente a una traza de suspensión o reanudación</span><span class="sxs-lookup"><span data-stu-id="9346a-132">It must have a Transfer trace immediately preceding a Suspend or Resume trace</span></span>  
  
- <span data-ttu-id="9346a-133">No debe presentar traza alguna entre las trazas de suspensión y reanudación, en caso de que éstas existan</span><span class="sxs-lookup"><span data-stu-id="9346a-133">It must not have any traces between the Suspend and Resume traces if such traces exist</span></span>  
  
- <span data-ttu-id="9346a-134">Puede tener cuantas trazas crítico/error/advertencia/información/detalles/transferencia, siempre y cuando se cumplan las condiciones anteriores</span><span class="sxs-lookup"><span data-stu-id="9346a-134">It can have any and as many of critical/Error/Warning/Information/Verbose/Transfer traces as long as the previous conditions are observed</span></span>  
  
 <span data-ttu-id="9346a-135">La siguiente expresión se utiliza habitualmente para definir una actividad ideal en el ámbito global,</span><span class="sxs-lookup"><span data-stu-id="9346a-135">The following is a regular expression that defines an ideal activity in the global scope,</span></span>  
  
`R+`  
  
 <span data-ttu-id="9346a-136">en la que R es la expresión regular para una actividad en el ámbito local.</span><span class="sxs-lookup"><span data-stu-id="9346a-136">with R being the regular expression for an activity in the local scope.</span></span> <span data-ttu-id="9346a-137">Esto se traduce en,</span><span class="sxs-lookup"><span data-stu-id="9346a-137">This translates to,</span></span>  
  
`[R+ = Start ( Critical | Error | Warning | Information | Verbose | Transfer | (Transfer Suspend Transfer Resume) )* Stop]+`
