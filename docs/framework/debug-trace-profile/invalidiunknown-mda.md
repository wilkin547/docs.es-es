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
ms.openlocfilehash: 5df9a3f506d8c2de6f1a3125459adc2d59d510bf
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "77217364"
---
# <a name="invalidiunknown-mda"></a><span data-ttu-id="00c25-102">MDA de invalidIUnknownPointer</span><span class="sxs-lookup"><span data-stu-id="00c25-102">invalidIUnknown MDA</span></span>
<span data-ttu-id="00c25-103">El asistente para la depuración administrada (MDA) de `invalidIUnknown` se activa cuando un puntero `IUnknown` no válido se pasa a código administrado de código nativo.</span><span class="sxs-lookup"><span data-stu-id="00c25-103">The `invalidIUnknown` managed debugging assistant (MDA) is activated when an invalid `IUnknown` pointer is passed to managed code from native code.</span></span> <span data-ttu-id="00c25-104">Se produce un error en `IUnknown` a la hora de devolver un resultado correctamente cuando se solicita la interfaz `IUnknown`.</span><span class="sxs-lookup"><span data-stu-id="00c25-104">The `IUnknown` fails to return success when queried for the `IUnknown` interface.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="00c25-105">Síntomas</span><span class="sxs-lookup"><span data-stu-id="00c25-105">Symptoms</span></span>  
 <span data-ttu-id="00c25-106">Se produce un error inesperado al calcular referencias de un puntero a una interfaz COM durante el cálculo de referencias del argumento.</span><span class="sxs-lookup"><span data-stu-id="00c25-106">An unexpected error occurs when marshaling a COM interface pointer during argument marshaling.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="00c25-107">Causa</span><span class="sxs-lookup"><span data-stu-id="00c25-107">Cause</span></span>  
 <span data-ttu-id="00c25-108">Implementación de `QueryInterface` incorrecta en la interfaz COM pasada al CLR.</span><span class="sxs-lookup"><span data-stu-id="00c25-108">An incorrect `QueryInterface` implementation on the COM interface passed to the CLR.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="00c25-109">Solución</span><span class="sxs-lookup"><span data-stu-id="00c25-109">Resolution</span></span>  
 <span data-ttu-id="00c25-110">Corrija la implementación de `QueryInterface`.</span><span class="sxs-lookup"><span data-stu-id="00c25-110">Correct the `QueryInterface` implementation.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="00c25-111">Efecto en el Runtime</span><span class="sxs-lookup"><span data-stu-id="00c25-111">Effect on the Runtime</span></span>  
 <span data-ttu-id="00c25-112">Este MDA no tiene ningún efecto en el CLR.</span><span class="sxs-lookup"><span data-stu-id="00c25-112">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="00c25-113">Output</span><span class="sxs-lookup"><span data-stu-id="00c25-113">Output</span></span>  
 <span data-ttu-id="00c25-114">Descripción del error.</span><span class="sxs-lookup"><span data-stu-id="00c25-114">The description of the error.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="00c25-115">Configuración</span><span class="sxs-lookup"><span data-stu-id="00c25-115">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidIUnknown />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="00c25-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="00c25-116">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="00c25-117">Diagnosing Errors with Managed Debugging Assistants (Diagnóstico de errores con asistentes para la depuración administrada)</span><span class="sxs-lookup"><span data-stu-id="00c25-117">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="00c25-118">Serialización para interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="00c25-118">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
