---
title: MDA de illegalPrepareConstrainedRegion
ms.date: 03/30/2017
helpviewer_keywords:
- PrepareConstrainedRegions method
- managed debugging assistants (MDAs), illegal PrepareConstrainedRegions
- try/catch exception handling, managed debugging assistants
- IllegalPrepareConstrainedRegions MDA
- MDAs (managed debugging assistants), illegal PrepareConstrainedRegions
ms.assetid: 2f9b5031-f910-4e01-a196-f89eab313eaf
ms.openlocfilehash: b80d6160876834b22e8d9d1eb7112b8b67c15fcc
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "77216470"
---
# <a name="illegalprepareconstrainedregion-mda"></a><span data-ttu-id="3b487-102">MDA de illegalPrepareConstrainedRegion</span><span class="sxs-lookup"><span data-stu-id="3b487-102">illegalPrepareConstrainedRegion MDA</span></span>
<span data-ttu-id="3b487-103">El Asistente para la depuración administrada (MDA) `illegalPrepareConstrainedRegion` se activa cuando una llamada al método <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A?displayProperty=nameWithType> no precede inmediatamente a la instrucción `try` del controlador de excepciones.</span><span class="sxs-lookup"><span data-stu-id="3b487-103">The `illegalPrepareConstrainedRegion` managed debugging assistant (MDA) is activated when a <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A?displayProperty=nameWithType> method call does not immediately precede the `try` statement of the exception handler.</span></span> <span data-ttu-id="3b487-104">Esta restricción está en el nivel de MSIL, por lo que permite tener un origen de no generación de código entre la llamada y `try` (por ejemplo comentarios).</span><span class="sxs-lookup"><span data-stu-id="3b487-104">This restriction is at the MSIL level, so it is permissible to have non-code-generating source between the call and the `try`, such as comments.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="3b487-105">Síntomas</span><span class="sxs-lookup"><span data-stu-id="3b487-105">Symptoms</span></span>  
 <span data-ttu-id="3b487-106">Una región de ejecución restringida (CER) que nunca se trata como tal, sino como un simple bloque de control de excepciones (`finally` o `catch`).</span><span class="sxs-lookup"><span data-stu-id="3b487-106">A constrained execution region (CER) that is never treated as such, but as a simple exception handling block (`finally` or `catch`).</span></span> <span data-ttu-id="3b487-107">En consecuencia, la región no se ejecuta en el caso de una condición de memoria insuficiente o una anulación del subproceso.</span><span class="sxs-lookup"><span data-stu-id="3b487-107">As a consequence, the region does not run in the event of an out-of-memory condition or a thread abort.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="3b487-108">Causa</span><span class="sxs-lookup"><span data-stu-id="3b487-108">Cause</span></span>  
 <span data-ttu-id="3b487-109">El modelo de preparación para una región CER no se ha seguido correctamente.</span><span class="sxs-lookup"><span data-stu-id="3b487-109">The preparation pattern for a CER is not followed correctly.</span></span>  <span data-ttu-id="3b487-110">Se trata de un evento de error.</span><span class="sxs-lookup"><span data-stu-id="3b487-110">This is an error event.</span></span> <span data-ttu-id="3b487-111">La llamada al método <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A> utilizada para marcar los controladores de excepciones como la introducción de una CER en su `catch`/`finally`/`fault`/bloques `filter` deben usarse inmediatamente antes de la instrucción `try`.</span><span class="sxs-lookup"><span data-stu-id="3b487-111">The <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A> method call used to mark exception handlers as introducing a CER in their `catch`/`finally`/`fault`/`filter` blocks must be used immediately before the `try` statement.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="3b487-112">Solución</span><span class="sxs-lookup"><span data-stu-id="3b487-112">Resolution</span></span>  
 <span data-ttu-id="3b487-113">Asegúrese de que la llamada a <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A> se produce inmediatamente antes de la instrucción `try`.</span><span class="sxs-lookup"><span data-stu-id="3b487-113">Ensure that the call to <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A> happens immediately before the `try` statement.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="3b487-114">Efecto en el Runtime</span><span class="sxs-lookup"><span data-stu-id="3b487-114">Effect on the Runtime</span></span>  
 <span data-ttu-id="3b487-115">Este MDA no tiene ningún efecto en el CLR.</span><span class="sxs-lookup"><span data-stu-id="3b487-115">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="3b487-116">Output</span><span class="sxs-lookup"><span data-stu-id="3b487-116">Output</span></span>  
 <span data-ttu-id="3b487-117">El MDA muestra el nombre del método que llama al método <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A>, el desplazamiento MSIL y un mensaje que indica que la llamada no precede inmediatamente al inicio del bloque try.</span><span class="sxs-lookup"><span data-stu-id="3b487-117">The MDA displays the name of the method calling the <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A> method, the MSIL offset, and a message indicating the call does not immediately precede the beginning of the try block.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="3b487-118">Configuración</span><span class="sxs-lookup"><span data-stu-id="3b487-118">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <illegalPrepareConstrainedRegion/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a><span data-ttu-id="3b487-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3b487-119">Example</span></span>  
 <span data-ttu-id="3b487-120">En el ejemplo de código siguiente se muestra el patrón que hace que se active este MDA.</span><span class="sxs-lookup"><span data-stu-id="3b487-120">The following code example demonstrates the pattern that causes this MDA to be activated.</span></span>  
  
```csharp
void MethodWithInvalidPCR()  
{  
    RuntimeHelpers.PrepareConstrainedRegions();  
    Object o = new Object();  
    try  
    {  
        …  
    }  
    finally  
    {  
        …  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="3b487-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3b487-121">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A>
- [<span data-ttu-id="3b487-122">Diagnosing Errors with Managed Debugging Assistants (Diagnóstico de errores con asistentes para la depuración administrada)</span><span class="sxs-lookup"><span data-stu-id="3b487-122">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="3b487-123">Serialización para interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="3b487-123">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
