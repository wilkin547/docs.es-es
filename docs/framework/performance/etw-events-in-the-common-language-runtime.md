---
title: Eventos ETW en Common Language Runtime
description: Lea un resumen y vea los vínculos relativos a los eventos de seguimiento de eventos para Windows (ETW) en el Common Language Runtime (CLR).
ms.date: 03/30/2017
helpviewer_keywords:
- CLR ETW events
- ETW, common language runtime
- ETW, CLR events
ms.assetid: 5bb9b6a2-7b57-4aea-8809-32b28bc73e88
ms.openlocfilehash: ab9cb7c53171ebf1dd0d48dec133464fe4042043
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96263638"
---
# <a name="etw-events-in-the-common-language-runtime"></a><span data-ttu-id="fd99b-103">Eventos ETW en Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="fd99b-103">ETW Events in the Common Language Runtime</span></span>

<span data-ttu-id="fd99b-104">Common Language Runtime (CLR) proporciona información de diagnóstico del Seguimiento de eventos para Windows (ETW) útil para una gran variedad de eventos de depuración y de generación de perfiles.</span><span class="sxs-lookup"><span data-stu-id="fd99b-104">The common language runtime (CLR) provides useful event tracing for Windows (ETW) diagnostic information through a large variety of debugging and profiling events.</span></span> <span data-ttu-id="fd99b-105">Los eventos ETW de CLR se aprovechan del sistema de seguimiento ETW de Windows para aumentar la compatibilidad con la depuración y generación de perfiles proporcionada por Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="fd99b-105">CLR ETW events leverage the Windows ETW tracing system to augment the existing profiling and debugging support provided by the common language runtime.</span></span>  
  
 <span data-ttu-id="fd99b-106">Puede encontrar más información sobre ETW en el artículo [mejorar la optimización del rendimiento y la depuración con ETW](/archive/msdn-magazine/2007/april/event-tracing-improve-debugging-and-performance-tuning-with-etw) .</span><span class="sxs-lookup"><span data-stu-id="fd99b-106">More information about ETW is available in the [Improve Debugging and Performance Tuning with ETW](/archive/msdn-magazine/2007/april/event-tracing-improve-debugging-and-performance-tuning-with-etw) article.</span></span> <span data-ttu-id="fd99b-107">La información sobre Xperf se puede encontrar en la entrada [Kit de herramientas de rendimiento de Windows - Xperf](/archive/blogs/ntdebugging/windows-performance-toolkit-xperf) del blog de NTDebugging.</span><span class="sxs-lookup"><span data-stu-id="fd99b-107">Information about Xperf can be found in the entry [Windows Performance Toolkit - Xperf](/archive/blogs/ntdebugging/windows-performance-toolkit-xperf) in the NTDebugging blog.</span></span>  
  
 <span data-ttu-id="fd99b-108">Se necesita el .NET Framework 4 o posterior para todos los eventos descritos en los temas de eventos.</span><span class="sxs-lookup"><span data-stu-id="fd99b-108">The .NET Framework 4 or later is required for all the events described in the event topics.</span></span> <span data-ttu-id="fd99b-109">El sistema operativo Windows Vista es el cliente compatible mínimo, y Windows Server 2008 es el servidor compatible mínimo.</span><span class="sxs-lookup"><span data-stu-id="fd99b-109">The Windows Vista operating system is the minimum supported client, and Windows Server 2008 is the minimum supported server.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="fd99b-110">En esta sección</span><span class="sxs-lookup"><span data-stu-id="fd99b-110">In This Section</span></span>  

 [<span data-ttu-id="fd99b-111">Controlar el registro de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="fd99b-111">Controlling .NET Framework Logging</span></span>](controlling-logging.md)  
 <span data-ttu-id="fd99b-112">Describe las herramientas y los comandos para capturar y ver los eventos ETW.</span><span class="sxs-lookup"><span data-stu-id="fd99b-112">Describes the tools and commands for capturing and viewing ETW events.</span></span>  
  
 [<span data-ttu-id="fd99b-113">Proveedores ETW de CLR</span><span class="sxs-lookup"><span data-stu-id="fd99b-113">CLR ETW Providers</span></span>](clr-etw-providers.md)  
 <span data-ttu-id="fd99b-114">Proporciona información sobre los proveedores de runtime y de detención; además, explica el modo de usarlos para la recopilación de datos ETW.</span><span class="sxs-lookup"><span data-stu-id="fd99b-114">Provides information about the runtime and rundown providers, and how you can use them for ETW data collection.</span></span>  
  
 [<span data-ttu-id="fd99b-115">Palabras clave y niveles ETW de CLR</span><span class="sxs-lookup"><span data-stu-id="fd99b-115">CLR ETW Keywords and Levels</span></span>](clr-etw-keywords-and-levels.md)  
 <span data-ttu-id="fd99b-116">Describe las palabras clave para los proveedores de runtime y de detención que habilitan el filtrado de eventos por categoría.</span><span class="sxs-lookup"><span data-stu-id="fd99b-116">Describes the keywords for the Runtime and Rundown providers that enable the filtering of events by category.</span></span>  
  
 [<span data-ttu-id="fd99b-117">CLR ETW Events (Eventos ETW de CLR)</span><span class="sxs-lookup"><span data-stu-id="fd99b-117">CLR ETW Events</span></span>](clr-etw-events.md)  
 <span data-ttu-id="fd99b-118">Proporciona información detallada sobre eventos ETW de CLR, sus palabras clave, niveles y datos de evento.</span><span class="sxs-lookup"><span data-stu-id="fd99b-118">Provides detailed information about CLR ETW events, their keywords, levels, and event data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd99b-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="fd99b-119">See also</span></span>

- [<span data-ttu-id="fd99b-120">Eventos de ETW en .NET Framework</span><span class="sxs-lookup"><span data-stu-id="fd99b-120">ETW Events in the .NET Framework</span></span>](etw-events.md)
