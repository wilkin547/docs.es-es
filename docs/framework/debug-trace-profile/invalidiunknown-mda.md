---
title: MDA de invalidIUnknownPointer
description: Revise el Asistente para la depuración administrada (MDA) Invalidiunknownpointer, que se activa cuando se pasa un puntero IUnknown no válido al código administrado desde código nativo.
ms.date: 03/30/2017
helpviewer_keywords:
- MDAs (managed debugging assistants), invalid IUnknown pointer
- InvalidIUnknown MDA
- invalid IUnknown pointers
- IUnknown pointers
- managed debugging assistants (MDAs), invalid IUnknown pointer
ms.assetid: c7924771-a16b-40fe-b337-ce51dcdf6a12
ms.openlocfilehash: 65d704463ed746390ff1710b590bf080013bf53d
ms.sourcegitcommit: 0edbeb66d71b8df10fcb374cfca4d731b58ccdb2
ms.contentlocale: es-ES
ms.lasthandoff: 07/07/2020
ms.locfileid: "86051732"
---
# <a name="invalidiunknown-mda"></a><span data-ttu-id="f9088-103">MDA de invalidIUnknownPointer</span><span class="sxs-lookup"><span data-stu-id="f9088-103">invalidIUnknown MDA</span></span>
<span data-ttu-id="f9088-104">El asistente para la depuración administrada (MDA) de `invalidIUnknown` se activa cuando un puntero `IUnknown` no válido se pasa a código administrado de código nativo.</span><span class="sxs-lookup"><span data-stu-id="f9088-104">The `invalidIUnknown` managed debugging assistant (MDA) is activated when an invalid `IUnknown` pointer is passed to managed code from native code.</span></span> <span data-ttu-id="f9088-105">Se produce un error en `IUnknown` a la hora de devolver un resultado correctamente cuando se solicita la interfaz `IUnknown`.</span><span class="sxs-lookup"><span data-stu-id="f9088-105">The `IUnknown` fails to return success when queried for the `IUnknown` interface.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="f9088-106">Síntomas</span><span class="sxs-lookup"><span data-stu-id="f9088-106">Symptoms</span></span>  
 <span data-ttu-id="f9088-107">Se produce un error inesperado al calcular referencias de un puntero a una interfaz COM durante el cálculo de referencias del argumento.</span><span class="sxs-lookup"><span data-stu-id="f9088-107">An unexpected error occurs when marshaling a COM interface pointer during argument marshaling.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="f9088-108">Causa</span><span class="sxs-lookup"><span data-stu-id="f9088-108">Cause</span></span>  
 <span data-ttu-id="f9088-109"> Implementación de `QueryInterface` incorrecta en la interfaz COM pasada al CLR.</span><span class="sxs-lookup"><span data-stu-id="f9088-109">An incorrect `QueryInterface` implementation on the COM interface passed to the CLR.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="f9088-110">Resolución</span><span class="sxs-lookup"><span data-stu-id="f9088-110">Resolution</span></span>  
 <span data-ttu-id="f9088-111">Corrija la implementación de `QueryInterface`.</span><span class="sxs-lookup"><span data-stu-id="f9088-111">Correct the `QueryInterface` implementation.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="f9088-112">Efecto en el Runtime</span><span class="sxs-lookup"><span data-stu-id="f9088-112">Effect on the Runtime</span></span>  
 <span data-ttu-id="f9088-113">Este MDA no tiene ningún efecto en el CLR.</span><span class="sxs-lookup"><span data-stu-id="f9088-113">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="f9088-114">Output</span><span class="sxs-lookup"><span data-stu-id="f9088-114">Output</span></span>  
 <span data-ttu-id="f9088-115">Descripción del error.</span><span class="sxs-lookup"><span data-stu-id="f9088-115">The description of the error.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="f9088-116">Configuración</span><span class="sxs-lookup"><span data-stu-id="f9088-116">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidIUnknown />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f9088-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="f9088-117">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="f9088-118">Diagnóstico de errores con asistentes de depuraciones administradas</span><span class="sxs-lookup"><span data-stu-id="f9088-118">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="f9088-119">Serialización de interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="f9088-119">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
