---
title: Eventos ETW en Common Language Runtime
ms.date: 03/30/2017
helpviewer_keywords:
- CLR ETW events
- ETW, common language runtime
- ETW, CLR events
ms.assetid: 5bb9b6a2-7b57-4aea-8809-32b28bc73e88
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1d059a5d4df402b309f628bf3e9393114c4cdeec
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59191398"
---
# <a name="etw-events-in-the-common-language-runtime"></a><span data-ttu-id="28f42-102">Eventos ETW en Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="28f42-102">ETW Events in the Common Language Runtime</span></span>
<span data-ttu-id="28f42-103">Common Language Runtime (CLR) proporciona información de diagnóstico del Seguimiento de eventos para Windows (ETW) útil para una gran variedad de eventos de depuración y de generación de perfiles.</span><span class="sxs-lookup"><span data-stu-id="28f42-103">The common language runtime (CLR) provides useful event tracing for Windows (ETW) diagnostic information through a large variety of debugging and profiling events.</span></span> <span data-ttu-id="28f42-104">Los eventos ETW de CLR se aprovechan del sistema de seguimiento ETW de Windows para aumentar la compatibilidad con la depuración y generación de perfiles proporcionada por Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="28f42-104">CLR ETW events leverage the Windows ETW tracing system to augment the existing profiling and debugging support provided by the common language runtime.</span></span>  
  
 <span data-ttu-id="28f42-105">Puede encontrar más información sobre ETW disponible en el artículo [Improve Debugging and Performance Tuning with ETW](https://go.microsoft.com/fwlink/?LinkID=161142) (Mejorar la depuración y el ajuste de rendimiento con ETW) en MSDN.</span><span class="sxs-lookup"><span data-stu-id="28f42-105">More information about ETW is available in the article [Improve Debugging and Performance Tuning with ETW](https://go.microsoft.com/fwlink/?LinkID=161142) on MSDN.</span></span> <span data-ttu-id="28f42-106">La información sobre Xperf se puede encontrar en la entrada [Kit de herramientas de rendimiento de Windows - Xperf](https://go.microsoft.com/fwlink/?LinkID=161144) del blog de NTDebugging.</span><span class="sxs-lookup"><span data-stu-id="28f42-106">Information about Xperf can be found in the entry [Windows Performance Toolkit - Xperf](https://go.microsoft.com/fwlink/?LinkID=161144) in the NTDebugging blog.</span></span>  
  
 <span data-ttu-id="28f42-107">Se requiere [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] o posterior para todos los eventos descritos en los temas de eventos.</span><span class="sxs-lookup"><span data-stu-id="28f42-107">The [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] or later is required for all the events described in the event topics.</span></span> <span data-ttu-id="28f42-108">El sistema operativo Windows Vista es el cliente compatible mínimo, y Windows Server 2008 es el servidor compatible mínimo.</span><span class="sxs-lookup"><span data-stu-id="28f42-108">The Windows Vista operating system is the minimum supported client, and Windows Server 2008 is the minimum supported server.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="28f42-109">En esta sección</span><span class="sxs-lookup"><span data-stu-id="28f42-109">In This Section</span></span>  
 [<span data-ttu-id="28f42-110">Controlar el registro de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="28f42-110">Controlling .NET Framework Logging</span></span>](../../../docs/framework/performance/controlling-logging.md)  
 <span data-ttu-id="28f42-111">Describe las herramientas y los comandos para capturar y ver los eventos ETW.</span><span class="sxs-lookup"><span data-stu-id="28f42-111">Describes the tools and commands for capturing and viewing ETW events.</span></span>  
  
 [<span data-ttu-id="28f42-112">Proveedores ETW de CLR</span><span class="sxs-lookup"><span data-stu-id="28f42-112">CLR ETW Providers</span></span>](../../../docs/framework/performance/clr-etw-providers.md)  
 <span data-ttu-id="28f42-113">Proporciona información sobre los proveedores de runtime y de detención; además, explica el modo de usarlos para la recopilación de datos ETW.</span><span class="sxs-lookup"><span data-stu-id="28f42-113">Provides information about the runtime and rundown providers, and how you can use them for ETW data collection.</span></span>  
  
 [<span data-ttu-id="28f42-114">Palabras clave y niveles ETW de CLR</span><span class="sxs-lookup"><span data-stu-id="28f42-114">CLR ETW Keywords and Levels</span></span>](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)  
 <span data-ttu-id="28f42-115">Describe las palabras clave para los proveedores de runtime y de detención que habilitan el filtrado de eventos por categoría.</span><span class="sxs-lookup"><span data-stu-id="28f42-115">Describes the keywords for the Runtime and Rundown providers that enable the filtering of events by category.</span></span>  
  
 [<span data-ttu-id="28f42-116">CLR ETW Events (Eventos ETW de CLR)</span><span class="sxs-lookup"><span data-stu-id="28f42-116">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)  
 <span data-ttu-id="28f42-117">Proporciona información detallada sobre eventos ETW de CLR, sus palabras clave, niveles y datos de evento.</span><span class="sxs-lookup"><span data-stu-id="28f42-117">Provides detailed information about CLR ETW events, their keywords, levels, and event data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28f42-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="28f42-118">See also</span></span>

- [<span data-ttu-id="28f42-119">Eventos ETW en .NET Framework</span><span class="sxs-lookup"><span data-stu-id="28f42-119">ETW Events in the .NET Framework</span></span>](../../../docs/framework/performance/etw-events.md)
