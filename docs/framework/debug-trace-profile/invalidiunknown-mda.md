---
title: MDA de invalidIUnknownPointer
ms.date: 03/30/2017
helpviewer_keywords:
- MDAs (managed debugging assistants), invalid IUnknown pointer
- InvalidIUnknown MDA
- invalid IUnknown pointers
- IUnknown pointers
- managed debugging assistants (MDAs), invalid IUnknown pointer
ms.assetid: c7924771-a16b-40fe-b337-ce51dcdf6a12
author: mairaw
ms.author: mairaw
ms.openlocfilehash: db360a3b7c5f70596d5d5855b8e38dae5d484c42
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33390180"
---
# <a name="invalidiunknown-mda"></a><span data-ttu-id="9d88a-102">MDA de invalidIUnknownPointer</span><span class="sxs-lookup"><span data-stu-id="9d88a-102">invalidIUnknown MDA</span></span>
<span data-ttu-id="9d88a-103">El asistente para la depuración administrada (MDA) de `invalidIUnknown` se activa cuando un puntero `IUnknown` no válido se pasa a código administrado de código nativo.</span><span class="sxs-lookup"><span data-stu-id="9d88a-103">The `invalidIUnknown` managed debugging assistant (MDA) is activated when an invalid `IUnknown` pointer is passed to managed code from native code.</span></span> <span data-ttu-id="9d88a-104">Se produce un error en `IUnknown` a la hora de devolver un resultado correctamente cuando se solicita la interfaz `IUnknown`.</span><span class="sxs-lookup"><span data-stu-id="9d88a-104">The `IUnknown` fails to return success when queried for the `IUnknown` interface.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="9d88a-105">Síntomas</span><span class="sxs-lookup"><span data-stu-id="9d88a-105">Symptoms</span></span>  
 <span data-ttu-id="9d88a-106">Se produce un error inesperado al calcular referencias de un puntero a una interfaz COM durante el cálculo de referencias del argumento.</span><span class="sxs-lookup"><span data-stu-id="9d88a-106">An unexpected error occurs when marshaling a COM interface pointer during argument marshaling.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="9d88a-107">Motivo</span><span class="sxs-lookup"><span data-stu-id="9d88a-107">Cause</span></span>  
 <span data-ttu-id="9d88a-108">Implementación de `QueryInterface` incorrecta en la interfaz COM pasada al CLR.</span><span class="sxs-lookup"><span data-stu-id="9d88a-108">An incorrect `QueryInterface` implementation on the COM interface passed to the CLR.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="9d88a-109">Resolución</span><span class="sxs-lookup"><span data-stu-id="9d88a-109">Resolution</span></span>  
 <span data-ttu-id="9d88a-110">Corrija la implementación de `QueryInterface`.</span><span class="sxs-lookup"><span data-stu-id="9d88a-110">Correct the `QueryInterface` implementation.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="9d88a-111">Efecto en el Runtime</span><span class="sxs-lookup"><span data-stu-id="9d88a-111">Effect on the Runtime</span></span>  
 <span data-ttu-id="9d88a-112">Este MDA no tiene ningún efecto en el CLR.</span><span class="sxs-lookup"><span data-stu-id="9d88a-112">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="9d88a-113">Salida</span><span class="sxs-lookup"><span data-stu-id="9d88a-113">Output</span></span>  
 <span data-ttu-id="9d88a-114">Descripción del error.</span><span class="sxs-lookup"><span data-stu-id="9d88a-114">The description of the error.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="9d88a-115">Configuración</span><span class="sxs-lookup"><span data-stu-id="9d88a-115">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidIUnknown />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="9d88a-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="9d88a-116">See Also</span></span>  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [<span data-ttu-id="9d88a-117">Diagnosing Errors with Managed Debugging Assistants (Diagnóstico de errores con asistentes para la depuración administrada)</span><span class="sxs-lookup"><span data-stu-id="9d88a-117">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [<span data-ttu-id="9d88a-118">Serialización de interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="9d88a-118">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
