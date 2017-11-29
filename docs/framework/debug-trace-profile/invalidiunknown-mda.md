---
title: MDA de invalidIUnknownPointer
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MDAs (managed debugging assistants), invalid IUnknown pointer
- InvalidIUnknown MDA
- invalid IUnknown pointers
- IUnknown pointers
- managed debugging assistants (MDAs), invalid IUnknown pointer
ms.assetid: c7924771-a16b-40fe-b337-ce51dcdf6a12
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 04fdc96168823397296449ebc25ccdded1ea55c9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="invalidiunknown-mda"></a><span data-ttu-id="265a7-102">MDA de invalidIUnknownPointer</span><span class="sxs-lookup"><span data-stu-id="265a7-102">invalidIUnknown MDA</span></span>
<span data-ttu-id="265a7-103">El asistente para la depuración administrada (MDA) de `invalidIUnknown` se activa cuando un puntero `IUnknown` no válido se pasa a código administrado de código nativo.</span><span class="sxs-lookup"><span data-stu-id="265a7-103">The `invalidIUnknown` managed debugging assistant (MDA) is activated when an invalid `IUnknown` pointer is passed to managed code from native code.</span></span> <span data-ttu-id="265a7-104">Se produce un error en `IUnknown` a la hora de devolver un resultado correctamente cuando se solicita la interfaz `IUnknown`.</span><span class="sxs-lookup"><span data-stu-id="265a7-104">The `IUnknown` fails to return success when queried for the `IUnknown` interface.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="265a7-105">Síntomas</span><span class="sxs-lookup"><span data-stu-id="265a7-105">Symptoms</span></span>  
 <span data-ttu-id="265a7-106">Se produce un error inesperado al calcular referencias de un puntero a una interfaz COM durante el cálculo de referencias del argumento.</span><span class="sxs-lookup"><span data-stu-id="265a7-106">An unexpected error occurs when marshaling a COM interface pointer during argument marshaling.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="265a7-107">Motivo</span><span class="sxs-lookup"><span data-stu-id="265a7-107">Cause</span></span>  
 <span data-ttu-id="265a7-108">Implementación de `QueryInterface` incorrecta en la interfaz COM pasada al CLR.</span><span class="sxs-lookup"><span data-stu-id="265a7-108">An incorrect `QueryInterface` implementation on the COM interface passed to the CLR.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="265a7-109">Resolución</span><span class="sxs-lookup"><span data-stu-id="265a7-109">Resolution</span></span>  
 <span data-ttu-id="265a7-110">Corrija la implementación de `QueryInterface`.</span><span class="sxs-lookup"><span data-stu-id="265a7-110">Correct the `QueryInterface` implementation.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="265a7-111">Efecto en el Runtime</span><span class="sxs-lookup"><span data-stu-id="265a7-111">Effect on the Runtime</span></span>  
 <span data-ttu-id="265a7-112">Este MDA no tiene ningún efecto en el CLR.</span><span class="sxs-lookup"><span data-stu-id="265a7-112">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="265a7-113">Salida</span><span class="sxs-lookup"><span data-stu-id="265a7-113">Output</span></span>  
 <span data-ttu-id="265a7-114">Descripción del error.</span><span class="sxs-lookup"><span data-stu-id="265a7-114">The description of the error.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="265a7-115">Configuración</span><span class="sxs-lookup"><span data-stu-id="265a7-115">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidIUnknown />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="265a7-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="265a7-116">See Also</span></span>  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [<span data-ttu-id="265a7-117">Diagnosing Errors with Managed Debugging Assistants (Diagnóstico de errores con asistentes para la depuración administrada)</span><span class="sxs-lookup"><span data-stu-id="265a7-117">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [<span data-ttu-id="265a7-118">Serialización para interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="265a7-118">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
