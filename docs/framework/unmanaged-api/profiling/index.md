---
title: Generación de perfiles (Referencia de la API no administrada)
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- profiling [.NET Framework], using the unmanaged API
- native API reference [.NET Framework], profiling
- unmanaged API reference [.NET Framework], profiling
ms.assetid: 14c68e84-657e-49c2-aa8b-4978dbaf4454
caps.latest.revision: 20
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5583a9b81d81acfca80368ca54d5f97899daa1d8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="profiling-unmanaged-api-reference"></a><span data-ttu-id="e1fe7-102">Generación de perfiles (Referencia de la API no administrada)</span><span class="sxs-lookup"><span data-stu-id="e1fe7-102">Profiling (Unmanaged API Reference)</span></span>
<span data-ttu-id="e1fe7-103">La API de generación de perfiles permite a un generador de perfiles supervisar la ejecución de un programa por common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="e1fe7-103">The profiling API enables a profiler to monitor a program's execution by the common language runtime (CLR).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e1fe7-104">En esta sección</span><span class="sxs-lookup"><span data-stu-id="e1fe7-104">In This Section</span></span>  
 [<span data-ttu-id="e1fe7-105">Información general sobre la generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="e1fe7-105">Profiling Overview</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-overview.md)  
 <span data-ttu-id="e1fe7-106">Describe los servicios e interfaces que proporciona CLR para admitir la generación de perfiles en el entorno de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e1fe7-106">Describes the services and interfaces that the CLR provides to support profiling in the .NET Framework environment.</span></span>  
  
 [<span data-ttu-id="e1fe7-107">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="e1fe7-107">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 <span data-ttu-id="e1fe7-108">Describe las interfaces no administradas que utiliza la API de generación de perfiles.</span><span class="sxs-lookup"><span data-stu-id="e1fe7-108">Describes the unmanaged interfaces that the profiling API uses.</span></span>  
  
 [<span data-ttu-id="e1fe7-109">Configuración de un entorno de generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="e1fe7-109">Setting Up a Profiling Environment</span></span>](../../../../docs/framework/unmanaged-api/profiling/setting-up-a-profiling-environment.md)  
 <span data-ttu-id="e1fe7-110">Describe los pasos que debe seguir para generar perfiles de una aplicación de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e1fe7-110">Describes the steps you must take to profile a .NET Framework application.</span></span>  
  
 [<span data-ttu-id="e1fe7-111">Aplicaciones de la Tienda Windows y generador de perfiles CLR</span><span class="sxs-lookup"><span data-stu-id="e1fe7-111">CLR Profilers and Windows Store Apps</span></span>](../../../../docs/framework/unmanaged-api/profiling/clr-profilers-and-windows-store-apps.md)  
 <span data-ttu-id="e1fe7-112">Describe cómo migrar las herramientas de diagnóstico que utilizan la API de generación de perfiles de CLR para que funcione correctamente con aplicaciones de la tienda de Windows.</span><span class="sxs-lookup"><span data-stu-id="e1fe7-112">Discusses how to port diagnostic tools that consume the CLR Profiling API to work successfully with Windows Store apps.</span></span>  
  
 [<span data-ttu-id="e1fe7-113">CORPROF_E_UNSUPPORTED_CALL_SEQUENCE (HRESULT)</span><span class="sxs-lookup"><span data-stu-id="e1fe7-113">CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT</span></span>](../../../../docs/framework/unmanaged-api/profiling/corprof-e-unsupported-call-sequence-hresult.md)  
 <span data-ttu-id="e1fe7-114">Documenta las condiciones en las que una llamada al método devuelve el `CORPROF_E_UNSUPPORTED_CALL_SEQUENCE` HRESULT.</span><span class="sxs-lookup"><span data-stu-id="e1fe7-114">Documents the conditions under which a method call returns the `CORPROF_E_UNSUPPORTED_CALL_SEQUENCE` HRESULT.</span></span>  
  
 [<span data-ttu-id="e1fe7-115">Funciones estáticas globales para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="e1fe7-115">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)  
 <span data-ttu-id="e1fe7-116">Describe las funciones estáticas globales no administradas que utiliza la API de generación de perfiles.</span><span class="sxs-lookup"><span data-stu-id="e1fe7-116">Describes the unmanaged global static functions that the profiling API uses.</span></span>  
  
 [<span data-ttu-id="e1fe7-117">Enumeraciones para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="e1fe7-117">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)  
 <span data-ttu-id="e1fe7-118">Describe las enumeraciones no administradas que utiliza la API de generación de perfiles.</span><span class="sxs-lookup"><span data-stu-id="e1fe7-118">Describes the unmanaged enumerations that the profiling API uses.</span></span>  
  
 [<span data-ttu-id="e1fe7-119">Estructuras para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="e1fe7-119">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)  
 <span data-ttu-id="e1fe7-120">Describe las estructuras no administradas que utiliza la API de generación de perfiles.</span><span class="sxs-lookup"><span data-stu-id="e1fe7-120">Describes the unmanaged structures that the profiling API uses.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="e1fe7-121">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="e1fe7-121">Related Sections</span></span>  
 [<span data-ttu-id="e1fe7-122">Tutorial: identificar problemas de rendimiento</span><span class="sxs-lookup"><span data-stu-id="e1fe7-122">Walkthrough: Identifying Performance Problems</span></span>](/visualstudio/profiling/walkthrough-identifying-performance-problems)  
 <span data-ttu-id="e1fe7-123">Explica cómo utilizar las herramientas de generación de perfiles integradas en Microsoft Visual Studio 2005 Team System.</span><span class="sxs-lookup"><span data-stu-id="e1fe7-123">Explains how to use the built-in profiling tools in the Microsoft Visual Studio 2005 Team System.</span></span> <span data-ttu-id="e1fe7-124">Estas herramientas proporcionan una alternativa al uso de la API de generación de perfiles.</span><span class="sxs-lookup"><span data-stu-id="e1fe7-124">These tools provide an alternative approach to using the profiling API.</span></span>
