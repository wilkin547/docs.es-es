---
title: Eventos ETW en Common Language Runtime
ms.date: 03/30/2017
helpviewer_keywords:
- CLR ETW events
- ETW, common language runtime
- ETW, CLR events
ms.assetid: 5bb9b6a2-7b57-4aea-8809-32b28bc73e88
ms.openlocfilehash: 49d1141540fb00ab7ef462da5af84f02e6d9fc4d
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937855"
---
# <a name="etw-events-in-the-common-language-runtime"></a><span data-ttu-id="3f7a6-102">Eventos ETW en Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="3f7a6-102">ETW Events in the Common Language Runtime</span></span>
<span data-ttu-id="3f7a6-103">Common Language Runtime (CLR) proporciona información de diagnóstico del Seguimiento de eventos para Windows (ETW) útil para una gran variedad de eventos de depuración y de generación de perfiles.</span><span class="sxs-lookup"><span data-stu-id="3f7a6-103">The common language runtime (CLR) provides useful event tracing for Windows (ETW) diagnostic information through a large variety of debugging and profiling events.</span></span> <span data-ttu-id="3f7a6-104">Los eventos ETW de CLR se aprovechan del sistema de seguimiento ETW de Windows para aumentar la compatibilidad con la depuración y generación de perfiles proporcionada por Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="3f7a6-104">CLR ETW events leverage the Windows ETW tracing system to augment the existing profiling and debugging support provided by the common language runtime.</span></span>  
  
 <span data-ttu-id="3f7a6-105">Puede encontrar más información sobre ETW en el artículo [mejorar la optimización del rendimiento y la depuración con ETW](https://docs.microsoft.com/archive/msdn-magazine/2007/april/event-tracing-improve-debugging-and-performance-tuning-with-etw) .</span><span class="sxs-lookup"><span data-stu-id="3f7a6-105">More information about ETW is available in the [Improve Debugging and Performance Tuning with ETW](https://docs.microsoft.com/archive/msdn-magazine/2007/april/event-tracing-improve-debugging-and-performance-tuning-with-etw) article.</span></span> <span data-ttu-id="3f7a6-106">La información sobre Xperf se puede encontrar en la entrada [Kit de herramientas de rendimiento de Windows - Xperf](https://docs.microsoft.com/archive/blogs/ntdebugging/windows-performance-toolkit-xperf) del blog de NTDebugging.</span><span class="sxs-lookup"><span data-stu-id="3f7a6-106">Information about Xperf can be found in the entry [Windows Performance Toolkit - Xperf](https://docs.microsoft.com/archive/blogs/ntdebugging/windows-performance-toolkit-xperf) in the NTDebugging blog.</span></span>  
  
 <span data-ttu-id="3f7a6-107">Se necesita el .NET Framework 4 o posterior para todos los eventos descritos en los temas de eventos.</span><span class="sxs-lookup"><span data-stu-id="3f7a6-107">The .NET Framework 4 or later is required for all the events described in the event topics.</span></span> <span data-ttu-id="3f7a6-108">El sistema operativo Windows Vista es el cliente compatible mínimo, y Windows Server 2008 es el servidor compatible mínimo.</span><span class="sxs-lookup"><span data-stu-id="3f7a6-108">The Windows Vista operating system is the minimum supported client, and Windows Server 2008 is the minimum supported server.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3f7a6-109">Esta sección</span><span class="sxs-lookup"><span data-stu-id="3f7a6-109">In This Section</span></span>  
 [<span data-ttu-id="3f7a6-110">Controlar el registro de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="3f7a6-110">Controlling .NET Framework Logging</span></span>](controlling-logging.md)  
 <span data-ttu-id="3f7a6-111">Describe las herramientas y los comandos para capturar y ver los eventos ETW.</span><span class="sxs-lookup"><span data-stu-id="3f7a6-111">Describes the tools and commands for capturing and viewing ETW events.</span></span>  
  
 [<span data-ttu-id="3f7a6-112">Proveedores ETW de CLR</span><span class="sxs-lookup"><span data-stu-id="3f7a6-112">CLR ETW Providers</span></span>](clr-etw-providers.md)  
 <span data-ttu-id="3f7a6-113">Proporciona información sobre los proveedores de runtime y de detención; además, explica el modo de usarlos para la recopilación de datos ETW.</span><span class="sxs-lookup"><span data-stu-id="3f7a6-113">Provides information about the runtime and rundown providers, and how you can use them for ETW data collection.</span></span>  
  
 [<span data-ttu-id="3f7a6-114">Palabras clave y niveles ETW de CLR</span><span class="sxs-lookup"><span data-stu-id="3f7a6-114">CLR ETW Keywords and Levels</span></span>](clr-etw-keywords-and-levels.md)  
 <span data-ttu-id="3f7a6-115">Describe las palabras clave para los proveedores de runtime y de detención que habilitan el filtrado de eventos por categoría.</span><span class="sxs-lookup"><span data-stu-id="3f7a6-115">Describes the keywords for the Runtime and Rundown providers that enable the filtering of events by category.</span></span>  
  
 [<span data-ttu-id="3f7a6-116">CLR ETW Events (Eventos ETW de CLR)</span><span class="sxs-lookup"><span data-stu-id="3f7a6-116">CLR ETW Events</span></span>](clr-etw-events.md)  
 <span data-ttu-id="3f7a6-117">Proporciona información detallada sobre eventos ETW de CLR, sus palabras clave, niveles y datos de evento.</span><span class="sxs-lookup"><span data-stu-id="3f7a6-117">Provides detailed information about CLR ETW events, their keywords, levels, and event data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f7a6-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="3f7a6-118">See also</span></span>

- [<span data-ttu-id="3f7a6-119">Eventos ETW en .NET Framework</span><span class="sxs-lookup"><span data-stu-id="3f7a6-119">ETW Events in the .NET Framework</span></span>](etw-events.md)
