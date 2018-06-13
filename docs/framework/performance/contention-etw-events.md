---
title: Eventos ETW de contención
ms.date: 03/30/2017
helpviewer_keywords:
- contention events [.NET Framework]
- ETW, contention events (CLR)
ms.assetid: 6933e753-2f2a-425b-ae84-42138c957d76
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3487b67ea49cecfd0da2b5b3f993ea54d562145d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33397525"
---
# <a name="contention-etw-events"></a><span data-ttu-id="a3bf3-102">Eventos ETW de contención</span><span class="sxs-lookup"><span data-stu-id="a3bf3-102">Contention ETW Events</span></span>
<span data-ttu-id="a3bf3-103">Los eventos de contención se generan cuando el tiempo de ejecución usa contención de bloqueos <xref:System.Threading.Monitor?displayProperty=nameWithType> o nativos.</span><span class="sxs-lookup"><span data-stu-id="a3bf3-103">Contention events are raised whenever there is contention for <xref:System.Threading.Monitor?displayProperty=nameWithType> locks or native locks used by the runtime.</span></span> <span data-ttu-id="a3bf3-104">La contención se produce cuando un subproceso espera un bloqueo mientras otro posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="a3bf3-104">Contention occurs when a thread is waiting for a lock while another thread possesses the lock.</span></span>  
  
 <span data-ttu-id="a3bf3-105">En la tabla siguiente se muestra la palabra clave bajo la que se generan los eventos de contención y el nivel de los eventos.</span><span class="sxs-lookup"><span data-stu-id="a3bf3-105">The following table shows the keyword under which contention events are raised, and the level of the events.</span></span> <span data-ttu-id="a3bf3-106">(Para obtener más información, vea [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)).</span><span class="sxs-lookup"><span data-stu-id="a3bf3-106">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="a3bf3-107">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="a3bf3-107">Keyword for raising the event</span></span>|<span data-ttu-id="a3bf3-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="a3bf3-108">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="a3bf3-109">`ContentionKeyword` (0x4000)</span><span class="sxs-lookup"><span data-stu-id="a3bf3-109">`ContentionKeyword` (0x4000)</span></span>|<span data-ttu-id="a3bf3-110">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="a3bf3-110">Informational (4)</span></span>|  
  
 <span data-ttu-id="a3bf3-111">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="a3bf3-111">The following table shows event information.</span></span>  
  
|<span data-ttu-id="a3bf3-112">evento</span><span class="sxs-lookup"><span data-stu-id="a3bf3-112">Event</span></span>|<span data-ttu-id="a3bf3-113">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="a3bf3-113">Event ID</span></span>|<span data-ttu-id="a3bf3-114">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="a3bf3-114">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ContentionStart_V1`|<span data-ttu-id="a3bf3-115">81</span><span class="sxs-lookup"><span data-stu-id="a3bf3-115">81</span></span>|<span data-ttu-id="a3bf3-116">Se inicia la contención.</span><span class="sxs-lookup"><span data-stu-id="a3bf3-116">Contention starts.</span></span> <span data-ttu-id="a3bf3-117">Este evento no incluye la cantidad de tiempo de giro antes de que un subproceso comience a esperar para adquirir un bloqueo; solo se genera cuando el subproceso espera para adquirir un bloqueo.</span><span class="sxs-lookup"><span data-stu-id="a3bf3-117">This event does not include the amount of spinning time before a thread waits to acquire a lock; it is raised only when the thread waits to acquire a lock.</span></span>|  
|`ContentionStop`|<span data-ttu-id="a3bf3-118">81</span><span class="sxs-lookup"><span data-stu-id="a3bf3-118">81</span></span>|<span data-ttu-id="a3bf3-119">Finaliza la contención.</span><span class="sxs-lookup"><span data-stu-id="a3bf3-119">Contention ends.</span></span>|  
  
 <span data-ttu-id="a3bf3-120">En la siguiente tabla se muestran los datos del evento.</span><span class="sxs-lookup"><span data-stu-id="a3bf3-120">The following table shows event data.</span></span>  
  
|<span data-ttu-id="a3bf3-121">Nombre de campo</span><span class="sxs-lookup"><span data-stu-id="a3bf3-121">Field name</span></span>|<span data-ttu-id="a3bf3-122">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="a3bf3-122">Data type</span></span>|<span data-ttu-id="a3bf3-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="a3bf3-123">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="a3bf3-124">Marcas</span><span class="sxs-lookup"><span data-stu-id="a3bf3-124">Flags</span></span>|<span data-ttu-id="a3bf3-125">win:UInt8</span><span class="sxs-lookup"><span data-stu-id="a3bf3-125">win:UInt8</span></span>|<span data-ttu-id="a3bf3-126">0 para administrado; 1 para nativo.</span><span class="sxs-lookup"><span data-stu-id="a3bf3-126">0 for managed; 1 for native.</span></span>|  
|<span data-ttu-id="a3bf3-127">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="a3bf3-127">ClrInstanceID</span></span>|<span data-ttu-id="a3bf3-128">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="a3bf3-128">win:UInt16</span></span>|<span data-ttu-id="a3bf3-129">Identificador único para la instancia de CLR.</span><span class="sxs-lookup"><span data-stu-id="a3bf3-129">Unique ID for the instance of CLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a3bf3-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="a3bf3-130">See Also</span></span>  
 [<span data-ttu-id="a3bf3-131">CLR ETW Events (Eventos ETW de CLR)</span><span class="sxs-lookup"><span data-stu-id="a3bf3-131">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
