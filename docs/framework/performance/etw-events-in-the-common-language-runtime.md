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
ms.openlocfilehash: 46ad58813da5b71b884ad55f796db3522b2f1920
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2019
ms.locfileid: "71046612"
---
# <a name="etw-events-in-the-common-language-runtime"></a><span data-ttu-id="ad5c4-102">Eventos ETW en Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="ad5c4-102">ETW Events in the Common Language Runtime</span></span>
<span data-ttu-id="ad5c4-103">Common Language Runtime (CLR) proporciona información de diagnóstico del Seguimiento de eventos para Windows (ETW) útil para una gran variedad de eventos de depuración y de generación de perfiles.</span><span class="sxs-lookup"><span data-stu-id="ad5c4-103">The common language runtime (CLR) provides useful event tracing for Windows (ETW) diagnostic information through a large variety of debugging and profiling events.</span></span> <span data-ttu-id="ad5c4-104">Los eventos ETW de CLR se aprovechan del sistema de seguimiento ETW de Windows para aumentar la compatibilidad con la depuración y generación de perfiles proporcionada por Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="ad5c4-104">CLR ETW events leverage the Windows ETW tracing system to augment the existing profiling and debugging support provided by the common language runtime.</span></span>  
  
 <span data-ttu-id="ad5c4-105">Puede encontrar más información sobre ETW disponible en el artículo [Improve Debugging and Performance Tuning with ETW](https://go.microsoft.com/fwlink/?LinkID=161142) (Mejorar la depuración y el ajuste de rendimiento con ETW) en MSDN.</span><span class="sxs-lookup"><span data-stu-id="ad5c4-105">More information about ETW is available in the article [Improve Debugging and Performance Tuning with ETW](https://go.microsoft.com/fwlink/?LinkID=161142) on MSDN.</span></span> <span data-ttu-id="ad5c4-106">La información sobre Xperf se puede encontrar en la entrada [Kit de herramientas de rendimiento de Windows - Xperf](https://go.microsoft.com/fwlink/?LinkID=161144) del blog de NTDebugging.</span><span class="sxs-lookup"><span data-stu-id="ad5c4-106">Information about Xperf can be found in the entry [Windows Performance Toolkit - Xperf](https://go.microsoft.com/fwlink/?LinkID=161144) in the NTDebugging blog.</span></span>  
  
 <span data-ttu-id="ad5c4-107">Se necesita el .NET Framework 4 o posterior para todos los eventos descritos en los temas de eventos.</span><span class="sxs-lookup"><span data-stu-id="ad5c4-107">The .NET Framework 4 or later is required for all the events described in the event topics.</span></span> <span data-ttu-id="ad5c4-108">El sistema operativo Windows Vista es el cliente compatible mínimo, y Windows Server 2008 es el servidor compatible mínimo.</span><span class="sxs-lookup"><span data-stu-id="ad5c4-108">The Windows Vista operating system is the minimum supported client, and Windows Server 2008 is the minimum supported server.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ad5c4-109">En esta sección</span><span class="sxs-lookup"><span data-stu-id="ad5c4-109">In This Section</span></span>  
 [<span data-ttu-id="ad5c4-110">Controlar el registro de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="ad5c4-110">Controlling .NET Framework Logging</span></span>](controlling-logging.md)  
 <span data-ttu-id="ad5c4-111">Describe las herramientas y los comandos para capturar y ver los eventos ETW.</span><span class="sxs-lookup"><span data-stu-id="ad5c4-111">Describes the tools and commands for capturing and viewing ETW events.</span></span>  
  
 [<span data-ttu-id="ad5c4-112">Proveedores ETW de CLR</span><span class="sxs-lookup"><span data-stu-id="ad5c4-112">CLR ETW Providers</span></span>](clr-etw-providers.md)  
 <span data-ttu-id="ad5c4-113">Proporciona información sobre los proveedores de runtime y de detención; además, explica el modo de usarlos para la recopilación de datos ETW.</span><span class="sxs-lookup"><span data-stu-id="ad5c4-113">Provides information about the runtime and rundown providers, and how you can use them for ETW data collection.</span></span>  
  
 [<span data-ttu-id="ad5c4-114">Palabras clave y niveles ETW de CLR</span><span class="sxs-lookup"><span data-stu-id="ad5c4-114">CLR ETW Keywords and Levels</span></span>](clr-etw-keywords-and-levels.md)  
 <span data-ttu-id="ad5c4-115">Describe las palabras clave para los proveedores de runtime y de detención que habilitan el filtrado de eventos por categoría.</span><span class="sxs-lookup"><span data-stu-id="ad5c4-115">Describes the keywords for the Runtime and Rundown providers that enable the filtering of events by category.</span></span>  
  
 [<span data-ttu-id="ad5c4-116">CLR ETW Events (Eventos ETW de CLR)</span><span class="sxs-lookup"><span data-stu-id="ad5c4-116">CLR ETW Events</span></span>](clr-etw-events.md)  
 <span data-ttu-id="ad5c4-117">Proporciona información detallada sobre eventos ETW de CLR, sus palabras clave, niveles y datos de evento.</span><span class="sxs-lookup"><span data-stu-id="ad5c4-117">Provides detailed information about CLR ETW events, their keywords, levels, and event data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad5c4-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="ad5c4-118">See also</span></span>

- [<span data-ttu-id="ad5c4-119">Eventos ETW en .NET Framework</span><span class="sxs-lookup"><span data-stu-id="ad5c4-119">ETW Events in the .NET Framework</span></span>](etw-events.md)
